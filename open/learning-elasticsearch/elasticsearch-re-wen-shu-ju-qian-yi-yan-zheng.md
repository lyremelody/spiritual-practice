---
description: '2018-12-11'
---

# Elasticsearch热温数据迁移验证

## 1.目的

实现Elasticsearch不同级别的数据在不同存储介质中迁移。

实现方式：

当前基于Elasticsearch容器实例与存储介质绑定，并给予存储介质的特性定义标签。如：

* 定义绑定SSD的Elasticsearch实例\(节点\)为热节点\(hot\)
* 定义绑定SATA的Elasticsearch实例\(节点\)为温节点\(warm\)

  
设置索引规则默认写入到热节点，当需要进行存储迁移转换的时候，通过定时任务的方式设置索引的路由规则，以触发索引存储介质的迁移。下面验证索引介质迁移的触发。（产品实现上可通过定时任务管理来实现）

## 2.环境配置

### 2.1 存储配置

将SSD和SATA分别挂载到主机目录:

* /usrvol/ssd
* /usrvol/sata

### 2.2 Elasticsearch配置

#### 2.2.1 ES Node1数据存储使用SSD（/usrvol/ssd），配置为热节点

{% code title="elasticsearch.yml" %}
```yaml
cluster.name: elasticsearch
node.name: node1node.master: true
node.data: true
node.attr.box_type: hot
path.logs: /usr/share/elasticsearch/logs
network.host: 0.0.0.0
http.port: 9200
transport.tcp.port: 9300
# this value is required because we set "network.host"
# be sure to modify it appropriately for a production cluster deployment
discovery.zen.minimum_master_nodes: 1
discovery.zen.ping.unicast.hosts: ["10.211.55.5:9300","10.211.55.5:9301"]
```
{% endcode %}

启动参数：

```bash
docker run -itd --name=elasticsearch_hot --restart=always \
    -v /usrvol/ssd/data:/usr/share/elasticsearch/data \
    -v /root/hot/elasticsearch/config:/usr/share/elasticsearch/config \
    -v /root/hot/elasticsearch/plugins:/usr/share/elasticsearch/plugins \
    -v /root/hot/elasticsearch/logs:/usr/share/elasticsearch/logs \
    -v /etc/localtime:/etc/localtime \
    --net=host elasticsearch:5.0.2
```

#### 2.2.2 ES Node2数据存储使用SATA（/usrvol/sata），配置为温节点

{% code title="elasticsearch.yml" %}
```yaml
cluster.name: elasticsearch
node.name: node2
node.master: false
node.data: true
node.attr.box_type: warm
path.logs: /usr/share/elasticsearch/logs
network.host: 0.0.0.0
http.port: 9200
transport.tcp.port: 9300
# this value is required because we set "network.host"
# be sure to modify it appropriately for a production cluster deployment
discovery.zen.minimum_master_nodes: 1
discovery.zen.ping.unicast.hosts: ["10.211.55.5:9300","10.211.55.5:9301"]
```
{% endcode %}

启动参数：

```bash
docker run -itd --name=elasticsearch_warm --restart=always \
    -v /usrvol/ssd/data:/usr/share/elasticsearch/data \
    -v /root/warm/elasticsearch/config:/usr/share/elasticsearch/config \
    -v /root/warm/elasticsearch/plugins:/usr/share/elasticsearch/plugins \
    -v /root/warm/elasticsearch/logs:/usr/share/elasticsearch/logs \    
    -v /etc/localtime:/etc/localtime \
    --net=host elasticsearch:5.0.2
```

## 3.热数据到温数据的迁移

### 3.1执行数据切换过程

默认logstash-2018.12.11分配在SSD（node1）；修改索引的标签属性，以实现在ES实例的转移，从而实现在存储介质的转移。

![&#x56FE;1 &#x6570;&#x636E;&#x5207;&#x6362;&#x8FC7;&#x7A0B;](../../.gitbook/assets/2018121101.png)

### 3.2 结果

将logstash-2018.12.11从SSD（node1）迁移到了SATA （node2）。

![&#x56FE;2 &#x5207;&#x6362;&#x7ED3;&#x679C;](../../.gitbook/assets/2018121102.png)


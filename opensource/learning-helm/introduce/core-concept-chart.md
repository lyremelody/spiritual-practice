# Chart

## 1 Chart 目录结构和配置文件说明

Chart 是一个包含一系列文件的目录。目录的名字就是 Chart 的名字（不包含版本信息），例如一个 WordPress 的 Chart 就会存储在 wordpress 目录中。

目录中的文件结构如下：

```text
wordpress/
    Chart.yaml         # 用于描述 Chart 信息的 YAML 文件
    LICENSE            # 可选：Chart 的许可信息
    README.md          # 可选：README 文件
    values.yaml        # 默认的配置值
    charts/            # 可选：包含该 Chart 所依赖的其他 Chart，依赖管理推荐采用 requirements.yaml 文件来管理
    templates/         # 可选：结合 values.yaml，能够生成 Kubernetes 的 manifest 文件
        NOTES.txt      # 可选：用法描述
```

charts 目录和 requirements.yaml 的区别在于，前者需要提供整个 Chart 的文件，后者仅需要注明依赖 Chart 的仓库信息，例如一个 requirements.yaml 可以定义为：

```text
# requirements.yaml
dependencies:
  - name: apache
    version: 1.2.3
    repository: http://example.com/charts
  - name: mysql
    version: 3.2.1
    repository: http://another.example.com/charts
```

### 1.1 Chart.yaml 文件说明

| key | 可选/必选 | 说明 |
| :--- | :--- | :--- |
| name | 必选 | Chart 名 |
| version | 必选 | SemVer 2 规范的版本号 |
| description | 可选 | 项目的描述 |
| keywords | 可选 | 一个用于描述项目的关键字列表 |
| home | 可选 | 项目的主页 |
| sources | 可选 | 一个 URL 列表，说明项目的源代码地址 |
| maintainers | 可选 | 维护者列表 |
| maintainers.name | 可选 | 维护者名字 |
| maintainers.email | 可选 | 维护者邮箱 |
| engine | 可选 | 模版引擎名称，默认是 gotpl |
| appVersion | 可选 | Chart 中包含的应用的版本，无须遵循 SemVer 规范 |
| deprecated | 可选 | 布尔值，该 Chart 是否标注为“弃用“ |
| tillerVersion | 可选 | 该 Chart 所需的 Tiller 版本。取值应该是一个 SemVer 的范围，例如“&gt;2.0.0“ |

#### 1.1.1 例子

```text
apiVersion: v1
name: nginx-ingress
version: 1.33.0
appVersion: 0.30.0
home: https://github.com/kubernetes/ingress-nginx
description: An nginx Ingress controller that uses ConfigMap to store the nginx configuration.
icon: https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Nginx_logo.svg/500px-Nginx_logo.svg.png
keywords:
  - ingress
  - nginx
sources:
  - https://github.com/kubernetes/ingress-nginx
maintainers:
  - name: ChiefAlexander
  - name: taharah
    email: Trevor.G.Wood@gmail.com
engine: gotpl
kubeVersion: ">=1.10.0-0"
```




# Helm核心概念

Helm 的主要概念：Chart、Release、Repository。

## 1 Chart

Chart 是一个 Helm 包，其中包含了运行一个应用所需要的工具和资源定义，还可能包含 Kubernetes 集群中的服务定义，类似 Homebrew 中的 formula、APT 中的 dpkg 或者 Yum 中的 RPM 文件。

详细见 《[Chart](core-concept-chart.md)》

## 2 Release

Release 是在 Kubernetes 集群上运行的一个 Chart 实例。在同一个集群上，一个 Chart 可以安装多次。例如有一个 MySQL Chart，如果想在服务器上运行两个 MySQL 数据库，就可以基于这个 Chart 安装两次。每次安装都会生成新的 Release，会有独立的 Release 名称。

## 3 Repository

Repository 是用于存放和共享 Chart 的仓库，用于 Kubernetes 上应用的包。类似 Perl 的 [CPAN archive](https://www.cpan.org/) 或者 [Fedora Package Database](https://admin.fedoraproject.org/pkgdb/)。




[Docker](https://www.docker.com/) 是一个开源的应用容器引擎，而一个容器containers其实是一个虚拟化的独立的环境，让开发者可以打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。容器是完全使用沙箱机制，相互之间不会有任何接口。

> Docker 的局限性之一，它只能用在 64 位的操作系统上。

# 目录

[](https://github.com/jaywcjlove/docker-tutorial#%E7%9B%AE%E5%BD%95)

- [新版本安装](https://github.com/jaywcjlove/docker-tutorial#%E6%96%B0%E7%89%88%E6%9C%AC%E5%AE%89%E8%A3%85)
- [旧版本安装](https://github.com/jaywcjlove/docker-tutorial#%E6%97%A7%E7%89%88%E6%9C%AC%E5%AE%89%E8%A3%85)
- [命令介绍](https://github.com/jaywcjlove/docker-tutorial#%E5%91%BD%E4%BB%A4%E4%BB%8B%E7%BB%8D)
- [服务管理](https://github.com/jaywcjlove/docker-tutorial#%E6%9C%8D%E5%8A%A1%E7%AE%A1%E7%90%86)
- [镜像管理](https://github.com/jaywcjlove/docker-tutorial#%E9%95%9C%E5%83%8F%E7%AE%A1%E7%90%86)
    - [通过容器创建镜像](https://github.com/jaywcjlove/docker-tutorial#%E9%80%9A%E8%BF%87%E5%AE%B9%E5%99%A8%E5%88%9B%E5%BB%BA%E9%95%9C%E5%83%8F)
    - [通过Dockerfile创建镜像](https://github.com/jaywcjlove/docker-tutorial#%E9%80%9A%E8%BF%87dockerfile%E5%88%9B%E5%BB%BA%E9%95%9C%E5%83%8F)
    - [发布自己的镜像](https://github.com/jaywcjlove/docker-tutorial#%E5%8F%91%E5%B8%83%E8%87%AA%E5%B7%B1%E7%9A%84%E9%95%9C%E5%83%8F)
    - [镜像中安装软件](https://github.com/jaywcjlove/docker-tutorial#%E9%95%9C%E5%83%8F%E4%B8%AD%E5%AE%89%E8%A3%85%E8%BD%AF%E4%BB%B6)
- [容器管理](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%B9%E5%99%A8%E7%AE%A1%E7%90%86)
    - [容器服务管理](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%B9%E5%99%A8%E6%9C%8D%E5%8A%A1%E7%AE%A1%E7%90%86)
    - [进入容器](https://github.com/jaywcjlove/docker-tutorial#%E8%BF%9B%E5%85%A5%E5%AE%B9%E5%99%A8)
- [文件拷贝](https://github.com/jaywcjlove/docker-tutorial#%E6%96%87%E4%BB%B6%E6%8B%B7%E8%B4%9D)
- [Docker私有仓库搭建](https://github.com/jaywcjlove/docker-tutorial#docker%E7%A7%81%E6%9C%89%E4%BB%93%E5%BA%93%E6%90%AD%E5%BB%BA)
    - [`registry`](https://github.com/jaywcjlove/docker-tutorial#registry)
    - [`Harbor`](https://github.com/jaywcjlove/docker-tutorial#harbor)
- [使用 Docker 实战](https://github.com/jaywcjlove/docker-tutorial#%E4%BD%BF%E7%94%A8-docker-%E5%AE%9E%E6%88%98)
- [Docker REST API](https://github.com/jaywcjlove/docker-tutorial#docker-rest-api)
    - [`Nginx`](https://github.com/jaywcjlove/docker-tutorial#nginx)
    - [`MySQL`](https://github.com/jaywcjlove/docker-tutorial#mysql)
    - [`PostgreSQL`](https://github.com/jaywcjlove/docker-tutorial#postgres)
    - [`Redis`](https://github.com/jaywcjlove/docker-tutorial#redis)
    - [`Elasticsearch`](https://github.com/jaywcjlove/docker-tutorial#elasticsearch)
    - [`Gitlab`](https://github.com/jaywcjlove/docker-tutorial#gitlab)
    - [`Jenkins`](https://github.com/jaywcjlove/docker-tutorial#jenkins)
    - [`Rocket.Chat`](https://github.com/jaywcjlove/docker-tutorial#rocketchat)
    - [`Rancher`](https://github.com/jaywcjlove/docker-tutorial#rancher)
    - [`Portainer`](https://github.com/jaywcjlove/docker-tutorial#portainer)
    - [`Sourcegraph`](https://github.com/jaywcjlove/docker-tutorial#sourcegraph)
    - [`Mattermost`](https://github.com/jaywcjlove/docker-tutorial#Mattermost)
    - [`NPS`](https://github.com/jaywcjlove/docker-tutorial#nps)
    - [`Penpot`](https://github.com/jaywcjlove/docker-tutorial#penpot)
    - [`Navidrome`](https://github.com/jaywcjlove/docker-tutorial#navidrome)
    - [`Humpback`](https://github.com/jaywcjlove/docker-tutorial#humpback)
    - [`Seafile`](https://github.com/jaywcjlove/docker-tutorial#seafile)
    - [更多](https://github.com/jaywcjlove/docker-tutorial#%E6%9B%B4%E5%A4%9A)
- [卸载旧的版本](https://github.com/jaywcjlove/docker-tutorial#%E5%8D%B8%E8%BD%BD%E6%97%A7%E7%9A%84%E7%89%88%E6%9C%AC)
- [错误处理](https://github.com/jaywcjlove/docker-tutorial#%E9%94%99%E8%AF%AF%E5%A4%84%E7%90%86)
- [参考资料](https://github.com/jaywcjlove/docker-tutorial#%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99)
    - [官方英文资源](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%98%E6%96%B9%E8%8B%B1%E6%96%87%E8%B5%84%E6%BA%90)
    - [中文资源](https://github.com/jaywcjlove/docker-tutorial#%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90)
    - [其它资源](https://github.com/jaywcjlove/docker-tutorial#%E5%85%B6%E5%AE%83%E8%B5%84%E6%BA%90)

Docker 从 `1.13` 版本之后采用时间线的方式作为版本号，分为社区版 `CE` 和企业版 `EE`，社区版是免费提供给个人开发者和小型团体使用的，企业版会提供额外的收费服务，比如经过官方测试认证过的基础设施、容器、插件等。

社区版按照 `stable` 和 `edge` 两种方式发布，每个季度更新 `stable` 版本，如 `17.06`，`17.09`；每个月份更新 `edge` 版本，如`17.09`，`17.10`。

下面教程运行在 `Centos` 中

## 新版本安装

[](https://github.com/jaywcjlove/docker-tutorial#%E6%96%B0%E7%89%88%E6%9C%AC%E5%AE%89%E8%A3%85)

Docker 官方的安装教程，[在这里](https://docs.docker.com/install/linux/docker-ce/centos/)。

安装一些必要的系统工具

```shell
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

添加软件源信息

```shell
# docker 官方源
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# 阿里云源
sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

可选：启用 `edge` 和 `test` 存储库。 这些存储库包含在上面的 `docker.repo` 文件中，但默认情况下处于禁用状态。您可以将它们与稳定存储库一起启用。

```
$ sudo yum-config-manager --enable docker-ce-edge
$ sudo yum-config-manager --enable docker-ce-test
```

您可以通过使用 `--disable` 标志运行 `yum-config-manager` 命令来禁用边缘或测试存储库。 要重新启用它，请使用 `--enable` 标志。 以下命令禁用 `edge` 存储库:

```shell
$ sudo yum-config-manager --disable docker-ce-edge
$ sudo yum-config-manager --disable docker-ce-test
```

安装 Docker-ce

```shell
# 安装前可以先更新 yum 缓存：
sudo yum makecache fast
# 安装 Docker-ce
sudo yum install docker-ce
```

如果你想安装特定 `docker-ce` 版本，先列出 repo 中可用版本，然后选择安装

```shell
$ yum list docker-ce --showduplicates | sort -r
# docker-ce.x86_64       18.06.1.ce-3.el7              docker-ce-stable
# docker-ce.x86_64       18.06.1.ce-3.el7              @docker-ce-stable
# docker-ce.x86_64       18.06.0.ce-3.el7              docker-ce-stable
# docker-ce.x86_64       18.03.1.ce-1.el7.centos       docker-ce-stable
# docker-ce.x86_64       18.03.0.ce-1.el7.centos       docker-ce-stable
# docker-ce.x86_64       17.12.1.ce-1.el7.centos       docker-ce-stable
# 选择版本安装
$ sudo yum install docker-ce-<VERSION STRING>

# 选择安装 docker-ce-18.06.1.ce
$ sudo yum install docker-ce-18.06.1.ce
```

启动 Docker 后台服务

```shell
$ sudo systemctl start docker
```

通过运行 `hello-world` 镜像，验证是否正确安装了 `docker`。

```shell
$ docker run hello-world
```

## 旧版本安装

[](https://github.com/jaywcjlove/docker-tutorial#%E6%97%A7%E7%89%88%E6%9C%AC%E5%AE%89%E8%A3%85)

```shell
yum install docker        # CentOS 中安装
apt-get install docker-ce # Ubuntu 中安装
pacman -S docker          # Arch 中安装
emerge --ask docker       # Gentoo 中安装

#=====================
docker version      # 通过查看版本，检查安装是否成功
# Client:
#  Version:         1.12.6
#  API version:     1.24
#  Package version: docker-1.12.6-55.gitc4618fb.el7.centos.x86_64
#  Go version:      go1.8.3
#  Git commit:      c4618fb/1.12.6
#  Built:           Thu Sep 21 22:33:52 2017
#  OS/Arch:         linux/amd64
# 
# Server:
#  Version:         1.12.6
#  API version:     1.24
#  Package version: docker-1.12.6-55.gitc4618fb.el7.centos.x86_64
#  Go version:      go1.8.3
#  Git commit:      c4618fb/1.12.6
#  Built:           Thu Sep 21 22:33:52 2017
#  OS/Arch:         linux/amd64
```

## 命令介绍

[](https://github.com/jaywcjlove/docker-tutorial#%E5%91%BD%E4%BB%A4%E4%BB%8B%E7%BB%8D)

```shell
$ docker --help

管理命令:
  container   管理容器
  image       管理镜像
  network     管理网络
命令：
  attach      介入到一个正在运行的容器
  build       根据 Dockerfile 构建一个镜像
  commit      根据容器的更改创建一个新的镜像
  cp          在本地文件系统与容器中复制 文件/文件夹
  create      创建一个新容器
  exec        在容器中执行一条命令
  images      列出镜像
  kill        杀死一个或多个正在运行的容器    
  logs        取得容器的日志
  pause       暂停一个或多个容器的所有进程
  ps          列出所有容器
  pull        拉取一个镜像或仓库到 registry
  push        推送一个镜像或仓库到 registry
  rename      重命名一个容器
  restart     重新启动一个或多个容器
  rm          删除一个或多个容器
  rmi         删除一个或多个镜像
  run         在一个新的容器中执行一条命令
  search      在 Docker Hub 中搜索镜像
  start       启动一个或多个已经停止运行的容器
  stats       显示一个容器的实时资源占用
  stop        停止一个或多个正在运行的容器
  tag         为镜像创建一个新的标签
  top         显示一个容器内的所有进程
  unpause     恢复一个或多个容器内所有被暂停的进程
```

## 服务管理

[](https://github.com/jaywcjlove/docker-tutorial#%E6%9C%8D%E5%8A%A1%E7%AE%A1%E7%90%86)

```shell
service docker start       # 启动 docker 服务，守护进程
service docker stop        # 停止 docker 服务
service docker status      # 查看 docker 服务状态
chkconfig docker on        # 设置为开机启动
```

## 镜像管理

[](https://github.com/jaywcjlove/docker-tutorial#%E9%95%9C%E5%83%8F%E7%AE%A1%E7%90%86)

镜像可以看做我们平时装系统的镜像，里面就是一个运行环境。

```shell
docker pull centos:latest  # 从docker.io中下载centos镜像到本地
docker images              # 查看已下载的镜像
docker rmi [image_id]      # 删除镜像，指定镜像id

# 删除所有镜像
# none 默认为 docker.io
docker rmi $(docker images | grep none | awk '{print $3}' | sort -r)

# 连接进行进入命令行模式，exit命令退出。
docker run -t -i nginx:latest /bin/bash
```

### 下载镜像本地安装镜像

[](https://github.com/jaywcjlove/docker-tutorial#%E4%B8%8B%E8%BD%BD%E9%95%9C%E5%83%8F%E6%9C%AC%E5%9C%B0%E5%AE%89%E8%A3%85%E9%95%9C%E5%83%8F)

由于国区已经无法访问，可以将镜像打包，直接安装镜像压缩文件

```shell
$ docker pull gitlab/gitlab-ce:17.2.0-ce.0 # 下载镜像
$ docker pull --platform linux/amd64 gitlab/gitlab-ce:17.2.0-ce.0
$ docker pull --platform linux/amd64 portainer/portainer-ce:2.20.3-alpine
$ docker pull --platform linux/amd64 portainer/agent:2.20.3-alpine
# 保存 Docker 镜像到本地文件
$ docker save -o [output-file.tar] [image-name]
$ docker save -o gitlab-ce.0-17.2.0.tar gitlab/gitlab-ce:17.2.0-ce.0
$ docker save -o portainer-agent-2.20.3-alpine.tar portainer/agent:2.20.3-alpine
$ docker save -o portainer-ce-2.20.3-alpine.tar portainer/portainer-ce:2.20.3-alpine
```

将镜像文件发送到服务器

```shell
$ scp [output-file.tar] [user]@[server-ip]:[path]
$ scp gitlab-ce-17.0.1.tar root@110.55.8.163:/home/docker-images
```

服务器上加载 Docker 镜像

```shell
$ docker load -i /home/docker-images/gitlab-ce-17.0.1.tar # 加载 Docker 镜像
$ docker images # 验证镜像是否加载成功
```

### 通过容器创建镜像

[](https://github.com/jaywcjlove/docker-tutorial#%E9%80%9A%E8%BF%87%E5%AE%B9%E5%99%A8%E5%88%9B%E5%BB%BA%E9%95%9C%E5%83%8F)

我们可以通过以下两种方式对镜像进行更改。

1. 从已经创建的容器中更新镜像，并且提交这个镜像
2. 使用 Dockerfile 指令来创建一个新的镜像

下面通过已存在的容器创建一个新的镜像。

```shell
docker commit -m="First Docker" -a="wcjiang" a6b0a6cfdacf wcjiang/nginx:v1.2.1
```

上面命令参数说明：

- `-m` 提交的描述信息
- `-a` 指定镜像作者
- `a6b0a6cfdacf` 记住这个是容器id，不是镜像id
- `wcjiang/nginx:v1.2.1` 创建的目标镜像名

### 通过Dockerfile创建镜像

[](https://github.com/jaywcjlove/docker-tutorial#%E9%80%9A%E8%BF%87dockerfile%E5%88%9B%E5%BB%BA%E9%95%9C%E5%83%8F)

假设创建一个 node.js 镜像，首先在 node.js 项目根目录创建文件。

```shell
touch Dockerfile .dockerignore
```

`.dockerignore` 文件内容，下面代码表示，这三个路径要排除，不要打包进入 image 文件。如果你没有路径要排除，这个文件可以不新建。

```shell
.git
node_modules
npm-debug.log
```

Dockerfile 文件内容

```dockerfile
FROM node:8.4
COPY . /app
WORKDIR /app
RUN npm install --registry=https://registry.npm.taobao.org
EXPOSE 3000
```

- `FROM node:8.4`：该 `image` 文件继承官方的 `node image`，冒号表示标签，这里标签是`8.4`，即`8.4`版本的 `node`。
- `COPY . /app`：将当前目录下的所有文件（除了 `.dockerignore` 排除的路径），都拷贝进入 `image` 文件的 `/app` 目录。
- `WORKDIR /app`：指定接下来的工作路径为`/app`。
- `RUN npm install`：在/app目录下，运行 `npm install` 命令安装依赖。注意，安装后所有的依赖，都将打包进入 `image` 文件。
- `EXPOSE 3000`：将容器 `3000` 端口暴露出来， 允许外部连接这个端口。

有了 `Dockerfile` 文件以后，就可以使用 `docker image build` 命令创建 `image` 文件了。

```shell
$ docker image build -t koa-demo .
# 或者
$ docker image build -t koa-demo:0.0.1 .
```

上面命令，`-t` 参数用来指定 `image` 文件的名字，后面还可以用冒号指定标签。如果不指定，默认的标签就是 `latest`。注意后面有个 `.`，表示 Dockerfile 文件所在的路径为当前路径

```shell
docker run --name koa-demo-name --rm -d -p 9066:3000 koa-demo:latest
# 或者
docker run --name koa-demo-name --rm -d -p 9066:3000 koa-demo:0.0.1
```

上面命令，将刚创建的 `koa-demo` 景象跑起来，命令的 `--rm` 参数，在容器终止运行后自动删除容器文件。

### 发布自己的镜像

[](https://github.com/jaywcjlove/docker-tutorial#%E5%8F%91%E5%B8%83%E8%87%AA%E5%B7%B1%E7%9A%84%E9%95%9C%E5%83%8F)

1. 在[Docker](https://www.docker.com/) 注册账户，发布的镜像都在[这个页面里](https://cloud.docker.com/repository/list)展示
2. 将上面做的镜像`nginx`，起个新的名字`nginx-test`

```shell
docker tag wcjiang/nginx:v1.2.1 wcjiang/nginx-test:lastest
```

3. 登录docker

```
docker login
```

4. 上传`nginx-test`镜像

```shell
docker push wcjiang/nginx-test:lastest
# The push refers to a repository [docker.io/wcjiang/nginx-test]
# 2f5c6a3c22e3: Mounted from wcjiang/nginx
# cf516324493c: Mounted from wcjiang/nginx
# lastest: digest: sha256:73ae804b2c60327d1269aa387cf782f664bc91da3180d10dbd49027d7adaa789 size: 736
```

### 镜像中安装软件

[](https://github.com/jaywcjlove/docker-tutorial#%E9%95%9C%E5%83%8F%E4%B8%AD%E5%AE%89%E8%A3%85%E8%BD%AF%E4%BB%B6)

通常情况下，使用docker官方镜像，如 mysql镜像，默认情况下镜像中啥软件也没有，通过下面命令安装你所需要的软件：

```shell
# 第一次需要运行这个命令，确保源的索引是最新的
# 同步 /etc/apt/sources.list 和 /etc/apt/sources.list.d 中列出的源的索引
apt-get update
# 做过上面更新同步之后，可以运行下面的命令了
apt-get install vim
```

如果你安装了CentOS或者Ubuntu系统可以进入系统安装相关软件

```shell
# 进入到centos7镜像系统
docker run -i -t centos:7 /bin/bash
yum update
yum install vim
```

## 容器管理

[](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%B9%E5%99%A8%E7%AE%A1%E7%90%86)

容器就像一个类的实例

```shell
# 列出本机正在运行的容器
docker container ls
# 列出本机所有容器，包括终止运行的容器
docker container ls --all
docker start [containerID/Names] # 启动容器
docker stop [containerID/Names]  # 停止容器
docker rm [containerID/Names]    # 删除容器
docker logs [containerID/Names]  # 查看日志
docker exec -it [containerID/Names] /bin/bash  # 进入容器

# 从正在运行的 Docker 容器里面，将文件拷贝到本机，注意后面有个【点】拷贝到当前目录
docker container cp [containID]:[/path/to/file] .

docker run centos echo "hello world"  # 在docker容器中运行hello world!
docker run centos yum install -y wget # 在docker容器中，安装wget软件
docker ps                             # 列出包括未运行的容器
docker ps -a                          # 查看所有容器(包括正在运行和已停止的)
docker logs my-nginx                  # 查看 my-nginx 容器日志

docker run -i -t centos /bin/bash     # 启动一个容器
docker inspect centos                 # 检查运行中的镜像
docker commit 8bd centos              # 保存对容器的修改
docker commit -m "n changed" my-nginx my-nginx-image # 使用已经存在的容器创建一个镜像
docker inspect -f {{.State.Pid}} 44fc0f0582d9        # 获取id为 44fc0f0582d9 的PID进程编号
# 下载指定版本容器镜像
docker pull gitlab/gitlab-ce:11.2.3-ce.0
```

### 容器服务管理

[](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%B9%E5%99%A8%E6%9C%8D%E5%8A%A1%E7%AE%A1%E7%90%86)

```shell
docker run -itd --name my-nginx2 nginx  # 通过nginx镜像，【创建】容器名为 my-nginx2 的容器
docker start my-nginx --restart=always  # 【启动策略】一个已经存在的容器启动添加策略
    # no - 容器不重启
    # on-failure - 容器推出状态非0时重启
    # always - 始终重启
docker start my-nginx             # 【启动】一个已经存在的容器
docker restart my-nginx           # 【重启】容器
docker stop my-nginx              # 【停止运行】一个容器
docker kill my-nginx              # 【杀死】一个运行中的容器
docker rename my-nginx new-nginx  # 【重命名】容器
docker rm new-nginx               # 【删除】容器
```

### 进入容器

[](https://github.com/jaywcjlove/docker-tutorial#%E8%BF%9B%E5%85%A5%E5%AE%B9%E5%99%A8)

1. 创建一个守护状态的 Docker 容器

```shell
docker run -itd my-nginx /bin/bash
```

2. 使用`docker ps`查看到该容器信息

```shell
docker ps
# CONTAINER ID  IMAGE  COMMAND      CREATED          STATUS          PORTS    NAMES
# 6bd0496da64f  nginx  "/bin/bash"  20 seconds ago   Up 18 seconds   80/tcp   high_shirley
```

3. 使用`docker exec`命令进入一个已经在运行的容器

```shell
docker exec -it 6bd0496da64f /bin/bash
```

通常有下面几种方式进入Docker的容器，推荐使用 `exec`，使用 `attach` 一直进入失败。

- 使用`docker attach`
- 使用`SSH` [为什么不需要在 Docker 容器中运行 sshd](http://www.oschina.net/translate/why-you-dont-need-to-run-sshd-in-docker?cmp)
- 使用`nsenter`进入Docker容器，[nsenter官方仓库](https://github.com/jpetazzo/nsenter)
- 使用`docker exec`，在`1.3.*`之后提供了一个新的命令`exec`用于进入容器

## 文件拷贝

[](https://github.com/jaywcjlove/docker-tutorial#%E6%96%87%E4%BB%B6%E6%8B%B7%E8%B4%9D)

从主机复制到容器 `sudo docker cp host_path containerID:container_path`  
从容器复制到主机 `sudo docker cp containerID:container_path host_path`

## Docker私有仓库搭建

[](https://github.com/jaywcjlove/docker-tutorial#docker%E7%A7%81%E6%9C%89%E4%BB%93%E5%BA%93%E6%90%AD%E5%BB%BA)

通过官方提供的私有仓库镜像`registry`来搭建私有仓库。通过 [humpback](https://humpback.github.io/) 快速搭建轻量级的Docker容器云管理平台。关于仓库配置说明请参见[configuration.md](https://github.com/docker/distribution/blob/master/docs/configuration.md)

> ⚠️ 注意：也可以通过部署管理工具 `Harbor` 来部署 `registry`

除了 [Harbor](https://github.com/goharbor/harbor) 还有 [humpback](https://github.com/humpback/humpback) 和 [rancher](https://github.com/rancher/rancher)

### `registry`

[](https://github.com/jaywcjlove/docker-tutorial#registry)

```shell
docker pull registry:2.6.2
```

创建容器并运行，创建成功之后，可访问 `http://192.168.99.100:7000/v2/`，来检查仓库是否正常运行，当返回 `{}` 时，表示部署成功。

```shell
docker run -d \
  -p 5000:5000 \
  --restart=always \
  --name registry \
  registry:2

# 自定义存储位置
docker run -d \
  -p 5000:5000 \
  --restart=always \
  --name registry \
  -v $HOME/_docker/registry:/var/lib/registry \
  registry:2

docker run -d -p 5000:5000 --restart=always --name registry \
    -v `pwd`/config.yml:/etc/docker/registry/config.yml \
    registry:2
```

推送镜像到私有仓库

```shell
# 从官方仓库拉取一个镜像
docker pull nginx:1.13
# 为镜像 `nginx:1.13` 创建一个新标签 `192.168.31.69:7000/test-nginx:1.13`
docker tag nginx:latest 192.168.31.69:5000/test-nginx:1.13
# 推送到私有仓库中
docker push 192.168.31.69:5000/test-nginx:1.13
# The push refers to a repository [192.168.99.100:7000/test-nginx]
# Get https://192.168.99.100:7000/v1/_ping: http: server gave HTTP response to HTTPS client
```

在推送到的时候报错误，默认是使用 `https` 提交，这个搭建的默认使用的是 `http`，解决方法两个：

1. 创建一个 `https` 映射
2. 将仓库地址加入到不安全的仓库列表中

我们使用第二种方法，加入到不安全的仓库列表中，修改docker配置文件 `vi /etc/docker/daemon.json` 添加 `insecure-registries` 配置信息，如果 [daemon.json](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-configuration-file) 文件不存在可以创建，关键配置项，将仓库将入到不安全的仓库列表中。

```js
{
  "insecure-registries":[
    "192.168.31.69:5000"
  ]
}
```

> 如果是 macOS 可以通过 docker 客户端，`Preferences` => `Advanced` => `添加配置` => `Apply & Restart`，重启docker就可以了。

重启服务 `service docker restart`，默认情况下 push 是会报如下错误的：

```shell
docker push 192.168.99.100:7000/test-nginx:1.13
# The push refers to a repository [192.168.99.100:7000/test-nginx]
# a1a53f8d99b5: Retrying in 1 second
# ...
# received unexpected HTTP status: 500 Internal Server Error
```

上面错误是 `SELinux` 强制访问控制安全系统，阻止导致的错误，通过下面方法禁用 SELinux 之后就可以 push 了。

```shell
setenforce 0  
getenforce   
# Permissive  
```

```shell
# 停止本地 registry
docker container stop registry
# 要删除容器，请使用 docker container rm
docker container stop registry && docker container rm -v registry
# 自定义存储位置
```

### `Harbor`

[](https://github.com/jaywcjlove/docker-tutorial#harbor)

[部署 registry 管理工具 Harbor](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/harbor.md)

## Docker REST API

[](https://github.com/jaywcjlove/docker-tutorial#docker-rest-api)

`Docker` 不仅可以通过本地命令行 `docker` 命令进行调用，还可以通过开启远程控制 `API`，使用 `HTTP` 调用接口来进行访问，远程控制 `Docker Daemon` 来做很多操作。`Docker` 的远程 `API` 服务默认监听的是 TCP `2375` 端口，为了保证安全，Docker 安装后默认不会启用远程 `API` 服务，因为这个服务默认不做权限认证。

### CentOS

[](https://github.com/jaywcjlove/docker-tutorial#centos)

CentOS 的开启方法比较简单，先修改配置：

```shell
vim /usr/lib/systemd/system/docker.service

# 修改 `ExecStart` 配置项，默认如下：
ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

# 增加一个 `-H tcp://0.0.0.0:2375` 选项
ExecStart=/usr/bin/dockerd -H fd:// -H tcp://0.0.0.0:2375 --containerd=/run/containerd/containerd.sock
```

如果是内网生产环境，也可以将 `0.0.0.0` 改为内网 IP。同样的，`2375` 端口也可以修改。但是这样可能还有一个问题，无法在命令行使用 `docker` 命令了，还需要添加 `sock` 选项：`-H unix:///var/run/docker.sock`，最后为：

```shell
ExecStart=/usr/bin/dockerd -H fd:// -H unix:///var/run/docker.sock -H tcp://10.105.3.115:2375 --containerd=/run/containerd/containerd.sock
```

修改完配置之后需要重启 Docker 服务：

```shell
systemctl daemon-reload
systemctl restart docker
sudo service docker restart
```

重启完成后，可以使用 netstat 查看端口是否监听来确认是否成功：

```shell
[root@VM-3-115-centos ~]# netstat -nutlp | grep 2375
tcp   0   0 10.105.3.115:2375   0.0.0.0:*     LISTEN    32316/dockerd
```

### MacOS

[](https://github.com/jaywcjlove/docker-tutorial#macos)

在 Mac 下无法直接修改配置文件来开启远程 API 服务，后来在 [`docker/for-mac`](https://github.com/docker/for-mac) 的 [`issue`](https://github.com/docker/for-mac/issues/770) 中得到了解决方案。

可以运行一个 [`bobrik/socat`](https://hub.docker.com/r/bobrik/socat) 容器，将 `unix socket` 上的 Docker API 转发到 MacOS 上指定的端口中：

```shell
docker run -d -v /var/run/docker.sock:/var/run/docker.sock -p 127.0.0.1:2375:2375 bobrik/socat TCP-LISTEN:2375,fork UNIX-CONNECT:/var/run/docker.sock
```

### 测试

[](https://github.com/jaywcjlove/docker-tutorial#%E6%B5%8B%E8%AF%95)

启用成功后，可以进行一些测试，例如直接使用浏览器访问 info 和 version 等页面获取信息。

```shell
http://127.0.0.1:2375/info
http://127.0.0.1:2375/version
```

下面可测试 docker 是否启动了

```shell
curl -s --unix-socket /var/run/docker.sock http://dummy/containers/json
## 或者使用下面命令
docker info
```

## 使用 Docker 实战

[](https://github.com/jaywcjlove/docker-tutorial#%E4%BD%BF%E7%94%A8-docker-%E5%AE%9E%E6%88%98)

> ⚠文件挂载注意：docker 禁止用主机上不存在的文件挂载到 container 中已经存在的文件

```shell
-d, --detach=false      # 指定容器运行于前台还是后台，默认为false   
-i, --interactive=false # 打开STDIN，用于控制台交互  
-t, --tty=false         # 分配tty设备，该可以支持终端登录，默认为false  
-u, --user=""           # 指定容器的用户  
-a, --attach=[]         # 登录容器（必须是以docker run -d启动的容器）
-w, --workdir=""        # 指定容器的工作目录 
-c, --cpu-shares=0      # 设置容器CPU权重，在CPU共享场景使用  
-e, --env=[]            # 指定环境变量，容器中可以使用该环境变量  
-m, --memory=""         # 指定容器的内存上限  
-P, --publish-all=false # 指定容器暴露的端口  
-p, --publish=[]        # 指定容器暴露的端口 
-h, --hostname=""       # 指定容器的主机名  
-v, --volume=[]         # 给容器挂载存储卷，挂载到容器的某个目录  
--volumes-from=[]       # 给容器挂载其他容器上的卷，挂载到容器的某个目录
--cap-add=[]            # 添加权限，权限清单详见：http://linux.die.net/man/7/capabilities  
--cap-drop=[]           # 删除权限，权限清单详见：http://linux.die.net/man/7/capabilities  
--cidfile=""            # 运行容器后，在指定文件中写入容器PID值，一种典型的监控系统用法  
--cpuset=""             # 设置容器可以使用哪些CPU，此参数可以用来容器独占CPU  
--device=[]             # 添加主机设备给容器，相当于设备直通  
--dns=[]                # 指定容器的dns服务器  
--dns-search=[]         # 指定容器的dns搜索域名，写入到容器的/etc/resolv.conf文件  
--entrypoint=""         # 覆盖image的入口点  
--env-file=[]           # 指定环境变量文件，文件格式为每行一个环境变量  
--expose=[]             # 指定容器暴露的端口，即修改镜像的暴露端口  
--link=[]               # 指定容器间的关联，使用其他容器的IP、env等信息  
--lxc-conf=[]           # 指定容器的配置文件，只有在指定--exec-driver=lxc时使用  
--name=""               # 指定容器名字，后续可以通过名字进行容器管理，links特性需要使用名字  
--net="bridge"          # 容器网络设置:
                            # bridge 使用docker daemon指定的网桥     
                            # host 	//容器使用主机的网络  
                            # container:NAME_or_ID  >//使用其他容器的网路，共享IP和PORT等网络资源  
                            # none 容器使用自己的网络（类似--net=bridge），但是不进行配置 
--privileged=false      # 指定容器是否为特权容器，特权容器拥有所有的capabilities  
--restart="no"          # 指定容器停止后的重启策略:
                            # no：容器退出时不重启  
                            # on-failure：容器故障退出（返回值非零）时重启 
                            # always：容器退出时总是重启  
--rm=false              # 指定容器停止后自动删除容器(不支持以docker run -d启动的容器)  
--sig-proxy=true        # 设置由代理接受并处理信号，但是SIGCHLD、SIGSTOP和SIGKILL不能被代理
```

### `Nginx`

[](https://github.com/jaywcjlove/docker-tutorial#nginx)

[在 docker 中部署 Nginx](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/nginx.md)

### `MySQL`

[](https://github.com/jaywcjlove/docker-tutorial#mysql)

[在 docker 中部署 MySQL](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/mysql.md)

### `PostgreSQL`

[](https://github.com/jaywcjlove/docker-tutorial#postgresql)

[在 docker 中部署 PostgreSQL](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/postgres.md)

### `Redis`

[](https://github.com/jaywcjlove/docker-tutorial#redis)

[在 docker 中部署 Redis](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/redis.md)

### `Elasticsearch`

[](https://github.com/jaywcjlove/docker-tutorial#elasticsearch)

[在 docker 中部署 Elasticsearch](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/elasticsearch.md)

### `Gitlab`

[](https://github.com/jaywcjlove/docker-tutorial#gitlab)

[在 docker 中部署 Gitlab](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/gitlab/README.md)

### `Rocket.Chat`

[](https://github.com/jaywcjlove/docker-tutorial#rocketchat)

[在 docker 中部署 Gitlab](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/rocket.chat/README.md)

### `Rancher`

[](https://github.com/jaywcjlove/docker-tutorial#rancher)

[在 docker 中部署 Rancher](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/rancher.md)

### `Portainer`

[](https://github.com/jaywcjlove/docker-tutorial#portainer)

[在 docker 中部署 Portainer](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/portainer.md)

### `Sourcegraph`

[](https://github.com/jaywcjlove/docker-tutorial#sourcegraph)

[在 docker 中部署 Sourcegraph](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/sourcegraph/README.md)

### `Mattermost`

[](https://github.com/jaywcjlove/docker-tutorial#mattermost)

[在 docker 中部署 Mattermost](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/mattermost.md)

### `SeaweedFS`

[](https://github.com/jaywcjlove/docker-tutorial#seaweedfs)

[在 docker 中部署 SeaweedFS](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/seaweedfs/README.md)

### `NPS`

[](https://github.com/jaywcjlove/docker-tutorial#nps)

[在 docker 中搭建内网穿透服务器，带WEB管理](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/nps/README.md)

### `Penpot`

[](https://github.com/jaywcjlove/docker-tutorial#penpot)

[在 docker 中部署 Penpot](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/penpot.md)

### `Navidrome`

[](https://github.com/jaywcjlove/docker-tutorial#navidrome)

[在 docker 中部署 Navidrome](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/navidrome.md)

### `Jenkins`

[](https://github.com/jaywcjlove/docker-tutorial#jenkins)

[在 docker 中部署 Jenkins](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs/jenkins/README.md)

### `Humpback`

[](https://github.com/jaywcjlove/docker-tutorial#humpback)

首先创建放持久化数据文件夹，`mkdir -p /opt/app/humpback-web`，里面存放持久化数据文件，会存储站点管理和分组信息，启动后请妥善保存。

```shell
# 创建放持久化数据文件夹
mkdir -p /opt/app/humpback-web
# 下载humpback-web镜像到本地
docker pull humpbacks/humpback-web:1.0.0
# 启动 humpback-web 容器，将容器命名为 humpback-web
docker run -d --net=host --restart=always \
 -e HUMPBACK_LISTEN_PORT=7001 \
 -v /opt/app/humpback-web/dbFiles:/humpback-web/dbFiles \
 --name humpback-web \
 humpbacks/humpback-web:1.0.0
```

访问站点，打开浏览器输入：[http://192.168.99.100:7001](http://192.168.99.100:7001/) ，默认账户：`admin` 密码：`123456`

### `Seafile`

[](https://github.com/jaywcjlove/docker-tutorial#seafile)

```shell
docker run -d --name seafile \
  -e SEAFILE_SERVER_HOSTNAME=seafile.example.com \
  -v /opt/seafile-data:/shared \
  -p 80:80 \
  seafileltd/seafile:latest
```

```shell
docker run -d --name seafile \
  -e SEAFILE_SERVER_HOSTNAME=pan.example.com \
  -e SEAFILE_ADMIN_EMAIL=wcj@example.com \
  -e SEAFILE_ADMIN_PASSWORD=wcj@example.com \
  -v $HOME/_docker/seafile-data:/shared \
  -p 80:80 \
  seafileltd/seafile:latest
```

### 更多

[](https://github.com/jaywcjlove/docker-tutorial#%E6%9B%B4%E5%A4%9A)

[更多 docker 工具部署，在 docker 目录中](https://github.com/jaywcjlove/docker-tutorial/blob/master/docs)

## 卸载旧的版本

[](https://github.com/jaywcjlove/docker-tutorial#%E5%8D%B8%E8%BD%BD%E6%97%A7%E7%9A%84%E7%89%88%E6%9C%AC)

移除旧的版本

```shell
$ sudo yum remove docker \
  docker-client \
  docker-client-latest \
  docker-common \
  docker-latest \
  docker-latest-logrotate \
  docker-logrotate \
  docker-selinux \
  docker-engine-selinux \
  docker-engine
```

## 错误处理

[](https://github.com/jaywcjlove/docker-tutorial#%E9%94%99%E8%AF%AF%E5%A4%84%E7%90%86)

Create more free space in thin pool or use dm.min_free_space option to change behavior

> 特别慎用，东西都没有了，注意备份哦。[moby/moby#3182 (comment)](https://github.com/moby/moby/issues/3182#issuecomment-256532928)

**镜像拉不下来**

修改 Docker `daemon.json` 配置 macOS: `/etc/docker/daemon.json`，Linux: `~/.docker/daemon.json`

```js
{
  "registry-mirrors":[
     "https://docker.mirrors.ustc.edu.cn",
     "https://hub-mirror.c.163.com",
     "https://mirror.baidubce.com",
     "https://registry.docker-cn.com"
  ],
  "insecure-registries": [
     "192.168.188.111:2021"
  ]
}
```

## 参考资料

[](https://github.com/jaywcjlove/docker-tutorial#%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99)

### 官方英文资源

[](https://github.com/jaywcjlove/docker-tutorial#%E5%AE%98%E6%96%B9%E8%8B%B1%E6%96%87%E8%B5%84%E6%BA%90)

- Docker官网：[http://www.docker.com](http://www.docker.com/)
- Docker windows入门：[https://docs.docker.com/windows/](https://docs.docker.com/windows/)
- Docker Linux 入门：[https://docs.docker.com/linux/](https://docs.docker.com/linux/)
- Docker mac 入门：[https://docs.docker.com/mac/](https://docs.docker.com/mac/)
- Docker 用户指引：[https://docs.docker.com/engine/userguide/](https://docs.docker.com/engine/userguide/)
- Docker 官方博客：[http://blog.docker.com/](http://blog.docker.com/)
- Docker Hub: [https://hub.docker.com/](https://hub.docker.com/)
- Docker开源： [https://www.docker.com/open-source](https://www.docker.com/open-source)

### 中文资源

[](https://github.com/jaywcjlove/docker-tutorial#%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90)

- Docker中文网站：[http://www.docker.org.cn](http://www.docker.org.cn/)
- Docker中文文档：[http://www.dockerinfo.net/document](http://www.dockerinfo.net/document)
- Docker安装手册：[http://www.docker.org.cn/book/install.html](http://www.docker.org.cn/book/install.html)
- 一小时Docker教程 ：[https://blog.csphere.cn/archives/22](https://blog.csphere.cn/archives/22)
- Docker中文指南：[http://www.widuu.com/chinese_docker/index.html](http://www.widuu.com/chinese_docker/index.html)

### 其它资源

[](https://github.com/jaywcjlove/docker-tutorial#%E5%85%B6%E5%AE%83%E8%B5%84%E6%BA%90)

- [Docker 参考清单！](https://jaywcjlove.github.io/reference/docs/docker.html)
- [Docker 快速手册！](https://github.com/eon01/DockerCheatSheet)
- [Docker 教程](http://www.runoob.com/docker/docker-tutorial.html)
- [Docker 从入门到实践](https://www.gitbook.com/book/yeasy/docker_practice)
- [MySQL Docker 单一机器上如何配置自动备份](http://blog.csdn.net/zhangchao19890805/article/details/52756865)
- [使用Docker Compose管理多个容器](http://dockone.io/article/834)
- [https://segmentfault.com/t/docker](https://segmentfault.com/t/docker)
- [https://github.com/docker/docker](https://github.com/docker/docker)
- [https://wiki.openstack.org/wiki/Docker](https://wiki.openstack.org/wiki/Docker)
- [https://wiki.archlinux.org/index.php/Docker](https://wiki.archlinux.org/index.php/Docker)
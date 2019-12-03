# 深入系统 docker 学习

## 安装

### macos 安装 docker

- 使用 Homebrew 安装
  ```
    brew -v
    sudo brew update
    brew cask install update
  ```

* 手动下载安装
  官网下载即可`https://docs.docker.com/docker-for-mac/install/`

### centos 安装 docker

- 搭建 centos 虚拟机
  - 下载`virtualbox`, 地址`https://www.virtualbox.org/wiki/Downloads`
  * 下载`vagrant`, 地址`https://www.vagrantup.com/downloads.html`

* 基于 vagrant 构建

  ```
    vagrant init centos/7
    vagrant up
    vagrant ssh
    sudo yum update
    exit
    vagrant status
    vagrant halt
    vagrant destroy
  ```

* 在 centos 上安装 docker

  ```
    $ sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine

    $ sudo yum install -y yum-utils device-mapper-persistent-data lvm2

    $ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

    $ sudo yum install docker-ce docker-ce-cli containerd.io

    $ sudo systemctl start docker

    $ sudo docker run hello-world

  ```

## docker machine

- 使用 docker-machine 创建 virtualbox 虚拟机

  ```
    docker-machine version
    docker-machine create demo
    docker-machine ls
    docker-machine ssh demo
    docker-machine stop demo
    docker-machine env demo
    eval $(docker-machine env demo)
  ```

- 让 docker-machine 和阿里云搞 cp
  参考`https://github.com/AliyunContainerService/docker-machine-driver-aliyunecs`

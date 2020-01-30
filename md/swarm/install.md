# 安装Docker服务


CentOS7 安装docker
=======================

一般服务器在内网，机房网络已经有防火墙，可关闭服务器防火墙,不关闭需要开放节点端口。
```
# 关闭防火墙
systemctl disable firewalld
systemctl stop firewalld
```

Docker安装脚本
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
sudo yum-config-manager --add-repo  https://download.docker.com/linux/centos/docker-ce.repo  
sudo yum install -y docker-ce-19.03.5
sudo systemctl enable docker

#设置阿里云镜像仓库
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://62oh6osg.mirror.aliyuncs.com"],
  "graph":"/docker",
  "log-driver":"json-file",
  "log-opts":{ "max-size":"50m" }
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
------------------------------------------------------------------

卸载旧版本
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-selinux \
                  docker-engine-selinux \
                  docker-engine

yum管理工具
sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
  
yum源配置  
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo  

sudo yum-config-manager --add-repo https://mirrors.aliyun.com/repo/Centos-7.repo

安装
sudo yum install docker-ce

列出可选版本
yum list docker-ce --showduplicates | sort -r


sudo yum install docker-ce-<VERSION STRING>
sudo systemctl start docker

卸载
sudo yum remove docker-ce
```


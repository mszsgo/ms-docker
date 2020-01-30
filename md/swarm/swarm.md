# 配置Swarm集群

配置前请检查所有同网络中节点docker服务是否安装完成并关闭防火墙。

## 集群创建 
```
* 创建集群节点
docker swarm init --advertise-addr 172.17.193.184
* 新增集群节点
docker swarm join --advertise-addr 172.17.193.185 --token <token，从主节点获取> 172.17.193.184:2377
* 创建集群网络
在master节点创建自定义集群overlay网络：（只需要在master节点创建，worker节点会自动创建）
docker network create --attachable --driver overlay --subnet 10.11.0.0/16 cluster

```

## 集群管理




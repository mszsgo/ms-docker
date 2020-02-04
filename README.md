# ms-docker

Docker服务. 



# 配置中心
  config:
    image: "mszs/config"
    networks: [stack]
    deploy:
      mode: replicated
      replicas: 1
  # 服务网关
  gateway:
    image: "mszs/gateway"
    networks: [stack]
    deploy:
      mode: replicated
      replicas: 1
    depends_on: [config]

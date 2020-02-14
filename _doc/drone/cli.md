
```shell script
# Drone Cli
# export DRONE_SERVER=http://172.17.193.184:3080
# export DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E
drone info
docker run -e DRONE_SERVER=http://172.17.193.184:3080 -e DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E --rm -it drone/cli info
docker run -e DRONE_SERVER=http://172.17.193.184:3080 -e DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E --rm -it drone/cli orgsecret add zengs sshhost 172.17.193.184
docker run -e DRONE_SERVER=http://172.17.193.184:3080 -e DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E --rm -it drone/cli orgsecret add zengs sshport 22
docker run -e DRONE_SERVER=http://172.17.193.184:3080 -e DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E --rm -it drone/cli orgsecret add zengs sshname root
docker run -e DRONE_SERVER=http://172.17.193.184:3080 -e DRONE_TOKEN=UXsqjDqcoyooDtk9mc1qvZfUEerL4P2E --rm -it drone/cli orgsecret add zengs sshpass root

```

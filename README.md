# prometheus
动态实现监控系统，通过docker-compose 实现 

# docker-compose cp to /usr/local/bin

curl https://github.com/guozh10/nfs/blob/main/bin/docker-compose -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose 


# consul prometheus 使用官方镜像实现简化部署，方便同学们学习和使用


# 后台启动

docker-compose up -d

# 查看日志

docker-compose logs -f

# 注册consul 
```
cat data.json

{

"id": "192.168.10.20",
"name": "node-exporter",
"address": "192.168.10.20",
"port": 29100,
"tags": ["base","kvm",],

"Meta":{
"env":"base",
"group":"base"},

"checks": [

{"http": "http://192.168.100.20:29100/metrics",

"interval": "20s"}

]

}

curl  -X PUT  http://localhost:8500/v1/agent/service/register --data @data.json

```

# 注销consul

curl  -X PUT  http://localhost:8500/v1/agent/service/deregister/192.168.100.20

# 安装node-exporter
   

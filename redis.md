# 在docker desktop中安装redis

``` Shell
docker pull redis
docker run -d `
 -p 6379:6379 `
 -v c:/programdata/docker.mount/redis/config:/usr/local/etc/redis `
 -v c:/programdata/docker.mount/redis/data:/data `
 --name redis `
 redis:latest `
 redis-server /usr/local/etc/redis/redis.conf `
 --appendonly yes
```

|参数|说明|
|-|-|
|-d|后台模式启动redis
|-p 6379:6379|容器redis端口6379映射宿主主机6379
|-v c:/programdata/docker.mount/redis/config/redis.conf:/usr/local/etc/redis/redis.conf|挂载路径,将右边容器内部路径挂载到本地d:/docker.mount/...
|-v c:/programdata/docker.mount/redis/data:/data|同上,可以使用$PWD表示当前路径:$PWD/data:/data
|--name redis|容器名字为redis
|redis:latest|使用镜像:redis:latest
|redis-server /usr/local/etc/redis/redis.conf|redis将以此配置文件启动
|--appendonly yes|开启redis的AOF持久化，默认为false，不持久化
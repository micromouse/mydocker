# 在docker desktop中安装mysql
``` Shell
docker pull mysql
docker run -d `
--name mysql `
-p 3306:3306 `
-v c:/programdata/docker.mount/mysql/config:/etc/mysql/conf.d `
-v c:/programdata/docker.mount/mysql/data:/var/lib/mysql `
-v c:/programdata/docker.mount/mysql/log:/var/log/mysql `
-e MYSQL_ROOT_PASSWORD=mysql123! `
mysql:latest
```

|参数|说明|
|-|-|
|-d|后台模式启动mysql
|--name redis|容器名字为redis
|-p 6379:6379|容器mysql端口3306映射宿主主机3306
|-v c:/programdata/docker.mount/mysql/config:/etc/mysql/conf.d|挂载路径,将右边容器内部路径挂载到本地c:/programdata/docker.mount/...
|-e MYSQL_ROOT_PASSWORD|初始化root用户的密码
|mysql:latest|使用镜像:mysql:latest

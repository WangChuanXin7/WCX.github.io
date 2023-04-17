# Ubuntu安装docker
## 第一种安装方式
 
<!-- 菜鸟教程 -->
···
 curl -fsSL https://test.docker.com -o test-docker.sh
 sudo sh test-docker.sh
···

### 第二种安装方式

···
sudo apt-get install update # 更新下载镜像
sudo apt-get install docker.in #安装docker
···
## 可能会遇到containered 依赖错误信息

···
sudo apt-get install containered #安装前置依赖
sudo apt-get install
···
### docker切换镜像源


创建或修改 /etc/docker/daemon.json 文件，修改：

```
cd /etc/docker
vim daemon.json
```

加入如下配置：

```
{
    "registry-mirrors" :[
        "https://registry.docker-cn.com"
        "http://hub-mirror.c.163.com"
        "https://docker.mirrors.ustc.edu.cn"
        "https://cr.console.aliyun.com"
        "https://mirror.ccs.tencentyun.com"
    ]
}
```
重启docker服务使配置生效：


```
systemctl daemon-reload

systemctl restart docker.service
```

查看配置是否成功：

```
docker info
```

## docker安装tomcat

```
sudo docker pull tomcat #等待下载安装
```
### 启动tomcat
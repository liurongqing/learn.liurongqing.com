# 安装 MongoDB 社区版

按照以下步骤使用 apt-get 包管理器安装 MongoDB Community Edition。

# 导入管理系统使用的公钥

```bash
# 显示 ok 即成功
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
```

# 为 MongoDB 创建一个列表文件

```bash
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
```

# 重新加载本地包数据库

```bash
sudo apt-get update
```

# 安装 MongoDB 包

```bash
sudo apt-get install -y mongodb-org
```




创建文件 `/etc/yum.repos.d/mongodb-org-5.0.repo`  
```bash
[mongodb-org-5.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/5.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-5.0.asc
```

# 安装 MongoDB 包

安装 MongoDB 的最新稳定版本，使用以下命令
```bash
# 以下命令有可能会触发 - 常见问题1 常见问题2
sudo yum install -y mongodb-org
```

# 常见问题

1. 错误：Invalid configuration value: failovermethod=priority in /etc/yum.repos.d/CentOS-Epel.repo; 配置：ID 为 "failovermethod" 的 OptionBinding 不存在 

解决：  
编辑 `vi /etc/yum.repos.d/CentOS-Epel.repo` 文件，注释掉 failovermethod=priority

2. 错误：为仓库 'appstream' 下载元数据失败 : Cannot prepare internal mirrorlist: No URLs in mirrorlist

解决方法：
1. https://developer.aliyun.com/mirror/centos (我试了无效)
2. https://blog.51cto.com/u_15522232/5129674
    ```bash
    baseurl=https://mirrors.aliyun.com/centos/$releasever-stream/extras/$basearch/os/
    ```
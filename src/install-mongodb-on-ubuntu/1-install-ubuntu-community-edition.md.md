![logo](./images/install.png)

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
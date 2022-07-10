![logo](./images/start.png)

# 运行 MongoDB 社区版

默认文件路径  
日志：/var/log/mongodb
数据：/var/lib/mongodb

# 启动 MongoDB

```bash
sudo systemctl start mongod
```
# 验证 MongoDB 是否成功启动

```bash
# 查看是否成功启动
sudo systemctl status mongod

# 加入开机自启动
sudo systemctl enable mongod
```

# 停止 MongoDB

```bash
sudo systemctl stop mongod
```

# 重新启动 MongoDB

```bash
# 日志：/var/log/mongodb/mongod.log
sudo systemctl restart mongod
```

# 开始使用 Mongodb

```bash
mongodsh
```
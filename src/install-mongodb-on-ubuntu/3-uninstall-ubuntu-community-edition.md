![logo](./images/clean.png)

# 卸载 MongoDB 社区版

完全删除 MongoDB 配置、数据

# 停止 MongoDB

```bash
sudo service mongod stop
```

# 移除包

```bash
sudo apt-get purge mongodb-org*
```

# 删除数据目录

```bash
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongodb
```
### redis

**redis安装**：

- redis只有linux系统的版本

1. 将.tar.gz文件复制到linux电脑上

2. gcc --version（确保有C语言的运行环境，centos可使用yum install gcc来安装）

3. tar -zxvf redis-6.2.6.tar.gz

4. cd redis-6.2.6

5. make（编译成C语言）

6. make install（安装）

7. cp redis.conf /etc（复制redis.conf到一个文件夹，来把其中的daemonize no 改为yes，即允许后台运行，该步骤使用vim完成，省略（查找使用的“/”））

8. 后台启动redis:redis-server /etc/redis.conf

9. 关闭：redis-cli中：shutdown

   ```shell
   ps -aux | grep redis
   kill -9 进程号
   ```
   
   ```
   39.107.25.37密码为_sun(kc)7hon^est_
   ```

**允许远程访问**：

修改redis.conf 

- bind一行注释
- protect-mode no

#### Redis设置密码

方法一：修改配置文件中requirepass的值，重启后会持久生效

方法二（不推荐）：redis-cli中操作

```shell
config set requirepass test123 # 配置密码
auth test123 # 通过权限
config get requirepass # 获取密码
```


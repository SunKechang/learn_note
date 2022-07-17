## linux登入宝塔

> 查看面板入口：/etc/init.d/bt default

## linux安装python

https://blog.csdn.net/L_15156024189/article/details/84831045

## centos安装java

https://blog.csdn.net/weixin_42018258/article/details/102805996

## centos部署springboot项目

1、现在阿里云的控制台->防火墙中开放端口（8002），再在宝塔中”安全“中放行对应端口（8002），最后按照该文章在这个端口下建立网站，并进行方向代理。

https://www.cnblogs.com/howeya/p/15055512.html

这篇文章讲得很对，只要在本地测试好了端口和访问路径即可。本人中药项目就是按照这个配置好的



> 2021/11/9更新
>
> 好像只要是在服务器上跑起来项目，阿里云上打开对应端口就可以访问了

## centos关闭后台程序

https://www.cnblogs.com/iflytek/p/10790723.html

> 1、后台运行jar包程序，输入：nohup java -jar /路径/程序.jar &
>
> 2、后台终止jar包程序，输入：ps -ef | grep java，查看使用java命令的进程，再输入：kill pid 即可终止运行
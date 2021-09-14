roscore无法启动：

终端现实为如下：

```
... logging to /home/nubot1/.ros/log/8270a90e-1525-11ec-b0be-244bfe9a4f41/roslaunch-nubot1-19418.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

RLException: Unable to contact my own server at [http://nubot1:36613/].
This usually means that the network is not configured properly.

A common cause is that the machine cannot connect to itself.  Please check
for errors by running:

	ping nubot1

For more tips, please see

	http://wiki.ros.org/ROS/NetworkSetup

The traceback for the exception was written to the log file
```

原因：

网络配置出现问题，由于电脑连接了服务器，服务器中有一个nubot1，其地址为10.0.0.1，在10.0.0.1未安装ros，因此，我连接进入服务器时，每次roscore都寻找了服务器中的10.0.0.1。

解决方案：

```
echo 127.0.1.1 nubot1 >> /etc/hosts

echo export ROS_HOSTNAME=nubot1 >> ~/.bashrc
echo export ROS_MASTER_URI=http://nubot1:11311 >> ~/.bashrc

```

其中，nubot1是电脑用户名。

其实解决方案的核心思想就在于将ROS_HOSTNAME链接到本电脑，ROS_MASTER_URI用来声明11311的端口号即可。127.0.1.1必然是在本地的，也可以用其他固定的ip（譬如我在有线局域网的ip 10.0.1.155， 我在无线局域网的ip  192.168.43.163），都可以用来代替nubot1.

参考网站：

https://blog.csdn.net/weixin_41848012/article/details/102629709

https://answers.ros.org/question/249271/roslaunch-unable-to-contact-my-own-server/
 问题1：编译nubot_common时报错：No module named em

解决办法：

pip uninstall em

pip install empy

问题2：

 fatal error: nubot_hwcontroller/DebugInfo.h: No such file or directory
 #include "nubot_hwcontroller/DebugInfo.h"

注释掉这一行

问题3：

关于gazebo的math报错

关于rosdep init失效：

```
sudo gedit /etc/hosts
# just for rosdep init
151.101.84.133 raw.githubusercontent.com
```

问题4 关于gazebo与ros相关package找不到

因为anaconda启动将python链接到conda环境中，ros找不到对应依赖文件，可以将bashrc中的conda相关语句进行屏蔽，但是这是临时解决办法，后续需要进一步处理。

问题5：

gregorian_calendar.ipp: 时间包的问题：
QTcreator 官网下载地址，选择对应版本即可，以5.12.10为例：

http://download.qt.io/archive/qt/

下载的文件为[qt-opensource-linux-x64-5.12.10.run](http://download.qt.io/archive/qt/5.12/5.12.10/qt-opensource-linux-x64-5.12.10.run)

1. run文件安装常规操作，cd到run文件所在目录，赋予可执行权限：

   ```
   sudo chmod +x qt-opensource-linux-x64-5.12.10.run
   ```

2. 以root权限运行文件，进行安装：

   ```
   sudo ./qt-opensource-linux-x64-5.12.10.run
   ```

3. 配置qtchooser 环境变量文件 default.conf;第一行改为bin目录的路径，第二行改为qt5.12.10目录的路径。

4. Qt卸载，找到qtcreator安装位置，运行

   ```
   sudo ./MaintenanceTool
   ```

二、qtcreator-ros plugin官方教程

https://ros-qtc-plugin.readthedocs.io/en/latest/_source/How-to-Install-Users.html


zotero 安装与迁移：

zotero从一台电脑复制到其他电脑的话，需要对应的storage文件和zotero.sqlite文件，其位置一般为home下的zotero文件夹内

zotero下载：

官网链接：https://www.zotero.org/downloads

在压缩包所在目录运行命令：

解压文件：

tar jxvf Zotero-5.0.93_linux-x86_64.tar.bz2 Zotero_linux-x86_64/

复制文件至/opt/

sudo cp -r Zotero_linux-x86_64/ /opt/

cd /opt/Zotero_linux-x86_64

赋予可执行权限：

sudo chmod +x zotero zotero-bin set_launcher_icon

运行安装代码：

sudo ./set_launcher_icon

./zotero

向启动器件添加快捷方式：

快捷方式是存储在/usr/share/applications/下的，将zotero目录下的zotero.desktop复制到该目录下，以管理员权限编辑:

```
[Desktop Entry]
Name=Zotero
Exec=bash -c "/opt/Zotero_linux-x86_64/zotero -url %U"
Icon=/opt/Zotero_linux-x86_64/chrome/icons/default/default256.png
Type=Application
Terminal=false
Categories=Office;
MimeType=text/plain      
```

​         
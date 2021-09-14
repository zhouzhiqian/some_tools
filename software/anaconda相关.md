**anaconda 安装：**
下载对应的Anaconda文件，譬如：Anaconda3-2020.02-Linux-x86_64.sh 
赋予文件可执行权限：
```
sudo chmod +x Anaconda3-2020.02-Linux-x86_64.sh
```
**进入安装过程：**
```
./Anaconda3-2020.02-Linux-x86_64.sh
```
安装过程中，不断回车、输入yes即可，相关操作包括是否同意许可证内容，是否使用默认文件安装位置，最后，会有一个关于conda init的配置，建议选yes，如果选择no，conda的环境配置不会添加到bashrc之中。
这也就意味着，没办法直接通过命令行启动conda相关命令，包括创建环境等等
也就是在~/.bashrc最后添加
```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/fetch/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/fetch/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/home/fetch/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/fetch/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```
而后，将自动激活conda base环境配置为否，否则每次启动命令行都会进入conda_base环境
```
conda config --set auto_activate_base false
```
需要注意的是，默认安装文件位置为home下的anaconda.

**conda换源**
更换为清华源：
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
```
更换为中科大源：
```
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
```
上述配置写在 ~/.condarc 之中，通过gedit或者vim均可以查看
其中defaults为默认源位置，往往网速会慢一些

**anaconda使用：**
创建环境：
```
conda create --name human_detect python=3.6
```
name与python分别指定conda环境名，以及python版本。

启动环境：
```
conda activate human_detect
```
退出环境：
```
conda deactivate human_detect
```

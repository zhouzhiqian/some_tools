方法一：
安装完ros与anaconda 之后，anaconda3 默认的python为python3，而很多的ros需求为python2.7,因此可以考虑特意建立新的专门为ros服务的conda环境
conda create -n ros_env python=2.7 anaconda
每次启动ros时，通过ros_env启动，当然也可以将它添加到bashrc之中，但是这样可能会影响其他工程

方法二：
屏蔽掉.bashrc中关于anaconda的设置，即

```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/“user”/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/"user"/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/home/"user"/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/"user"/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```

每次使用anaconda时，在终端中输入

```
$ export PATH="/home/"user"/anaconda3/bin:$PATH"
```

这也是ros在github上提出的方法

方法三：

与方法二类似，但是在bashrc中声明一条命令，用于替代export PATH

```
alias condaenv=”export PATH=”/home/"user"/anaconda3/bin:$PATH””
```

每次运行可以通过condaenv启动conda环境。
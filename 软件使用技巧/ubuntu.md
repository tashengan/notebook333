# 1.指令

##### （1）更新软件包

```
sudo apt-get update
```

##### （2）深度学习环境激活

```
source ~/miniconda3/bin/activate
conda activate yolo
```

##### （3）进入到指定文件夹下

相对路径:

```
cd ~/opt/...
```

绝对路径：

先查看文件的详细信息，复制路径

```
cd 路径
```

##### （4）系统环境软件安装

```
sudo apt-get install ....
```

卸载

```
sudo apt-get uninstall
```

##### （5）requirement安装

首先进入到项目文件目录下

然后：

```
pip3 install -r opt/reqirements.txt
```

##### （6）解压

```
tar -xvf cudnn-linux-xxx.tar.xz
```

##### （7）软件移动到opt文件夹

```
sudo mv pycharm-community-2020.2.3/ /opt/
```

##### （8）执行.sh文件

```
chmod +x helloworld.sh
```

##### （9）使用清华源pip安装加速

```
 pip install 库名 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

##### （10）whl文件

whl格式本质上是一个压缩包，里面包含了py文件，以及经过编译的pyd文件。使得可以在不具备编译环境的情况下，选择合适自己的[python](https://so.csdn.net/so/search?q=python&spm=1001.2101.3001.7020)环境进行安装。

```
pip install xxxx.whl
```



# 2.快捷键

##### （1）显示隐藏项目

```
control+H
```

##### （2）自动补全指令

```
Tab
```

##### （3）显示上次运行的代码

```
↑
```

##### （4）复制粘贴

```
control+shift+C
control+shift+V
```

##### （5）强制退出

```
control+C
control+Z
```

##### （6）查看当前目录下的文件夹和文件

```
ls
ls -l  #显示内容的详细列表
```

##### （7）清理终端内容

```
clear
```

### 3.基础知识

##### （1）根目录

Linx的根目录就是“/”

```
cd /   #进入根目录
```

##### （2）家目录

```
cd ~
```

家目录的绝对路径为：

```
/home/用户名/
```

##### （3）点

```
..代表上级目录
.代表当前目录
cd ..    #返回上级目录
./可执行程序      #执行当前目录下的可执行程序
```

##### （4）新建文件夹

```
mkdir test   #新建一个test文件夹
rmdir test   #删除test文件夹（空）
rm -rf test/ #强制删除文件夹
```

##### （5）sudo

super do  相当于管理员命令

谨慎使用

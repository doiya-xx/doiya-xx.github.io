# Python

官网文档，最好的学习资料

系统唯一的 python 解释器，安装包，然后各种虚拟环境都是根据基环境中的包来生成的。

安装一个 miniconda 就足够了。

## venv 虚拟环境

### 创建

python3 中自带 venv包

```shell
python -m venv ENV_DIR
```

然后就可以在pycharm中选择这个虚拟环境，记得选择关联这个环境，这样才可以在终端中链接到这个环境，而忽略系统变量中设置的默认python环境。

而在命令行想链接这个环境，则需要启动虚拟环境下的脚本

```shell
# cmd
./Script/activate.bat
# powershell
./Script/activate.ps1
# ubuntu
./Script/activate.sh
```

使用venv创建的虚拟环境无法使用conda。使用pip就好。

### 在虚拟环境中安装 jupyter notebook

> 在虚拟环境中需要安装 `pip install ipykernel` 就可以了。不需要完全安装jupyter notebook
>
> 在系统环境中安装 jupyter 和 nb_conda，然后在虚拟环境中安装 ipykernel 即可自动识别。如果没有安装 nb_conda 则需要手动设置。

```shell
pip install jupyter notebook
```

启动 jupyter notebook

```shell
# 会自动打开浏览器
jupyter notebook
```

解决在 jupyter notebook 中无法识别到虚拟环境

```shell
python -m ipykernel install --user --name=<name>
```

### 将环境写入文件，通过文件安装包

## conda

还是用conda创建虚拟环境好用

### powershell 无法链接 anaconda 的环境问题

```shell
# in powershell
conda init powershell
# restart powershell
```

但是这样会使得 powershell 一启动就进入 anaconda 的 base 环境，或者说是在命令行前面显示 base

### powershell 进入 anaconda 环境

```shell
# enter
conda activate ENV
# quit
exit
```


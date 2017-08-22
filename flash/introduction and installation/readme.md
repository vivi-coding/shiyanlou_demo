#Virtualenv 

能够允许多个不同版本的 Python 安装，每一个服务于各自的项目。 它实际上并没有安装独立的 Python 副本，只是提供了一种方式使得环境保持独立。让我们见识下 virtualenv 怎么工作的。

如果你在 Mac OS X 或 Linux下，下面两条命令可能会适用:
'''
$ sudo easy_install virtualenv
'''
此处输入图片的描述

或者更好的:
'''
$ sudo pip install -i http://mirrors.aliyuncs.com/pypi/simple virtualenv
'''
上述的命令会在你的系统中安装 virtualenv。它甚至可能会出现在包管理器中。如果你使用 Ubuntu ，请尝试:
'''
$ sudo apt-get install python-virtualenv
'''
如果是在 Windows 下并且没有安装 easy_install 命令，你首先必须安装 easy_install 。 要想获取更多的安装信息，请查看 Windows 下的 pip 和 distribute 。一旦安装好 easy_install ， 运行上述的命令，但是要去掉 sudo 前缀。

一旦成功安装 virtualenv，运行 shell 创建自己的环境。我通常会创建一个项目文件夹myproject，其下创建 venv 文件夹，该文件夹就是一个虚拟的 Python 环境:
'''
$ mkdir myproject
$ cd myproject
$ virtualenv venv
New python executable in venv/bin/python
Installing distribute............done.
'''
现在，只要你想要在某个项目上工作，只要激活相应的环境。在 OS X 和 Linux 下，按如下做:
'''
$ . venv/bin/activate
'''
如果你是个 Windows 用户，下面的命令行是为你而准备:
'''
$ venv\scripts\activate
'''
无论哪种方式，你现在能够使用你的 virtualenv (注意你的 shell 提示符显示的是活动的环境)。

现在你只需要键入以下的命令来激活你的 virtualenv 中的 flask:
'''
$ pip install -i http://mirrors.aliyuncs.com/pypi/simple flask
'''
几秒后，一切就为你准备就绪。

#全局安装

以下命令安装环境也是可行的，尽管我不推荐。只需要以 root 权限运行 pip:
'''
$ sudo pip install -i http://mirrors.aliyuncs.com/pypi/simple flask
'''
(在 Windows 系统上，在管理员权限的命令提示符中运行这条命令，不需要 sudo。)

#体验最新的 Flask (Living on the Edge)

如果你想要用最新版的 Flask 干活，这里有两种方式：你可以使用 pip 拉取开发版本， 或让它操作一个 git checkout。无论哪种方式，依然推荐使用 virtualenv。

在一个新的 virtualenv 上获取一个 git checkout，在开发模式下运行:
'''
$ git clone https://github.com/shiyanlou/flask
Initialized empty Git repository in ~/dev/flask/.git/
$ cd flask
$ virtualenv venv --distribute
New python executable in venv/bin/python
Installing distribute............done.
$ . venv/bin/activate
$ python setup.py develop
...
Finished processing dependencies for Flask
'''
这会拉取依赖关系并激活 git head 作为 virtualenv 中的当前版本。然后你只需要执行 git pull origin 来升级到最新版本。

没有 git 下获取最新的开发版本，需要这样做:
'''
$ mkdir flask
$ cd flask
$ virtualenv venv --distribute
$ . venv/bin/activate
New python executable in venv/bin/python
Installing distribute............done.
$ pip install -i http://mirrors.aliyuncs.com/pypi/simple Flask==dev
...
Finished processing dependencies for Flask==dev
'''
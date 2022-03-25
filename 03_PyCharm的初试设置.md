# PyCharm的初始设置
## 01.恢复PyCharm的初始设置
`PyCharm`的**配置信息**是保存在**用户家目录下**的`.PyCharmxxxx.x`目录下的`xxxx.x`表示当前使用的`PyCharm`的版本号
如果要恢复`PyCharm`的初试设置，可以按照以下步骤进行：
1. 关闭正在运行的`PyCharm`
2. 在终端中执行以下终端命令，删除`PyCharm`的配置信息目录：
```
$ rm ~/.PyCharm2016.3
```
3. 重新启动`PyCharm`
## 02.第一次启动PyCharm
1. 导入配置信息
2. 选择许可协议
3. 配置初试界面
### 2.1 导入配置信息
- 在第一次启动`PyCharm`时，会首先提示用户是否导入**之前的配置信息**
- 如果是第一次使用，直接点击**OK**按钮
### 2.2 选择许可协议
### 2.3 PyCharm的配置初始页面
- 在初试配置界面，可以通过`Editor colors and fonts`选择**编辑器的配色方案**
### 2.4 欢迎界面
- 所哟基础配置工作结束之后，就可以看到`PyCharm`的**欢迎界面**了，通过**欢迎界面**就可以开始开发Python项目了
## 03.新建/打开一个Python项目
### 3.1项目简介
- 开发**项目**就是开发一个**专门解决一个复杂业务功能的软件**
- 通常每**一个项目**就具有一个**独立专属的目录**，用于保存**所有和项目相关的文件**
	- 一个项目通常会包含**很多源文件**
### 3.2打开Python项目
- 直接点击**Open**按钮，然后浏览到之前保存**Python文件的目录**，即可以打开项目
- 打开之后，会在目录下新建一个`.idea`的目录，用于保存**项目相关的信息**，例如：**解释器版本、项目包含的文件**等等
- 第一次打开项目，需要耐心等待`PyCharm`对项目**进行初始设置**
#### 设置项目使用的解释器版本
- 打开的目录如果不是由`PyCharm`建立的项目目录，**有的时候**使用的解释器版本是`Python 2.x`的，需要**单独设置解释器的版本**
- 通过**File/Setting…**可以打开设置窗口
### 3.3新建项目
## 04.设置PyCharm的字体显示
## 05.PyCharm的升级以及其他
### 5.1安装和启动步骤
- 1.执行以下终端命令，解压下载后的安装包
```
tar -zxvf pycharm-community-2021.3.3.tar.gz 
```
- 2.将解压后的目录移动到`/opt`目录下，可以方便其他用户使用
> `/opt`目录用户存放给主机额外安装的软件
```
sudo mv pycharm-community-2021.3.3 /opt/
```
- 3.切换工作目录
```
cd /opt/pycharm-community-2021.3.3/bin/
```
- 4.启动`PyCharm`
```
./pycharm.sh 
```
### 5.2设置专业版启动图标
- 在**专业版**中，选择菜单**Tools/Create Desktop Entry…**可以设置任务栏启动图标
	- 注意：设置图标时，需要勾选`Create the entry for all users`
### 5.3卸载之前版本的PyCharm
#### 1)程序安装
- 1.程序文件目录
	- 将安装包解压缩，并移动到`/opt`目录下
	- **所有的相关文件都保存在解压缩的目录中**
- 2.配置文件目录
	- 启动`PyCharm`后，会在用户家目录下建立一个`.PyCharmxxx`的隐藏目录
	- 保存`PyCharm`相关配置信息
- 3.快捷方式文件
	- `/usr/share/applications/jetbrains-pycharm.desktop`
> 在`ubuntu`中，应用程序启动的快捷方式通常都保存在`/usr/share/applications`目录下
#### 2)程序卸载
要卸载`PyCharm`只需要做以下两步工作：
- 1.删除解压缩目录
```
sudo rm -r /opt/pycharm-community-2021.3.3/
```
- 2.删除家目录下用于保存配置信息的隐藏目录
```
rm -r ~/.PyCharmxxx.
```
> 如果不再使用PyCharm还需要将`/usr/share/application`下的`jetbrains-pycharm.desktop`删掉
**设置启动图标**
- 1.编辑快捷方式文件
```
sudo gedit /usr/share/applications/jetbrains-pycharm.desktop
```
- 2.按照以下内容修改文件内容，需要注意**指定正确的**`pycharm`**目录**
```
[Desktop Entry]
Verison=1.0
Type=Application
Name=PyCharm
Icon=/opt/pycharm-2021.3.3/bin/pycharm.png
Exec="/opt/pycharm-2021.3.3/bin/pycharm.sh" %f
Comment=The Drive to Develop
Categories=Development;IDE;
Terminal=false
StartupWMClass=jetbrains-pycharm
```

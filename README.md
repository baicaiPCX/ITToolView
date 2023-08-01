# ITToolView
```
qt学习文档：https://qtdocs.pyvista.org/usage.html
python库：PySide2(推荐，开源)、pyqt
搭建3Ddemo:pyvistaqt https://qtdocs.pyvista.org/usage.html
PySide2搭建qt程序：
qt界面设计工具,最后生成ui文件(和qrc文件如果有资源):designer
将ui文件转py文件:pyside2-uic.exe main.ui -o mainview.py
将qrc文件转py文件:pyside2-rcc.exe
```
```
python高效的矩阵操作库（爱因斯坦求和）:einsum
pytorch、TensorFlow高效的张量操作库:einopt
pytorch自带的高效张量操作(爱因斯坦求和):einsum
```
```
apex:NVIDIA官方推出的混合精度训练pytorch扩展库（float16,float32）
```
```
ubuntu监视cpu使用：htop
```
```
vs Release模式下调试exe：右键项目属性->链接器->调试->生成调试信息:生成调试信息(/DEBUG)
vs 某个源文件不优化(调试每一步单步查看局部变量):
    右键该源文件->属性->c/c++->优化->[优化:已禁用(/Od),内联函数扩展:已禁用(/Ob0)]
    右键该源文件->属性->c/c++->常规->调试信息格式:Zi\ZI\Z7
vs 调试时回到上一步:鼠标右键该行->设置下一语句，或者光标切到该行然后按[ctl+shift+F10]
vs 调试时修改变量(两种方法):
    1.在[局部变量窗口]下鼠标双击修改该变量的值;
    2.在[即时窗口]下命令赋值，eg:c=a+3;
```
```
ubuntu 打印目录结构:
tree -L 2 dirname # dirname下面的2级目录结构
```
```
win10好用的解压缩软件:https://www.7-zip.org/
```
```
git diff文本编辑：
1.配置
先把vscode作为git默认编辑器：git config --global core.editor "code --wait"
用vscode 打开 .gitconfig文件：git config --global -e
加上：
[diff]
    tool = default-difftool
[difftool "default-difftool"]
    cmd = code --wait --diff $LOCAL $REMOTE
2.使用
git difftool取代git diff命令
```
```
pytorch训练过程中可视化工具:tensorboard(结合torchvision)、visdom
可以可视化图表、图片、文本.
```
```
可以写代码的ai插件:github copilot(openai提供的codtex)
```
```
Linux上的office：LibreOffice 跨平台
```
```
procdump windows和linux跨平台的dump抓取工具，也可以监视cpu利用率和内内存
介绍：https://learn.microsoft.com/zh-cn/sysinternals/downloads/procdump
捕捉进程崩溃：procdump -ma -t
```
```
win10在powershell设置环境变量（可以在python中os.environ使用):env
1、列出环境变量:ls env or ls env:Test*
2、添加环境变量:$env:NEWV="."
3、删除环境变量:del env:windir
4、查看环境变量值:$env:windir
```
```
vscode 可视化compare的扩展工具:git history.(可以根据分支、作者筛选log)
git 命令：git show hash值
```
```
ubuntu 查看文件路径快捷方式: ctl+L
```
```
git cherry-pick hash值:(merge)合并某次提交
```
```
1、windows系统的文件搜索工具:everything
2、ubuntu系统的文件搜索命令
1) locate +文件名
推荐，从系统数据库中找（该库每天更新一次），效率最快
更新数据库：sudo updatedb
2）whereis +文件名
用于程序名的搜索，搜索结果只限于二进制文件（参数-b）、man说明文件（参数-m）和源代码文件（参数-s），如果省略参数，则返回所有信息
3）find -name +文件名
在指定的目录下遍历查找，如果目录使用 / 则表示在所有目录下查找，find方式从磁盘中查找，速度也慢一点
4）which+可执行文件名
which的作用是在PATH变量指定的路径中，搜索某个系统命令的位置，并且返回第一个搜索结果
```
```
性能分析工具：
1、WPT
微软公司开发，用于分析windows设备性能，主要分析cpu、内存、Disk I/O之间的性能瓶颈，有timeline
2、Nsight
NVIDIA开发(nvprof->Visual Profiler->Nsight)，支持windows、Linux,主要分析NVIDIA gpu计算、显存、cpu调度、数据传输之间的性能瓶颈，有timeline，且支持nvtx注释；
nvtx可以看到哪些时间段处于代码哪个阶段，c++用法：
#include"nvToolsExt.h"
nvtxRangePushA("...");
...测试代码部分
nvtxRangePop("...");
3、VTune
由Intel开发，用于Intel设备性能分析，通过火焰图以及建议更容易看到性能瓶颈，但是上手比较难
4、perf
Linux系统上的cpu性能分析，类似于WPT。
```
```
PEView 查看pe文件结构以及逆向分析pe文件的工具
```
```
c++用cpu计时函数测量gpu运行时间：
#include<time.h>
#include<cuda_runtime.h>
long start,end;
start=clock();
// 测试代码 
cudaThreadSynchronize();
end=clock();
long t=end-start;//单位ms
```
```
nmake：Microsoft Visual Studio中的附带命令，需要安装VS，相当于linux的make
cmake生成：
cmake -G "NMake Makefiles" -DCMAKE_BUILD_TYPE=Release ..
nmake
```
```
Ninja:类似于make（生成makefile）的编译构建工具，优势是加速编译速度。
安装：https://ninja-build.org/
cmake生成ninja文件：
cmake -G Ninja
ninja #编译
```
```
windows程序开发相关环境变量（没有则自己创建）：
INCLUDE:头文件搜索路径
LIB:链接库搜索路径
Path:命令行文件搜索路径
```
```
windows运行xxx.ps1文件(ps1文件其实就是powershell脚本):
powershell先运行命令 set-executionpolicy remotesigned
```
```
windbg 微软发布的轻量化的针对windows的调试器，比vs的调试器更强大.
windbg预览版 是windbg的改进版，可以支持timeline.
```
```
ubuntu解压zip中文乱码:unzip -O CP936 filename.zip
```
```
visual c++ 折叠代码块:
#pragma region name

#pragma endregion name
```
```
查询英文缩写网站:https://www.allacronyms.com/information/abbreviated
```
```
ubuntu安装Boost:
sudo apt-get install libboost-all-dev
```
```
C++程序中读取CmakeList中定义的变量:
set(a "/home/wsw/test/c++")
#定义变量，用-D开头，后面跟字符串，相当于一个宏_VAR，其内容是一个字符串,\"是转义字符，${a}是一个引用变量，用上面的set(a "/home/wsw/test/c++")中的字符串替换
ADD_DEFINITIONS(-D_VAR=\"${a}\")
```
```
gunicorn处理flask并发请求:
pip install gunicorn
pip install greenlet
pip install eventlet 
pip install gevent

gunicorn -w 3 -b 127.0.0.1:5000 app:app

ps -ef | grep gunicorn #找到gunicorn进程
```
```
paraview 跨平台、开源的数据分析和可视化工具
```
```
win10好用的bash工具：windows terminal
```
```
git拉取大项目(仓库代码太大）：
git clone --depth 1 <url>
git fetch --unshallow
git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
git fetch -pv
git fetch --all
```
```
win10安装git:https://git-scm.com/downloads
```
```
c++代码转字符串，编写shader语言：#define SHADER_STRING(...) #__VA_ARGS__
```
```
git查看分支关系图
git log --graph --decorate --oneline --simplify-by-decoration --all
--decorate 标记会让git log显示每个commit的引用(如:分支、tag等)
--oneline 一行显示
--simplify-by-decoration 只显示被branch或tag引用的commit
--all 表示显示所有的branch，这里也可以选择，比如我指向显示分支ABC的关系，则将--all替换为branchA branchB branchC
```
```
pdf 文件操作:PyPDF2
pip install PyPDF2
```
```
C++ 执行文件相关的内置宏:
__FUNCTION__ ：函数名
__TIME__ ：文件运行的时间
__LINE__ ：所在行数
__FILE__：文件的名字
```
```
局域网聊天软件（免费）：内网通
```
```
python开发2D游戏库：pygame
python开发3D游戏库：panda3D
```
```
C++利用输入输出重定向排除bug:
#include<iostream>
#include<fstream>
using namespace std;
//将标准输出重定向到 out.txt文件
ofstream fout("out.txt"); //文件输出流对象
streambuf* pOld =cout.rdbuf(fout.rdbuf()); 
cout << "test" << "\n";
cout.rdbuf(pOld); //用于恢复 标准输出
```
```
理解神经网络（神经网络可视化）：
1）可视化卷积核(Activation Maximization)
PytorchRevelio:https://github.com/farhad-dalirani/PytorchRevelio
2）可视化特征图
https://github.com/waallf/Viusal-feature-map
3）可视化激活热力图(Class Activation Mapping,saliency map)
pytorch-grad-cam:https://github.com/jacobgil/pytorch-grad-cam
```
```
神经网络结构展示（论文里面放图）:
PlotNeuralNet:https://github.com/HarisIqbal88/PlotNeuralNet
ConvNetDraw:https://github.com/cbovar/ConvNetDraw
NN-SVG:http://alexlenail.me/NN-SVG/
```
```
开源的通用的(C/C++)反编译工具：reko
地址:https://github.com/uxmal/reko
```
```
VC dumpbin工具：
# 查看dll接口函数
dumpbin /exports xx.dll
# 查看exe、dll依赖的动态库
dumpbin /dependents xx.dll
```
```
python 汉语翻译成拼音包:pip install pypinyin

# 不带声调的(style=pypinyin.NORMAL)
def pinyin(word):
    s = ''
    for i in pypinyin.pinyin(word, style=pypinyin.NORMAL):
    s += ''.join(i)
    return s
    
# 带声调的(默认)
def yinjie(word):
    s = ''
    # heteronym=True开启多音字
    for i in pypinyin.pinyin(word, heteronym=True):
    s = s + ''.join(i) + " "
    return s
```
```
pycryptodome python强大的加密包
linux install:
pip install pycryptodome

windows install:
pip install pycryptodomex
```

```
python 对对象进行二进制序列化和反序列化（包括字典转bytes，numpy转bytes）：pickle
pickle.dumps()
pickle.loads()
```
```
python py文件转pyd
-->setup.py:
from distutils.core import setup
from Cython.Build import cythonize

setup(
    name='addpyd',
    ext_modules=cythonize("pydt.py"),
)

-->转:
python setup.py build_ext --inplace
```
```
python 选择文件路径对话框：
import tkinter as tk
from tkinter import filedialog

root = tk.Tk()
root.withdraw()

Folderpath = filedialog.askdirectory() #获得选择好的文件夹
Filepath = filedialog.askopenfilename() #获得选择好的文件
```

```
cmake文件里面的find_package(OpenCV):查找OpenCV库。原理在pkg-config里面.
```
```
pkg-confg:找出库的头文件和库的路径
–-list-all     列出所有已安装的共享库
-–cflags     列出指定共享库的预处理和编译flag
-–libs     列出指定共享库的链接flag
```
```
git stash用于将当前工作区的修改暂存起来，就像堆栈一样，可以随时将某一次缓存的修改再重新应用到当前工作区
```
```
查看文件有没有被修改过：md3sum “filename”
```
```
ubuntu解压.tar.gz文件：tar -xzvf filename
```
```
ubuntu查看GPU资源使用情况（每隔10s）：watch -n 10 nvidia-smi
```
```
查看神经网络onnx模型：netron 或者http//lutzroeder.github.io/netron/
```
```
python自定义输入参数：https://blog.csdn.net/zz2230633069/article/details/88914548
```
```
pytorch里面所有网络的基类是nn.Module。在网络的构造函数中要声明使用的所有图层，
在前向函数中要定义从输入怎么到输出。可以通过钩子来检查和修改图层的输出和梯度输出：
egg:  def hook(self,input,output); net.conv2.register_forward_hook(hook);/net.conv2.register_backwark_hook(hook).
```
```
linux批量解压命令:
                for i in *.zip
                do
                unzip -o（会覆盖） $i
                done

```
```
在指定的文件夹搜索某个文件命令：find dirname -name filename
```
```
koroFileHeader:用于vscode的自动生成头文件和函数的注释。文件头注释快捷键：
window:ctrl+alt+I,mac:ctrl+cmd+I;添加函数注释快捷键：window:ctrl+alt+t,mac:ctrl+cmd+t.
```
```
安卓手机上查看日志：adb shell logcat | grep "libtracking"
```
```
取得当前脚本执行的父目录：dirname $0；eg:current_dir=$(cd ‘dirname $0’;pwd)
```
```
python获取或者设置环境变量值：
1）	import os
2）	os.environ[‘environ_name’]=’environ_value’
```
```
Bash自动处理yes/no的提示：echo y | command. 或者 echo n | command
```
```
流程图作图平台:ProcessOn
```
```
Python 用tqdm模块实现进度条显示
```
```
快速图像数据增强库：albumentations
```
```
对庞大的数据集分批读取操作库: h5py
```
```
Ios数据持久化：https://www.jianshu.com/p/1085815457bd
```
```
App产品设计：磨刀https://next.modao.cc
```
```
Python快速搭建服务器:fask包
```
```
mac颜色值查看器：数码测色计
```
```
预训练模型：https://www.jianshu.com/p/7e13a498bd63
```
```
快速构建机器学习 应用的用户界面UIpython库: Streamlit,
教程：http://cw.hubwiz.com/card/c/streamlit-manual/
```
```
调试/测试网页工具:postman
```
```
C++代码测速：
struct timeval start,end;
gettimeofday(&start, NULL );
//test code
gettimeofday(&end, NULL );
double timeuse = ( end.tv_sec - start.tv_sec ) + (end.tv_usec -start.tv_usec)/1000000.0;
printf("time=%f\n",timeuse);
```
```
torchvision用于计算机视觉流行的数据集和模型: 
https://pytorch.org/docs/stable/torchvision/index.html
```
```
pytorch中文文档:
https://pytorch.apachecn.org/docs/0.3/transfer_learning_tutorial.html
```
```
ios处理gpu的图像和视频库：GPUImage
```
```
可微的计算机视觉库:kornia
```
```
python日志管理标准库 logging ：
https://www.cnblogs.com/yyds/p/6901864.html
```
```
为logging日志配置颜色使用 coloredlogs 库
```
```
Python里面的std数据结构库 collections 库
```
```
Python动态导入对象 importlib 库
```
```
Pytorch 分布式训练文档
https://zhuanlan.zhihu.com/p/86441879
```
```
Pytorch 定义学习率调整 torch.optim.lr_scheduler
```
```
Ios支持的gpu并行图形接口:opengl es、Metal(是苹果原生，可以支持gpu多线程)
```
```
Python处理点云或者三角网格的包：open3d
读取带纹理图片的数据：o3d.io.read_triangle_mesh(path,True)
```
```
远程访问公司内网及内部系统的app：EasyConnect
```
```
操作系统图形界面窗口系统:X Window System(也叫X窗口系统)
知名的基于X窗口系统基础构建的桌面环境:GNOME,KDE
远程桌面及交互传输软件:VNC(Virtual Network Computing,包含VNC Server,VNC Viewer)
了解文档：https://bbs.huaweicloud.com/blogs/192107
```
```
服务端请求图片编解码
import base64
import cv2
import numpy as np
# base64ToImg:
image=base64.b64decode(image_b64)
image=np.asarray(bytearray(image),dtype='uint8')
image=cv2.imdecode(image,cv2.IMREAD_COLOR)
# imgToBase64:
retval,buffer=cv2.imencode('.jpg',image)
image_b64=str(base64.b64encode(buffer),encoding='utf-8')
```
```
帮助团队规划、指派、跟踪、报告和管理工作(比如提需求、bug):Jira 平台
```
```
Linux/macOS Terminal下的翻墙
1、安装proxychains-ng
git clone https://github.com/rofl0r/proxychains-ng.git
./configure
make -j8 && make install && make install-config
2、配置
编辑文件/usr/local/etc/proxychains.conf在末尾添加http或者socks5代理地址 如: socks5 172.16.3.44 1080
PS:这里socks5可以指向Shadowsocks的地址，需要安装一个ss的服务 https://github.com/shadowsocks/shadowsocks-qt5/wiki/使用手册
3、加到要翻墙的程序前使用即可，如wget
proxychains4 wget http://youwebsite.com/youfile
```
```
私人使用的仓库:Gitlab
```
```
与服务端互传文件:filezilla
```
```
持续集成管线 CI:
1、GitLab CI/CD
2、Jenkins
```
```
团队、部门、企业内部的信息共享、协同编辑:Confluence
```
```
企业内部管理系统:Office Automation(OA)
```
```
ubunt挂载硬盘:https://www.cnblogs.com/sddai/p/11097028.html
```
```
ubuntu16.04安装nvidia:https://blog.csdn.net/lihe4151021/article/details/90083431
```
```
C++包管理工具：conan
```
```
cuda与gpu驱动版本对应:https://www.nvidia.com/Download/index.aspx?lang=en-us
```
```
pytorch的图神经网络运算库:torch_geometric
```
```
比较两个字符串的相识度:python:difflib.SequenceMatcher
```
```
把当前ubuntu系统制作成镜像:https://www.cnblogs.com/linuxAndMcu/p/10774020.html
重装系统:https://jingyan.baidu.com/article/5225f26b0bb45fe6fa0908bc.html
```
```
pytorch安装官网:https://pytorch.org/get-started/locally/#start-locally
tensorflow安装官网:https://www.tensorflow.org/install/pip?hl=zh-cn（pip包:https://pypi.org/project/tensorflow/#files)
tensorflow配置表:https://tensorflow.google.cn/install/source#linux
nvidia驱动安装官网:https://www.nvidia.com/Download/index.aspx
cuda安装官网:https://developer.nvidia.com/cuda-downloads
cudnn安装官网:https://developer.nvidia.com/rdp/cudnn-download
pip安装:sudo apt install python3-pip
在pip官网搜索whl包:https://pypi.org/
第三方库whl安装包:https://www.lfd.uci.edu/~gohlke/pythonlibs/
conda安装:https://www.anaconda.com/products/individual#Downloads miniconda:https://docs.conda.io/en/latest/miniconda.html
ubuntu镜像下载:https://releases.ubuntu.com/
```
```
ubuntu16配置x11vnc:https://blog.csdn.net/tangkai_prc/article/details/77674671
```
```
vscode插件下载:https://marketplace.visualstudio.com/
```
```
ubuntu修改pip源:
1、长久使用
sudo gedit ~/.pip/pip.conf
# input begin
[global]
index-url = https://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host = https://mirrors.aliyun.com
# input end
2、临时使用
pip install -i https://mirrors.aliyun.com/pypi/simple/ pandas
3、通过命令行配置
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
pip config set install.trusted-host https://mirrors.aliyun.com
```
```
ubuntu设置pip3为默认pip:
sudo update-alternatives --install /usr/bin/pip pip /usr/bin/pip2 1
sudo update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 2
sudo update-alternatives --config pip
######
ubuntu设置python3为默认python:
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7   1
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.5   2
```
```
ubuntu配置本地apt源:https://www.modb.pro/db/11937
apt-get install apt-mirror
lsb_release -a
#
No LSB modules are available.
    Distributor ID: Ubuntu
    Description:    Ubuntu 16.04 LTS
    Release:    16.04
    Codename:   xenial
#
vim /etc/apt/mirror.list
apt-miiror
apt-get install apache2
ln -s /var/spool/apt-mirror/mirror/mirrors.aliyun.com/ubuntu /var/www/html/ubuntu

```
```
python开启文件的http服务:python3 -m http.server
```
```
python根据正则表达式访问文件目录下的文件:glob
python一版的访问文件操作:os
```
```
python开启并发http服务:
import socketserver
import http.server
class ThreadedHTTPServer(socketserver.ThreadingMixIn,http.server.HTTPServer):
    daemon_threads=True
port=8000
server=ThreadedHTTPServer(('',port),http.server.SimpleHTTPRequestHandler)
try:
    server.serve_forever()
except KeyboardInterrupt:
    pass
```
```
解决显存暂用：
fuser -v /dev/nvidia*
然后用kill -9 杀死所有PID
```
```
ubuntu连接远程windows:
sudo apt install rdesktop
windows设置：计算机---属性---远程设置---远程，勾选：允许远程连接到此计算机。去掉默认勾选：仅允许运行使用网络级别验证...，（如果不取消这个，在运行时会出现“ERROR: recv: 连接被对端重置”）
rdesktop -f -a 16  192.168.1.112
```
```
数据标注软件:labelme
```
```
OpenScenGraph:开源的基于opengl的三维引擎，支持跨平台，被广泛的应用在可视化仿真、游戏、虚拟现实、科学计算、三维重建、地理信息、太空探索、石油矿产等领域。
```
```
html:前端的内容；
css:前端的样式;
js:控制前端页面;
jQuery.js:便于搭建前端框架控件;
Three.js:基于WebGL开发的前端3D渲染引擎；
Node.js:服务端js运行环境；
```
```
renderDoc:linux、windows、andrio上的GPU分析工具，可以单步执行shader。
```

```
求两个点云之间的变换用：procrustes 分析
```
```
python操作XML文件:xlm.doc.minidom
```
```
pyinstaller:对python脚本打包成可执行文件，支持windows、macOS。
pip install pyinstaller
pyinstaller -F python_file
pyinstaller -F -w python_file --add-binary "path_configfile:abstrace_path" # 打包配置文件
```
```
cmake构建x64架构:cmake -A x64 path

# win编译命令
cmake .. -G "Visual Studio 16"
cmake --build . --config Release

# Linux/mac编译命令
cmake .. -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Release
cmake --build .
```
```
免费开源的数学作图工具：GeoGebra 
下载地址：https://www.geogebra.org/download
```
```
类似于企业微信、钉钉这样的团队交流工具（跨平台）:BearyChat
```
```
3D Slicer:用于医学领域的图像数据处理软件，包括体素数据可视化、分割、标注
```
```
ubuntu系统永久设置环境变量:
1.1 在/etc/profile文件里面添加(该文件为系统启动文件，对所有用户均有效)
1.2 在/ect/environment文件里面添加(该文件为第二系统启动文件，对所有用户均有效)
1.3 在~/.profile文件里面添加(该文件只有对当前用户有效)
1.4 在~/.bashrc文件里面添加(该文件被~/.profile配置，对当前用户有效)
2 执行 source $config_file 生效当前配置
```
```
类似于make构建工程（支持c++、python、java）:bazel
```
```
可微的图形渲染:tensorflow_graphics(cpu)/tensorflow_graphics_gpu(gpu)
```
```
交互式笔记本：Jupyter Notebook,支持运行40多种编程语言，便于创建和共享文学化程序文档，支持实时代码，数学方程，可视化和 markdown.
1、安装:
pip install jupyter
2、生成配置文件：
jupyter notebook --generate-config
3、生成SHA1加密的密钥，保存密钥：
python # 进入python编辑环境 
>>> from notebook.auth import passwd 
>>> passwd()
4、修改配置文件：
vim jupyter_notebook_config.py（然后在文末加入以下代码）
c = get_config()
c.IPKernelApp.pylab = 'inline'
c.NotebookApp.ip = '0.0.0.0' # 指定访问ip '0.0.0.0' 代表所有ip均可访问   ‘*’ 部分也可
c.NotebookApp.open_browser = False  # 禁止自动打开浏览器
c.NotebookApp.allow_root = True        # 以root身份运行
c.NotebookApp.password = 'sha1:**********************' # 刚才生成的秘钥
c.NotebookApp.port = 7777           # 指定端口，默认8888
c.NotebookApp.notebook_dir = '/data/jupyter-root'     # 指定工作目录
c.PAMAuthenticator.encoding = 'utf8'  #指定utf-8编码，解决读取中文路径或者文件乱码问题
c.NotebookApp.allow_remote_access = True # 允许远程访问
5、启动服务：
jupyter notebook --config jupyter_notebook_config.py
6、浏览器访问
http://{{IP}}:{{PORT}}/
```
```
jupyter显示网页：
1、安装IPython：
pip install --upgrade IPython
2、建立代理页面:
from IPython.display import IFrame
IFrame(src='http://chenqionghe.cnblogs.com', width=1000, height=600)
```
```
windows配置cmake的编译器:
MinGW:只支持32位程序
MinGW-w64:基于MinGW,可以支持64位程序
Cygwin：可以提供类Unix环境
TDM-GCC: 基于MinGW与MinGW-w64,安装比较简单，可以直接在power shell使用gcc命令
```
```
运行c++报一大堆错误可能的原因：
1、引用头文件“#include"xx"加入到了"#program_once"之后了；
2、文件编码问题，比如UTF-8；
3、回车空格格式问题，Linux/Mac 一般是LF，windows是CRLF；
解决跨平台的格式问题：
git config --global core.autocrlf true #Git可以在你push时自动地把行结束符CRLF转换成LF，而在pull代码时把LF转换成CRLF。
git config --global core.autocrlf input #Linux或Mac系统使用LF作为行结束符，当一个以CRLF为行结束符的文件不小心被引入时你肯定想进行修正，把core.autocrlf设置成input来告诉 Git 在push时把CRLF转换成LF，pull时不转换。
git config --global core.autocrlf false #在本地和代码库中都保留CRLF，无论pull还是push都不变，代码库什么样，本地还是什么样子。
```
```
编译器：
1、MSVC->微软的windows系统。
2、GCC->Linux系统。
3、CLANG->apple系统，从GCC发展而来，后端采用LLVM编译器。
4、LLVM，典型的三段式编译器：前端（主要负责词法和语法分析，将源代码转化为抽象语法树(中间代码))、优化器（在前端的基础上，对得到的中间代码进行优化，使代码更加高效）、后端（将已经优化的中间代码转化为针对各自平台的机器）。
```
```
python存储对象的标准库:pickle,CPickle
```
```
网上3d模型:https://www.artec3d.com/3d-models
```
```
可视化图形图像数据的，开源的，跨平台的，支持python/c++/java语言的可视化类库：VTK
PyVista: VTK的高级封装, 文档：https://docs.pyvista.org/examples/index.html
```
```
python测试程序时间:
import time
time.perf_counter() #返回秒，包括睡眠时间
time.process_counter() #返回秒，不包括睡眠时间
```
```
git远程仓库迁移：
1）保持git和gitlab上的用户名的密码一样，在新gitlab上建好需要的group，仓库可以不用建；
2）进入本地仓库的目录，打开Git Bash;
3）git remote add gitlab http://gitlab.xxx.io/<groupname>/<projectname>
4)  git remote   查看新旧两个remote，知道的可以跳过
5)  git push gitlab refs/remotes/<oldremote>/*:refs/heads/*
6)  git pull <oldremote> --tags
7)  git push gitlab --tags
如果 后续旧remote上更新，可以再执一下5）~7）步即同步。
```
```
git config 用户名和密码只需要配置一次:
git config –global credential.helper store
```

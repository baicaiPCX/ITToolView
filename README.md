# ITToolView

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
Python处理点云的包：open3d
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
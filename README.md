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
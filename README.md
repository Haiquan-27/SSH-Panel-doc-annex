# SSH-Panel-doc-annex
=====================

这个仓库用于提供*Sublime Text SSH-Panel*包的必要依赖文件以及详细说明

# 提供的文件

1. python3.dll

2. 以下python3.8 库（分别在Windows10、Ubuntu1.8上使用python3.8环境完成编译）：
> * bcrypt
> * cffi
> * cryptography
> * nacl
> * six

# 使用方法：

## 对于Windows：
* 将python3.dll复制到sublime text安装目录下
![Screenshot](https://raw.githubusercontent.com/Haiquan-27/SSH-Panel-doc-annex/main/dependent_dll.png)
* 将python依赖库放入sublime text用户的*Lib\python38*路径下
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_win.png?raw=true)

## 对于Linux：
* 安装libffi
```bash
# if Debian / Ubuntu
apt-get install libffi-dev
# if Fedora / CentOS / RHEL
sudo yum install libffi-devel
```
* 将python依赖库放入sublime text用户的*Lib\python38*路径下
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_ubuntu.png?raw=true)

SSH-Panel-doc-annex
=====================

This repositories is used to provide necessary dependency files and detailed descriptions of *sublime text SSH panel* package

It can be used in `Windows 64bit` and `Linux 64bit`. For other OS or platforms, you may need to find or compile relevant files by yourself

[此处](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/README-CN.md)中文文档

# Files

1. python3.dll

2. python3.8 library（On Windows10 and Ubuntu1.8 Using Python 3.8 environment to complete compilation）：
> * bcrypt
> * cffi
> * cryptography
> * nacl
> * six

# How to use：
1. Download the project to local
2. Select the required file and copy it to the corresponding loading path of sublime text
3. Restart sublime text

## for Windows：
* copy python3.dll to sublime text *installation directory*
![Screenshot](https://raw.githubusercontent.com/Haiquan-27/SSH-Panel-doc-annex/main/dependent_dll.png)
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_win.png?raw=true)

## for Linux：
> this may not be necessary
* install libffi
```bash
# if Debian / Ubuntu
apt-get install libffi-dev
# if Fedora / CentOS / RHEL
sudo yum install libffi-devel
```
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_ubuntu.png?raw=true)

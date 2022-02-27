SSH-Panel-doc-annex
=====================

This repositories is used to provide necessary dependency files and detailed descriptions of *sublime text SSH panel* package

# Files

1. python3.dll

2. python3.8 library（On Windows10 and Ubuntu1.8 Using Python 3.8 environment to complete compilation）：
> * bcrypt
> * cffi
> * cryptography
> * nacl
> * six

# How to use：

## for Windows：
* copy python3.dll to sublime text *installation directory*
![Screenshot](https://raw.githubusercontent.com/Haiquan-27/SSH-Panel-doc-annex/main/dependent_dll.png)
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_win.png?raw=true)

## for Linux：
* install libffi
```bash
# if Debian / Ubuntu
apt-get install libffi-dev
# if Fedora / CentOS / RHEL
sudo yum install libffi-devel
```
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_ubuntu.png?raw=true)

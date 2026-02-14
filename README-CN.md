SSH-Panel-doc-annex
=====================

这个仓库用于提供*Sublime Text SSH-Panel*包的必要依赖文件以及详细说明

可使用在`Windows x86`、`Windows amd64`、`Linux amd64`、`MacOS amd64`、`MacOS arm64`,对于其他OS或平台你可能需要自行寻找或编译相关文件

# 提供的文件(library)
```
├── py38_linux_x64 (sublime text 4+)
│	 └── dist-packages
│		├── bcrypt (3.2.0)
│		├── cffi (1.15.0)
│		├── six (1.16.0)
│		├── cryptography (36.0.1)
│		├── nacl (1.5.0)
│		└── paramiko (3.5.0)
├── py38_windows_x64 (sublime text 4+)
|	├── dist-packages
|	│	 ├── bcrypt (4.2.0)
|	│	 ├── cffi (1.17.0)
|	│	 ├── cryptography (43.0.0)
|	│	 ├── nacl (1.5.0)
|	│	 ├── paramiko (3.5.0)
|	│	 └── pycparser (2.22)
|	└── python3.dll (python3.8.6/[MSC v.1927 64 bit (AMD64)] on win32)
├─── py38_osx_x64 (sublime tet 4+)
|	 └── dist-packages
|		 ├── bcrypt (4.2.0)
|		 ├── cryptography (43.0.0)
|		 ├── cffi (1.17.0)
|		 ├── nacl (1.5.0)
|		 ├── paramiko (3.5.0)
|		 └── pycparser (2.22)
├─── py38_osx_arm64 (sublime tet 4+)
|	 └── dist-packages
|		 ├── bcrypt (4.2.0)
|		 ├── cryptography (43.0.0)
|		 ├── cffi (1.17.0)
|		 ├── nacl (1.5.0)
|		 ├── paramiko (3.5.0)
|		 └── pycparser (2.22)
├── py33_windows_x64 (sublime text 3211)
│	 └── dist-packages
│		├── asn1crypto (1.5.1)
│		├── bcrypt (3.1.3)
│		├── cffi (1.11.5)
│		├── Crypto (2.6.1)
│		├── ecdsa (0.18.0)
│		├── nacl (1.1.2)
│		├── enum (0.4.7)
│		├── six (1.16.0)
│		└── paramiko (1.18.5)
└── py33_windows_x32 (sublime text 3211)
	 └── dist-packages
		├── ecdsa (0.18.0)
		├── paramiko (0.18.5)
		├── six (0.16.0)
		└── Crypto (2.6.1)
```

# 使用方法：

## 在Linux上
* 安装libffi
```bash
# if Debian / Ubuntu
apt-get install libffi-dev
# if Fedora / CentOS / RHEL
sudo yum install libffi-devel
# if Arch / Manjaro `untest`
sudo pacman -S libffi
# if Opensuse `untest`
sudo zypper install libffi-devel
```
## 在MAC/Apple Silicon上,需要安装 **libffi**
```bash
# you can install from Homebrew
brew install libffi
# Since brew does not add a default search path for downloaded files, a link is required
# link libffi.dylib to /usr/local/lib/
sudo ln -s $(brew --prefix libffi)/lib/libffi.dylib /usr/local/lib/libffi.dylib
# or link to ~/lib
# mkdir -p ~/lib
# ln -s $(brew --prefix libffi)/lib/libffi.dylib ~/lib/libffi.dylib
```
> 由于受到`MacOS SIP`机制的影响，可能无法在诸如`/usr/lib`这样的路径创建连接，为了让libffi.dylib能够正确被sublime text加载，还可以使用`install_name_tool`对`@rapth`进行替换，如果上述方法无效，请使用如下方法:
```bash
# step 1
# install libffi from Homebrew
brew install libffi
ls -al $(brew --prefix libffi)/lib/libffi.8.dylib # check install
# install Xcode Command Line Tools
xcode-select --install
xcode-select -p # check install
install_name_tool -help

# step 2
# running ssh_panel_install_dependencies command in sublime_text console

# step 3
# Locate the directory where _cffi_backend.cpython-38-darwin.so is located and enter it
cd "~/Library/Application Support/Sublime Text"
cd $(dirname $(find . -name "_cffi_backend.cpython-38-darwin.so" | head -1))

# step 4
cp $(brew --prefix libffi)/lib/libffi.8.dylib .
install_name_tool -change @rpath/libffi.8.dylib @loader_path/libffi.8.dylib ./_cffi_backend.cpython-38-darwin.so

# step 5
# restart sublime text
```
## 放置python依赖包

### (推荐)使用`ssh_panel_install_dependencies`自动安装
1. 在安装完`SSH-Panel`后在console中使用`window.run_command('ssh_panel_install_dependencies')`命令进行自动安装
2. 重启sublime text

### 手动安装
1. 将项目下载到本地
2. 根据您的系统平台和sublime text版本选择需要的文件复制到sublime text的相应加载路径中
3. 重启sublime text

#### 对于Windows：
* 将python3.dll复制到sublime text安装目录下 (only sublime text 4+)
![Screenshot](https://raw.githubusercontent.com/Haiquan-27/SSH-Panel-doc-annex/main/dependent_dll.png)
* 将python依赖库放入sublime text用户的*Lib\python38(or python3.3)*路径下
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_win.png?raw=true)

#### 对于Linux：
* 将python依赖库放入sublime text用户的*Lib\python38(or python3.3)*路径下
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_ubuntu.png?raw=true)

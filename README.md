SSH-Panel-doc-annex
=====================

This repositories is used to provide necessary dependency files and detailed descriptions of *sublime text SSH panel* package

It can be used in `Windows amd64` `Linux amd64` `MacOS amd64`. For other OS or platforms, you may need to find or compile relevant files by yourself

[此处](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/README-CN.md)中文文档

# Files(library)
```
├── py33_windows_x64 (sublime text 3211)
│	 └── dist-packages
│		├── asn1crypto (1.5.1)
│		├── bcrypt (3.1.3)
│		├── cffi (1.11.5)
│		├── Crypto (2.6.1)
│		├── ecdsa (0.18.0)
│		├── nacl (1.1.2)
│		└── paramiko (1.18.5)
├── py38_linux_x64 (sublime text 4+)
│	 └── dist-packages
│		├── bcrypt (3.2.0)
│		├── cffi (1.15.0)
│		├── cryptography (36.0.1)
│		├── nacl (1.5.0)
│		└── paramiko (2.9.2)
├── py38_windows_x64 (sublime text 4+)
|	├── dist-packages
|	│	 ├── bcrypt (4.2.0)
|	│	 ├── cffi (1.17.0)
|	│	 ├── cryptography (43.0.0)
|	│	 ├── nacl (1.5.0)
|	│	 ├── paramiko (3.4.1)
|	│	 └── pycparser (2.22)
|	└── python3.dll (python3.8.6/[MSC v.1927 64 bit (AMD64)] on win32)
└─── py38_osx_x64 (sublime tet 4+)
	 └── dist-packages
		 ├── bcrypt (4.2.0)
		 ├── cryptography (43.0.0)
		 ├── cffi (1.17.0)
		 ├── nacl (1.5.0)
		 ├── paramiko (3.4.1)
		 └── pycparser (2.22)
```

# How to use：

## if Linux
* install libffi
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

## place python dependency library

### (recommend) using auto install command with `ssh_panel_install_dependencies`
1. After install `SSH-Panel`,use `window.run_command('ssh_panel_install_dependencies')` in console
2. Restart sublime text

## manual install
1. Download the project to local
2. Select the required file and copy it to the corresponding loading path of sublime text based on your system platform and sublime text version
3. Restart sublime text

## for Windows：
* copy python3.dll to sublime text *installation directory* (only sublime text 4+)
![Screenshot](https://raw.githubusercontent.com/Haiquan-27/SSH-Panel-doc-annex/main/dependent_dll.png)
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_win.png?raw=true)

## for Linux：
* copy python dependency library to *Lib\python38* of user of sublime text
![Screenshot](https://github.com/Haiquan-27/SSH-Panel-doc-annex/blob/main/dependent_ubuntu.png?raw=true)

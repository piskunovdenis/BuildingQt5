# Building a static Qt5 for Windows

## Directory structure
```
C:\
├── Qt
│   ├── 5.14.2
│   |   ├── jom
│   |   ├── Src.x64
│   |   ├── Src.x86
│   ├── third-party
│   |   ├── nasm
│   |   |   ├── Src.x64
│   |   |   |   ├── nasm-2.15.05
│   |   |   ├── Src.x86
│   |   |   |   ├── nasm-2.15.05
│   |   ├── openssl
│   |   |   ├── Src.x64
│   |   |   |   ├── openssl-1.1.1g
│   |   |   ├── Src.x86
│   |   |   |   ├── openssl-1.1.1g
└── ...
```

## Prerequisites
1. Visual Studio 2017
    1. download and install Visual Studio
2. Qt
    1. download ```qt-everywhere-src-5.14.2.zip``` from https://account.qt.io/downloads ```(Qt Source Package, Full Framework with Windows style line endings)```
    2. extract ```qt-everywhere-src-5.14.2.zip``` to ```C:\Qt\5.14.2\Src.x64``` for x64 architecture
    3. extract ```qt-everywhere-src-5.14.2.zip``` to ```C:\Qt\5.14.2\Src.x86``` for x86 architecture
    4. copy ```.qt-license``` to ```%USERPROFILE%```
3. JOM
    1. download ```jom-1.1.2.zip``` from https://account.qt.io/downloads ```(Jom - The parallel make tool for Windows)```
    2. extract ```jom-1.1.2.zip``` to ```C:\Qt\5.14.2\jom```
4. OpenSSL
    1. download ```openssl-1.1.1g.tar.gz``` from https://ftp.openssl.org/source/old/1.1.1/
    2. extract ```openssl-1.1.1g.tar.gz``` to ```C:\Qt\third-party\openssl\Src.x64\openssl-1.1.1g``` for x64 architecture
    3. extract ```openssl-1.1.1g.tar.gz``` to ```C:\Qt\third-party\openssl\Src.x86\openssl-1.1.1g``` for x86 architecture
5. NASM
    1. download ```nasm-2.15.05-win64.zip``` from https://www.nasm.us/pub/nasm/releasebuilds/2.15.05/win64/
    2. extract ```nasm-2.15.05-win64.zip``` to ```C:\Qt\third-party\nasm\Src.x64\nasm-2.15.05``` for x64 architecture
    3. download ```nasm-2.15.05-win32.zip``` from https://www.nasm.us/pub/nasm/releasebuilds/2.15.05/win32/
    4. extract ```nasm-2.15.05-win32.zip``` to ```C:\Qt\third-party\nasm\Src.x86\nasm-2.15.05``` for x86 architecture
6. Active Perl
    1. go to https://www.activestate.com and create a new build with the additional package ```Win32-Console```
    2. download and install Active Perl using the generated cmd command
    3. ensure the installation location is in the system path; in my case the pathes are ```%LOCALAPPDATA%\ActiveState\cache\bin``` and ```%LOCALAPPDATA%\ActiveState\StateTool\release\bin```
7. Python
    1. download ```python-3.8.0-amd64.exe``` from https://www.python.org/downloads/release/python-380
    2. install Python using the downloaded installer
    3. ensure the installation location is in the system path; in my case the pathes are ```%LOCALAPPDATA%\Programs\Python\Python38\``` and ```%LOCALAPPDATA%\Programs\Python\Python38\Scripts\```

## Build
1. copy ```build.bat``` to ```C:\Qt```
2. run ```build.bat x64``` to build a 32-bit version
3. run ```build.bat x86``` to build a 64-bit version

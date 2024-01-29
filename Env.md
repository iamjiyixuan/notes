# 我的工作环境

<!-- TOC -->

- [硬件](#%E7%A1%AC%E4%BB%B6)
- [Windows](#windows)
    - [硬件检测软件](#%E7%A1%AC%E4%BB%B6%E6%A3%80%E6%B5%8B%E8%BD%AF%E4%BB%B6)
    - [科学上网](#%E7%A7%91%E5%AD%A6%E4%B8%8A%E7%BD%91)
    - [Shell 环境](#shell-%E7%8E%AF%E5%A2%83)
    - [C++ 环境](#c-%E7%8E%AF%E5%A2%83)
        - [CMake](#cmake)
    - [如何判断可执行文件是 32bit 还是 64bit](#%E5%A6%82%E4%BD%95%E5%88%A4%E6%96%AD%E5%8F%AF%E6%89%A7%E8%A1%8C%E6%96%87%E4%BB%B6%E6%98%AF-32bit-%E8%BF%98%E6%98%AF-64bit)
    - [OpenCV 环境](#opencv-%E7%8E%AF%E5%A2%83)
        - [官方预构建 x64 版本](#%E5%AE%98%E6%96%B9%E9%A2%84%E6%9E%84%E5%BB%BA-x64-%E7%89%88%E6%9C%AC)
        - [源码构建 x86 版本](#%E6%BA%90%E7%A0%81%E6%9E%84%E5%BB%BA-x86-%E7%89%88%E6%9C%AC)
    - [Python 环境](#python-%E7%8E%AF%E5%A2%83)
    - [CPU 版本 PyTorch 环境](#cpu-%E7%89%88%E6%9C%AC-pytorch-%E7%8E%AF%E5%A2%83)
    - [GPU 版本 PyTorch 环境](#gpu-%E7%89%88%E6%9C%AC-pytorch-%E7%8E%AF%E5%A2%83)
- [WSL2](#wsl2)
    - [Windows 与 WSL 的文件互访](#windows-%E4%B8%8E-wsl-%E7%9A%84%E6%96%87%E4%BB%B6%E4%BA%92%E8%AE%BF)
    - [远程连接 WSL2](#%E8%BF%9C%E7%A8%8B%E8%BF%9E%E6%8E%A5-wsl2)
    - [WSL2 下 CUDA 环境](#wsl2-%E4%B8%8B-cuda-%E7%8E%AF%E5%A2%83)
    - [WSL2 下 Python 环境](#wsl2-%E4%B8%8B-python-%E7%8E%AF%E5%A2%83)
    - [WSL2 下 Docker 环境](#wsl2-%E4%B8%8B-docker-%E7%8E%AF%E5%A2%83)
- [macOS](#macos)
- [其他工具](#%E5%85%B6%E4%BB%96%E5%B7%A5%E5%85%B7)
- [参考](#%E5%8F%82%E8%80%83)

<!-- /TOC -->

## 硬件
- 笔记本
  - [MacBook Pro 2019](https://item.jd.com/100010079900.html)
  - [ThinkPad X1 Carbon 2021](https://item.jd.com/100016419235.html)
    - Intel Core™ i7-1165G7 2.80GHz 4核8线程 CPU
    - 外接 [雷蛇（Razer）战核X 显卡拓展坞](https://item.jd.com/100005298502.html) + [技嘉 GeForce RTX 2060](https://item.jd.com/100031182780.html)
- PC（2024-01）
  - CPU：[i7-13700KF](https://item.jd.com/100040185493.html)
  - 主板：[微星 Z790 CARBON  暗黑](https://item.jd.com/100040431239.html)
  - 显卡：[技嘉 GeForce RTX 2060](https://item.jd.com/100031182780.html)
  - 内存：[宏碁掠夺者 16G×2 DDR5 6800 频率](https://item.jd.com/100045347362.html)
  - 固态：[宏碁掠夺者 GM7 1TB](https://item.jd.com/100049404381.html)
  - 散热：[追风者 D30 360 一体式水冷](https://item.jd.com/100058941167.html)
  - 电源：[追风者 AMP GH 金牌 850W](https://item.jd.com/100058941165.html)
  - 机箱：[追风者 P600S 曜石黑](https://item.jd.com/100003292786.html)
- [HP Z240 Small Form Factor Workstation 2016](https://support.hp.com/cn-zh/document/c04909569)
  - Intel Core™ i5-6500 3.20GHz 4核4线程 CPU
  - [金士顿（Kingston）FURY 16GB（8G×2）套装 DDR4](https://item.jd.com/100005116786.html)
  - <del>NVIDIA Quadro K420 2 GB</del>
  - [丽台（LEADTEK）NVIDIA T1000 8G](https://item.jd.com/100032514078.html)
  - [丽台（LEADTEK）NVIDIA T1000 4G](https://item.jd.com/100012341167.html)
- [华硕（ASUS）RT-AC86U 无线路由器](https://item.jd.com/5026604.html)
- 配件
  - [三星 27英寸 S80PB 平面高分辨率显示器 S27B800PXC](https://www.samsung.com/cn/monitors/high-resolution/s80pb-27-27-inch-ips-uhd-hdr-ls27b800pxcxxf/)
  - [雷蛇（Razer）蝰蛇2000 游戏鼠标 黑色版](https://item.jd.com/3756787.html)
  - [京东京造 C1 有线机械键盘 87 键复古茶轴](https://item.jd.com/100017358781.html)
  - [漫步者（EDIFIER）R1000BT 蓝牙音箱](https://item.jd.com/3202817.html)

## Windows

### 硬件检测软件
- [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
- [GPU-Z](https://www.techpowerup.com/gpuz/)
- [CrystalDiskInfo](https://crystalmark.info/en/software/crystaldiskinfo/) 硬盘健康状况检测工具
- [CrystalDiskMark](https://crystalmark.info/en/software/crystaldiskmark/) 硬盘读写性能评测工具
- [3DMark](https://benchmarks.ul.com/zh-hans/3dmark) 显卡跑分，可以在 Steam 购买

### 科学上网
- [AgentNEO](https://agentneo.tech/)
- [Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg) 下载 Clash.for.Windows.Setup.x.y.z.exe 即可（x.y.z 为版本号）
  - 如果 `pip install` 报错 `ValueError: check_hostname requires server_hostname` 需 Settings -> System Proxy -> 启用 Specify Protocol
  - 如果 `urllib.request.urlopen` 访问 https 不走代理，需要修改注册表 `\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings` 中 `ProxyServer` 为 `http=http://127.0.0.1:7890;https=http://127.0.0.1:7890`，原因分析：
    - https://note.bobo.moe/2021/02/clash-for-windows-pip-proxyerror.html
    - https://github.com/Fndroid/clash_for_windows_pkg/issues/1787
  - 在 `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup` 目录下创建 `.bat` 文件，开机自动执行修改注册表的脚本 `REG ADD "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyServer /d "http=http://127.0.0.1:7890;https=http://127.0.0.1:7890" /f`

### Shell 环境
- XShell
- Cygwin64 Terminal
- Git Bash
- Cmder

### C++ 环境

#### CMake

CMake 可以随 Visual Studio 一起安装在相关目录下，例如 `D:\Software\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe`。但该方式安装不包含 gui 工具，且如果希望在终端命令行使用，还需手动设置系统环境变量。因此推荐[官网下载](https://cmake.org/download/)安装完整版本。

如果下载 raw.githubusercontent.com 资源报 hosts 找不到，可以通过 https://www.ipaddress.com/ 查找对应 IP，然后修改 `C:\Windows\System32\drivers\etc\hosts` 文件临时解决问题

### 如何判断可执行文件是 32bit 还是 64bit
```
$ cd "D:\Software\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.33.31629\bin\Hostx64\x64"
$ .\dumpbin.exe /headers C:\Windows\system32\cmd.exe

Microsoft (R) COFF/PE Dumper Version 14.33.31630.0
Copyright (C) Microsoft Corporation.  All rights reserved.


Dump of file C:\Windows\system32\cmd.exe

PE signature found

File Type: EXECUTABLE IMAGE

FILE HEADER VALUES
            8664 machine (x64)
               7 number of sections
        43111367 time date stamp
               0 file pointer to symbol table
               0 number of symbols
              F0 size of optional header
              22 characteristics
                   Executable
                   Application can handle large (>2GB) addresses

OPTIONAL HEADER VALUES
             20B magic # (PE32+)
[...]
```

### OpenCV 环境

#### 官方预构建 x64 版本

从 https://github.com/opencv/opencv/releases 下载最新版本的 `opencv-x.x.x-vc14_vc15.exe` 文件并双击执行安装。

Visual Studio 创建新的 C++ 控制台应用项目 `HelloOpenCV`，并完成以下配置：
- 修改系统环境变量，将 `D:\Software\opencv\build\x64\vc15\bin` 添加到 PATH 中，否则会报找不到 dll 的错误
- 项目 → HelloOpenCV 属性 → 配置属性 → C++ → 常规 → 附加包含目录，添加 `D:\Software\opencv\build\include`
- 项目 → HelloOpenCV 属性 → 配置属性 → 链接器 → 常规 → 附加库目录，添加 `D:\Software\opencv\build\x64\vc15\lib`
- 项目 → HelloOpenCV 属性 → 配置属性 → 链接器 → 输入 → 附加依赖项，配置为 Debug 添加 `opencv_world460d.lib`，配置为 Release 添加 `opencv_world460.lib`

修改 `HelloOpenCV.cpp`：
```C++
// HelloOpenCV.cpp : 此文件包含 "main" 函数。程序执行将在此处开始并结束。
// 参考：https://docs.opencv.org/4.x/dd/d6e/tutorial_windows_visual_studio_opencv.html

#include <opencv2/core.hpp>
#include <opencv2/imgcodecs.hpp>
#include <opencv2/highgui.hpp>

#include <iostream>

using namespace cv;
using namespace std;

int main(int argc, char** argv)
{
    if (argc != 2)
    {
        cout << " Usage: " << argv[0] << " ImageToLoadAndDisplay" << endl;
        return -1;
    }
    Mat image;
    image = imread(argv[1], IMREAD_COLOR); // Read the file
    if (image.empty()) // Check for invalid input
    {
        cout << "Could not open or find the image" << std::endl;
        return -1;
    }
    namedWindow("Display window", WINDOW_AUTOSIZE); // Create a window for display.
    imshow("Display window", image); // Show our image inside it.
    waitKey(0); // Wait for a keystroke in the window
    return 0;
}
```

程序接收一个命令参数作为显示图片的文件路径，如果程序执行成功，则 OpenCV 基础环境配置成功。

#### 源码构建 x86 版本

目前 OpenCV 官方已经不再提供 x86（32bit）版本的 Pre-built Libraries，需要我们自己参考[官方教程](https://docs.opencv.org/4.x/d3/d52/tutorial_windows_install.html#tutorial_windows_install_build)完成构建。CMake 使用 3.24.3 版本。

### Python 环境

下载安装 [Anaconda](https://www.anaconda.com/)，然后使用 `conda info` 命令查看 conda 默认配置（注意一定要从 Anaconda Navigator 中启动终端）：
```
$ conda info

active environment : base
    active env location : D:\Software\Anaconda3
            shell level : 1
       user config file : C:\Users\jsm\.condarc
 populated config files : C:\Users\jsm\.condarc
          conda version : 4.12.0
    conda-build version : 3.21.8
         python version : 3.9.12.final.0
       virtual packages : __cuda=7.5=0
                          __win=0=0
                          __archspec=1=x86_64
       base environment : D:\Software\Anaconda3  (read only)
      conda av data dir : D:\Software\Anaconda3\etc\conda
  conda av metadata url : None
           channel URLs : https://repo.anaconda.com/pkgs/main/win-64
                          https://repo.anaconda.com/pkgs/main/noarch
                          https://repo.anaconda.com/pkgs/r/win-64
                          https://repo.anaconda.com/pkgs/r/noarch
                          https://repo.anaconda.com/pkgs/msys2/win-64
                          https://repo.anaconda.com/pkgs/msys2/noarch
          package cache : D:\Software\Anaconda3\pkgs
                          C:\Users\jsm\.conda\pkgs
                          C:\Users\jsm\AppData\Local\conda\conda\pkgs
       envs directories : C:\Users\jsm\.conda\envs
                          D:\Software\Anaconda3\envs
                          C:\Users\jsm\AppData\Local\conda\conda\envs
               platform : win-64
             user-agent : conda/4.12.0 requests/2.27.1 CPython/3.9.12 Windows/10 Windows/10.0.19044
          administrator : False
             netrc file : None
           offline mode : False
```

执行 `conda init powershell` 生成 `C:\Users\jyx\Documents\WindowsPowerShell\profile.ps1` 文件（如果卸载 conda 记得要删除该文件），使 PowerShell 打开默认进入 base 环境。
```
// profile.ps1
#region conda initialize
# !! Contents within this block are managed by 'conda init' !!
(& "C:\ProgramData\Anaconda3\Scripts\conda.exe" "shell.powershell" "hook") | Out-String | Invoke-Expression
#endregion
```

初始 `C:\Users\jsm\.condarc` 内容如下：
```
channels:
  - defaults
```

修改 `C:\Users\jsm\.condarc` 设置清华镜像下载源，并将 package cache 和 envs directories 指定到 D 盘（防止占用 C 盘空间）
```
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
pkgs_dirs:
  - D:\.conda\pkgs
envs_dirs:
  - D:\.conda\envs
```

### CPU 版本 PyTorch 环境

创建一个新的 conda 虚拟环境
```console
$ conda create --name hello-torch-cpu --yes
```

激活虚拟环境
```console
$ conda activate hello-torch-cpu
```

安装 CPU 版本 PyTorch
```console
$ conda install pytorch torchvision torchaudio cpuonly -c pytorch
```

检查 PyTorch 版本
```console
$ python

Python 3.10.4 | packaged by conda-forge | (main, Mar 30 2022, 08:38:02) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> torch.__version__
'1.11.0'
>>> exit()
```

设置环境变量 `TORCH_HOME`，否则预训练模型会下载到 `C:\Users\<username>\.cache\torch` 下，占用你的 C 盘空间。https://pytorch.org/docs/stable/hub.html#where-are-my-downloaded-models-saved

### GPU 版本 PyTorch 环境

英伟达官网下载安装最新的显卡驱动，然后检查 GPU 环境。注意 `nvidia-smi` 随显卡驱动安装 [Different CUDA versions shown by nvcc and NVIDIA-smi?](https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi)
```console
$ nvidia-smi

Mon Feb 28 16:08:31 2022
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 497.09       Driver Version: 497.09       CUDA Version: 11.5     |
|-------------------------------+----------------------+----------------------+
| GPU  Name            TCC/WDDM | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ... WDDM  | 00000000:22:00.0 Off |                  N/A |
|  0%   31C    P8    10W / 184W |    249MiB / 12288MiB |      0%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A      6968      C   Insufficient Permissions        N/A      |
+-----------------------------------------------------------------------------+

# 表示显卡驱动版本是 497.09，可以支持 <=11.5 版本的 cuda
```

如果 nvidia-smi 报不是外部命令，先将 `C:\Program Files\NVIDIA Corporation\NVSMI` 添加到系统环境变量 PATH 中

如果 nvidia-smi 没有显示 cuda version 信息，只是驱动版本过低（需要高于 410.72）。https://forums.developer.nvidia.com/t/nvidia-smi-doesnt-show-cuda-version-even-after-installation/68738

（可选）GPU 进程监控开源工具 https://github.com/XuehaiPan/nvitop

安装 CUDA Toolkit https://developer.nvidia.com/cuda-toolkit-archive
```
$ nvcc --version

nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2021 NVIDIA Corporation
Built on Mon_May__3_19:41:42_Pacific_Daylight_Time_2021
Cuda compilation tools, release 11.3, V11.3.109
Build cuda_11.3.r11.3/compiler.29920130_0
```

创建并激活新 conda 虚拟环境（同 CPU 环境）
```console
$ conda create --name hello-torch-cuda --yes
$ conda activate hello-torch-cuda
```

> **Note**
>
> 如果 `conda activate` 报错 `CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.`，尝试执行 `source activate`

安装 cuda 版本 PyTorch
```
$ conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
```

老显卡（例如 NVIDIA Quadro K420）因为算力不够会报 `PyTorch no longer supports this GPU because it is too old.` 可以尝试自己编译 PyTorch [Building PyTorch from source on Windows to work with an old GPU](https://datagraphi.com/blog/post/2021/9/13/building-pytorch-from-source-on-windows-to-work-with-an-old-gpu)

显卡算力查询：https://developer.nvidia.com/cuda-gpus

检查 torch 和 cuda 环境
```console
$ python -c "import torch; print(torch.__version__); print(torch.cuda.is_available()); print(torch.tensor([1, 2, 3]).cuda());"

1.10.2
True
tensor([1, 2, 3], device='cuda:0')
```

## WSL2

WSL：Windows Subsystem for Linux

微软商店安装 Ubuntu 20.04.4 LTS

> **Note**
> 
> 如果报错 `WslRegisterDistribution failed with error: 0x8007019e`，PowerShell 管理员权限下执行 `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`

检查当前 wsl 版本：
```
 $ wsl -l -v
  NAME            STATE           VERSION
* Ubuntu-20.04    Running         1
```

当前 wsl 版本为 1，需要升级到 2。WSL2 需要启动虚拟机功能，PowerShell 管理员权限下执行：
```
$ dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

重启系统，检查一下虚拟机是否已启动：
- 控制面版 --> 卸载程序 --> 启用或关闭 Windows 功能，确认 `Hyper-V`、 `适用于 Linux 的 Windows 子系统`、`虚拟机平台` 这三项已经勾上
- 任务管理器中 --> 性能 --> CPU，确认 `虚拟化` 已启用

> **Note**
> 
> 如果上述选项无法勾选，则需要在 BIOS 中开启虚拟化。以 HP 工作站 Z240 为例：开机按 F10 进入 BIOS，Advanced --> System Optioins --> Early PEIe Delay 中 勾上 `VTx` 和 `VTd`

将 WSL 升级到 2：
```
$ wsl --set-version Ubuntu-20.04 2

正在进行转换，这可能需要几分钟时间...
有关与 WSL 2 的主要区别的信息，请访问 https://aka.ms/wsl2
转换完成。
```

> **Note**
>
> 如果报错 `WSL 2 需要更新其内核组件`，则下载安装 https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

WSL2 的虚拟磁盘文件在 `C:\Users\{user}\AppData\Local\Packages\` 下面，不同的 WSL2 发行版对应的名称不同，例如 Pengwin 是 WhitewaterFoundryLtd.Co，Ubuntu 是 CanonicalGroupLimited，Debian 是 TheDebianProject。找到了你的 WSL2 的文件夹，就能在它下面找到 `LocalState\ext4.vhdx` 这个磁盘文件（初始 6.19G）。

### Windows 与 WSL 的文件互访

WSL 中访问 Windows 文件：
```
$ cd /mnt
```

Windows 访问 WSL 文件：
- Ubuntu 终端中执行 `explorer.exe .`
- 或者 Windows 资源管理器直接打开 `\\wsl$\Ubuntu-20.04\home`

### 远程连接 WSL2

安装网络工具（ifconfig、netstat 等）
```bash
$ sudo apt install net-tools
```

查看所有占用端口
```bash
$ netstat -ano
```

查看指定端口
```bash
$ netstat -aon|findstr "22"
```

设置密码登录。修改配置文件 `/etc/ssh/sshd_config` 允许使用密码登录：`PasswordAuthentication` 置为 yes

重启 ssh 服务：
```
$ sudo service ssh restart
```

查看 ssh 服务状态：
```
$ sudo service ssh status

 * sshd is running
```

尝试从 Windows 主机连接 ssh：
```
$ ssh -v jsm@localhost

OpenSSH_for_Windows_8.1p1, LibreSSL 3.0.2
debug1: Connecting to localhost [::1] port 22.
debug1: Connection established.
debug1: identity file C:\\Users\\jsm/.ssh/id_rsa type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_rsa-cert type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_dsa type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_dsa-cert type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_ecdsa type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_ecdsa-cert type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_ed25519 type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_ed25519-cert type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_xmss type -1
debug1: identity file C:\\Users\\jsm/.ssh/id_xmss-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_for_Windows_8.1
debug1: Remote protocol version 2.0, remote software version OpenSSH_8.2p1 Ubuntu-4ubuntu0.5
debug1: match: OpenSSH_8.2p1 Ubuntu-4ubuntu0.5 pat OpenSSH* compat 0x04000000
debug1: Authenticating to localhost:22 as 'jsm'
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: curve25519-sha256
debug1: kex: host key algorithm: ecdsa-sha2-nistp256
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: Server host key: ecdsa-sha2-nistp256 SHA256:nK+a6+hisNf8y/kQgcvN7Dr9h3+Ak2DVB/vHCBQzNQY
debug1: read_passphrase: can't open /dev/tty: No such file or directory
The authenticity of host 'localhost (::1)' can't be established.
ECDSA key fingerprint is SHA256:nK+a6+hisNf8y/kQgcvN7Dr9h3+Ak2DVB/vHCBQzNQY.

Are you sure you want to continue connecting (yes/no/[fingerprint])? yes # 这里输入 yes

Warning: Permanently added 'localhost' (ECDSA) to the list of known hosts.
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: pubkey_prepare: ssh_get_authentication_socket: No such file or directory
debug1: Will attempt key: C:\\Users\\jsm/.ssh/id_rsa
debug1: Will attempt key: C:\\Users\\jsm/.ssh/id_dsa
debug1: Will attempt key: C:\\Users\\jsm/.ssh/id_ecdsa
debug1: Will attempt key: C:\\Users\\jsm/.ssh/id_ed25519
debug1: Will attempt key: C:\\Users\\jsm/.ssh/id_xmss
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519,sk-ssh-ed25519@openssh.com,ssh-rsa,rsa-sha2-256,rsa-sha2-512,ssh-dss,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ecdsa-sha2-nistp256@openssh.com>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey,password
debug1: Next authentication method: publickey
debug1: Trying private key: C:\\Users\\jsm/.ssh/id_rsa
debug1: Trying private key: C:\\Users\\jsm/.ssh/id_dsa
debug1: Trying private key: C:\\Users\\jsm/.ssh/id_ecdsa
debug1: Trying private key: C:\\Users\\jsm/.ssh/id_ed25519
debug1: Trying private key: C:\\Users\\jsm/.ssh/id_xmss
debug1: Next authentication method: password
debug1: read_passphrase: can't open /dev/tty: No such file or directory

jsm@localhost's password: # 输入 WSL 用户登录密码

debug1: Authentication succeeded (password).
Authenticated to localhost ([::1]:22).
debug1: channel 0: new [client-session]
debug1: Requesting no-more-sessions@openssh.com
debug1: Entering interactive session.
debug1: pledge: network
debug1: ENABLE_VIRTUAL_TERMINAL_INPUT is supported. Reading the VTSequence from console
debug1: ENABLE_VIRTUAL_TERMINAL_PROCESSING is supported. Console supports the ansi parsing
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 5.10.16.3-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sun Jul 10 14:26:57 CST 2022

  System load:  0.01               Processes:             10
  Usage of /:   0.6% of 250.98GB   Users logged in:       0
  Memory usage: 0%                 IPv4 address for eth0: 172.29.247.176
  Swap usage:   0%


0 updates can be applied immediately.


*** System restart required ***

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.
```

Windows 主机设置防火墙入站规则，可以在 `控制面板 --> 系统和安全 --> Windows Defender 防火墙 --> 高级设置 --> 入站规则` 查看：
```
$ netsh advfirewall firewall add rule name=WSL2 dir=in action=allow protocol=TCP localport=2222
```

Windows 主机监听 2222 端口，然后转发至 WSL 的 22 端口：
```
$ netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=172.29.247.176 connectport=22
```

查看当前端口转发设置：
```
$ netsh interface portproxy show all

侦听 ipv4:                 连接到 ipv4:

地址            端口        地址            端口
--------------- ----------  --------------- ----------
0.0.0.0         2222        172.24.198.129  22
```

局域网内登录：
```
$ ssh -v jsm@192.168.50.108 -p 2222
```

### WSL2 下 CUDA 环境
更新 apt 源：
```bash
$ sudo apt update
$ sudo apt upgrade
```

安装 gcc（安装 CUDA Toolkit 需要）：
```bash
$ sudo apt install gcc

$ gcc --version
gcc (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0
Copyright (C) 2019 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

[英伟达官网](https://developer.nvidia.com/cuda-toolkit-archive)查找 WSL 版本 CUDA Toolkit 的安装脚本：
```bash
$ wget https://developer.download.nvidia.com/compute/cuda/11.3.0/local_installers/cuda_11.3.0_465.19.01_linux.run
$ sudo sh cuda_11.3.0_465.19.01_linux.run

===========
= Summary =
===========

Driver:   Not Selected
Toolkit:  Installed in /usr/local/cuda-11.3/
Samples:  Installed in /home/jyx/, but missing recommended libraries

Please make sure that
 -   PATH includes /usr/local/cuda-11.3/bin
 -   LD_LIBRARY_PATH includes /usr/local/cuda-11.3/lib64, or, add /usr/local/cuda-11.3/lib64 to /etc/ld.so.conf and run ldconfig as root

To uninstall the CUDA Toolkit, run cuda-uninstaller in /usr/local/cuda-11.3/bin
***WARNING: Incomplete installation! This installation did not install the CUDA Driver. A driver of version at least 465.00 is required for CUDA 11.3 functionality to work.
To install the driver using this installer, run the following command, replacing <CudaInstaller> with the name of this run file:
    sudo <CudaInstaller>.run --silent --driver

Logfile is /var/log/cuda-installer.log
```

修改环境变量配置 `~/.bashrc`：
```bash
export PATH="/usr/local/cuda-11.3/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-11.3/lib64:$LD_LIBRARY_PATH"
```

```bash
$ nvcc --version

nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2021 NVIDIA Corporation
Built on Sun_Mar_21_19:15:46_PDT_2021
Cuda compilation tools, release 11.3, V11.3.58
Build cuda_11.3.r11.3/compiler.29745058_0
```

### WSL2 下 Python 环境

Anconda 官网下载 [64-Bit(x86) Installer](https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh)，终端安装：
```
$ cd /mnt/c/Users/jsm/Downloads
$ bash Anaconda3-2020.02-Linux-x86_64.sh
```
默认安装在用户下，例如 `/home/jyx/anaconda3`

此时 `conda` 命令还不能在终端使用，修改环境变量：
- 临时生效：终端执行 `export PATH=/home/jyx/anaconda3/bin:$PATH`，可以通过 `echo $PATH` 查看配置结果。仅对当前用户当前终端会话期间有效，关闭终端后失效
- 永久生效：修改环境变量配置文件 `/etc/profile`（系统级） 或者 `~/.bashrc`（用户级，推荐），文件最后添加一行 `export PATH=/home/jyx/anaconda3/bin:$PATH`，最后执行 `source ~/.bashrc`。[Linux 文件 profile、bashrc、bash_profile 区别](https://zhuanlan.zhihu.com/p/405174594)

```
$ conda info

     active environment : None
       user config file : /home/jyx/.condarc
 populated config files :
          conda version : 4.12.0
    conda-build version : 3.21.8
         python version : 3.9.12.final.0
       virtual packages : __linux=5.10.16.3=0
                          __glibc=2.31=0
                          __unix=0=0
                          __archspec=1=x86_64
       base environment : /home/jyx/anaconda3  (writable)
      conda av data dir : /home/jyx/anaconda3/etc/conda
  conda av metadata url : None
           channel URLs : https://repo.anaconda.com/pkgs/main/linux-64
                          https://repo.anaconda.com/pkgs/main/noarch
                          https://repo.anaconda.com/pkgs/r/linux-64
                          https://repo.anaconda.com/pkgs/r/noarch
          package cache : /home/jyx/anaconda3/pkgs
                          /home/jyx/.conda/pkgs
       envs directories : /home/jyx/anaconda3/envs
                          /home/jyx/.conda/envs
               platform : linux-64
             user-agent : conda/4.12.0 requests/2.27.1 CPython/3.9.12 Linux/5.10.16.3-microsoft-standard-WSL2 ubuntu/20.04.4 glibc/2.31
                UID:GID : 1000:1000
             netrc file : None
           offline mode : False
```

修改 `~/.condarc`
```bash
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
pkgs_dirs:
  - /mnt/d/.conda4wsl/pkgs
envs_dirs:
  - /mnt/d/.conda4wsl/envs
```

### WSL2 下 Docker 环境
...

## macOS 

## 其他工具
- [快贴](https://home.clipber.com/)

## 参考
- [【知乎】填坑向：Win 11 + RTX3060 的深度学习环境配置](https://zhuanlan.zhihu.com/p/432831828)
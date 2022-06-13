# 我的工作环境（更新至 2022-05-22）

## 硬件
- [MacBook Pro 2019](https://item.jd.com/100010079900.html)
- [ThinkPad X1 Carbon 2021](https://item.jd.com/100016419235.html)
  - Intel Core™ i7-1165G7 2.80GHz 4核8线程 CPU
  - 外接 [雷蛇（Razer）战核X 显卡拓展坞](https://item.jd.com/100005298502.html) + [技嘉 GIGABYTE GeForce RTX 2060](https://item.jd.com/100031182780.html)
- [HP Z240 Small Form Factor Workstation 2016](https://support.hp.com/cn-zh/document/c04909569)
  - Intel Core™ i5-6500 3.20GHz 4核4线程 CPU
  - NVIDIA Quadro K420 2 GB
- [华硕（ASUS）RT-AC86U 无线路由器](https://item.jd.com/5026604.html)
- 配件
  - [京东京造 C1 有线机械键盘 87 键复古茶轴](https://item.jd.com/100017358781.html)

## Windows

### 硬件检测软件
- [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
- [GPU-Z](https://www.techpowerup.com/gpuz/)
- [CrystalDiskInfo](https://crystalmark.info/en/software/crystaldiskinfo/) 硬盘健康状况检测工具
- [CrystalDiskMark](https://crystalmark.info/en/software/crystaldiskmark/) 硬盘读写性能评测工具
- [3DMark](https://benchmarks.ul.com/zh-hans/3dmark) 显卡跑分，可以在 Steam 购买

### 科学上网
- [AgentNEO](https://agentneo.tech/)
- [Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg) 下载 Clash.for.Windows.Setup.x.y.z.exe 即可

### Windows Subsystem for Linux (WSL)
重置
```
Installing, this may take a few minutes...
Please create a default UNIX user account. The username does not need to match your Windows username.
For more information visit: https://aka.ms/wslusers
Enter new UNIX username: jyx
New password:
Retype new password:
passwd: password updated successfully
Installation successful!
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 4.4.0-22000-Microsoft x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Mar  5 19:08:44 CST 2022

  System load:    0.52      Processes:              7
  Usage of /home: unknown   Users logged in:        0
  Memory usage:   58%       IPv4 address for eth1:  172.19.208.1
  Swap usage:     0%        IPv4 address for wifi0: 192.168.50.203

1 update can be applied immediately.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


This message is shown once a day. To disable it please create the
/home/jyx/.hushlogin file.
```

### Shell 环境
- XShell
- Cygwin64 Terminal
- Git Bash
- Cmder

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

初始 `C:\Users\jsm\.condarc` 内容如下：
```
channels:
  - defaults
```

修改 `C:\Users\jsm\.condarc` 设置清华镜像下载源，并将 package cache 和 envs directories 指定到 D 盘（防止 C 盘爆满）
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

[在 WIN10 PowerShell 中使用并激活 Anaconda 虚拟环境](https://zhuanlan.zhihu.com/p/149656019) 注意，在此之前要将 `D:\Software\Anaconda3`、`D:\Software\Anaconda3\Scripts`、`D:\Software\Anaconda3\Library\bin` 添加到系统环境变量的 PATH 中。（D:\Software\Anaconda3 为 Anaconda3 的安装目录，根据实际情况替换）

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

安装 cuda 版本 PyTorch
```
$ conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
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

## macOS

## 其他工具
- [快贴](https://home.clipber.com/)

## 参考
- [【知乎】填坑向：Win 11 + RTX3060 的深度学习环境配置](https://zhuanlan.zhihu.com/p/432831828)
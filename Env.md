# 工作环境

## Windows

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
- Anaconda。修改 pip 下载源 https://www.jianshu.com/p/344b5b3c81f8
- IPython / Jupyter notebook
- PyCharm

### GPU 相关
- nvidia-smi 随显卡驱动安装 [Different CUDA versions shown by nvcc and NVIDIA-smi?](https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi)
```bash
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

- 安装 CUDA Toolkit https://developer.nvidia.com/cuda-toolkit-archive
```bash
$ nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2021 NVIDIA Corporation
Built on Mon_May__3_19:41:42_Pacific_Daylight_Time_2021
Cuda compilation tools, release 11.3, V11.3.109
Build cuda_11.3.r11.3/compiler.29920130_0
```

- cuDNN

- [Make Your First GAN With PyTorch：4.CUDA基础](https://zhuanlan.zhihu.com/p/427853659)

### git

- OpenSSL SSL_read Connection was reset, errno 10054 https://juejin.cn/post/6963073534398726152
- 设置代理 https://www.jianshu.com/p/739f139cf13c

## macOS

## 参考
- [填坑向：Win 11 + RTX3060 的深度学习环境配置](https://zhuanlan.zhihu.com/p/432831828)
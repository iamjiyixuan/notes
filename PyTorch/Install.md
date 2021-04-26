# PyTorch 开发环境

## macOS 环境使用 pip 安装 PyTorch
第一步，检查 python 环境
```bash
$ python3 --version
Python 3.9.4
```

第二步，检查 pip 是否安装
```bash
$ python3 -m pip --version
pip 20.2.3 from /Library/Frameworks/Python.framework/Versions/3.9/lib/python3.9/site-packages/pip (python 3.9)
```

第三步，使用 pip 安装 py 虚拟环境 virtualenv
```bash
$ sudo pip3 install virtualenv
```

第四步，创建 venv 虚拟环境
```bash
$ virtualenv --system-site-packages -p python3.9 ~/venv
```

第五步，激活 venv 虚拟环境
```bash
$ source ~/venv/bin/activate
```

第六步，在 venv 虚拟环境下安装 PyTorch
```bash
$ pip3 install torch torchvision torchaudio
```

第七步，验证 PyTorch 是否安装成功
```bash
$ python
Python 3.9.4 (v3.9.4:1f2e3088f3, Apr  4 2021, 12:32:44)
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> x = torch.rand(5, 3)
>>> print(x)
>>> exit()
```

第八步，退出 venv 虚拟环境
```bash
$ deactivate
```
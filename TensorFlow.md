# TensorFlow

<!-- TOC -->

- [开发环境 -- 使用 pip 安装 TensorFlow](#%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83----%E4%BD%BF%E7%94%A8-pip-%E5%AE%89%E8%A3%85-tensorflow)
- [开发环境 -- 安装 Jupyter Notebook](#%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83----%E5%AE%89%E8%A3%85-jupyter-notebook)
- [开发环境 -- 使用 Docker 部署 TensorFlow](#%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83----%E4%BD%BF%E7%94%A8-docker-%E9%83%A8%E7%BD%B2-tensorflow)

<!-- /TOC -->

## 开发环境 -- 使用 pip 安装 TensorFlow

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

第六步，在 venv 虚拟环境下安装 TensorFlow。不加 `--upgrade` 可能会出现 `THESE PACKAGES DO NOT MATCH THE HASHES FROM THE REQUIREMENTS FILE.` 的错误
```bash
$ pip install --upgrade tensorflow 
```

第七步，验证 TensorFlow 是否安装成功
```bash
$ python
Python 3.9.4 (v3.9.4:1f2e3088f3, Apr  4 2021, 12:32:44)
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>>
>>> exit()
```

第八步，退出 venv 虚拟环境
```bash
$ deactivate
```

## 开发环境 -- 安装 Jupyter Notebook

第一步，在 venv 虚拟环境中安装 Jupyter
```bash
$ pip install jupyter
```

第二步，为 Jupyter 创建一个 kernel，py 环境指定 venv
```bash
$ python -m ipykernel install --user --name=venv

Installed kernelspec venv in /Users/jyx/Library/Jupyter/kernels/venv
```

```bash
$ jupyter kernelspec list # 查看 Jupyter 当前可用的 kernels
Available kernels:
  venv       /Users/jyx/Library/Jupyter/kernels/venv
  python3    /Users/jyx/venv/share/jupyter/kernels/python3
```

第三步，启动
```bash
$ jupyter notebook
```

## 开发环境 -- 使用 Docker 部署 TensorFlow

第一步，安装 Docker Desktop

第二步，安装 TensorFlow Docker 镜像
```bash
$ docker pull tensorflow/tensorflow:nightly-jupyter
```

第三步，启动 Docker 容器
```bash
$ docker run -it -p 8888:8888 tensorflow/tensorflow:nightly-jupyter
```
# ROS Tutorials 笔记

## 安装 ROS 环境
- 执行 `sudo apt update` 如果出现 `GPG 错误：http://packages.ros.org/ros/ubuntu focal InRelease: 由于没有公钥，无法验证下列签名： NO_PUBKEY F42ED6FBAB17C654`，尝试先执行 `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F42ED6FBAB17C654`

## Navigating the ROS Filesystem

- `catkin` 是新的构建系统，用于替代旧的构建系统 `rosbuild`
- `rospack` 是用于查看 ROS 包信息的工具
- `rosbash`
    - `roscd` 是目录跳转工具，可以通过 ROS 包名跳转目录
    - `rosls`

## ROS 核心概念
- Node 节点
- Topic 话题
- Message 消息
- Service 服务，Node 间通讯的另一种模式
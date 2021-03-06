# HTTPS
<!-- TOC -->

- [定义](#%E5%AE%9A%E4%B9%89)
- [密码学](#%E5%AF%86%E7%A0%81%E5%AD%A6)
    - [随机数](#%E9%9A%8F%E6%9C%BA%E6%95%B0)
    - [Hash 算法](#hash-%E7%AE%97%E6%B3%95)
    - [AES 对称加密](#aes-%E5%AF%B9%E7%A7%B0%E5%8A%A0%E5%AF%86)
        - [加密步骤](#%E5%8A%A0%E5%AF%86%E6%AD%A5%E9%AA%A4)
    - [RSA 非对称加密](#rsa-%E9%9D%9E%E5%AF%B9%E7%A7%B0%E5%8A%A0%E5%AF%86)
- [数字证书](#%E6%95%B0%E5%AD%97%E8%AF%81%E4%B9%A6)
    - [签名过程](#%E7%AD%BE%E5%90%8D%E8%BF%87%E7%A8%8B)
    - [验签过程](#%E9%AA%8C%E7%AD%BE%E8%BF%87%E7%A8%8B)
    - [证书信任链](#%E8%AF%81%E4%B9%A6%E4%BF%A1%E4%BB%BB%E9%93%BE)
    - [证书类型](#%E8%AF%81%E4%B9%A6%E7%B1%BB%E5%9E%8B)
- [密钥交换算法演进](#%E5%AF%86%E9%92%A5%E4%BA%A4%E6%8D%A2%E7%AE%97%E6%B3%95%E6%BC%94%E8%BF%9B)
    - [RSA 密钥交换](#rsa-%E5%AF%86%E9%92%A5%E4%BA%A4%E6%8D%A2)
    - [DH 密钥交换](#dh-%E5%AF%86%E9%92%A5%E4%BA%A4%E6%8D%A2)
    - [ECDH 密钥交换](#ecdh-%E5%AF%86%E9%92%A5%E4%BA%A4%E6%8D%A2)
- [TLS](#tls)
    - [TLS 设计目的](#tls-%E8%AE%BE%E8%AE%A1%E7%9B%AE%E7%9A%84)
- [TLS1.2](#tls12)
- [TLS1.3](#tls13)
- [OpenSSL 实战](#openssl-%E5%AE%9E%E6%88%98)
- [Wireshark 抓包 tls](#wireshark-%E6%8A%93%E5%8C%85-tls)
- [References](#references)

<!-- /TOC -->
## 定义
HTTPS = HTTP over TLS

## 密码学

### 随机数

### Hash 算法

### AES 对称加密
AES 是当前的对称加密标准算法，以 Rijndael 算法为原型。AES 之前的对称加密算法还有 DES、3DES 等，但均已淘汰。
- AES 采用分组加密的工作模式。将明文按数据块大小（16字节）分割为多个数据块，如果最后一个数据块小于 Block Size，则需要填充（padding）
- AES 采用 PKCS7 填充算法。
- AES 采用 GCM 分组模式，GCM = CTR + GMAC。GMAC 是一种 hash 算法，解决数据完整性校验
    - ECB，数据特征过于明显
    - CBC，每个明文块先与前一个密文块进行异或，再进行加密。缺点是加密过程只能串行化，性能差
    - CTR，引入计数器，解决了 CBC 不能并发执行的问题
- AES 密钥长度有三种：AES-128、AES-192、AES-256

#### 加密步骤
- 明文，按 16 字节拆分为若干明文块
- 填充最后一个明文块
- 利用加密器和密钥对每个明文块加密得到密文块
    - 细节？
- 拼接所有密文块

### RSA 非对称加密

## 数字证书
### 签名过程
1. 对用户信息执行 hash 算法得到 hash 值
2. 用 CA 机构自己的私钥对 hash 值加密，得到一串密文，就是签名
3. 签名、用户信息、用户公钥打包成一个数字证书
### 验签过程
1. 客户端或浏览器用户得到数字证书，读取出用户信息、签名
2. 对用户信息执行 hash 算法得到 hash 值
3. 用 CA 机构的公钥对签名进行解密，得到另一个 hash 值
4. 如果 2 和 3 步骤中的 hash 值相等则延签成功
### 证书信任链
每个证书由它的上一层证书来做信用背书，直到根证书。根证书已经内置在浏览器或操作系统中
### 证书类型
不同证书类型在安全性上是一致的，只是 CA 对身份判断的严格程度不同
- DV，域名验证，通常免费
- OV，组织验证，通常不会免费
- EV，扩展验证，一般用于金融机构，价格最贵

## 密钥交换算法演进
### RSA 密钥交换
- 第一步，Client 发 Hello 给 Server
- 第二步，Server 将自己的公钥发给 Client
- 第三步，Client 生成一个随机数作为会话密钥，然后用第二步拿到的公钥对其加密，最后发给 Server
- 第四步，后续通信都采用第三步的会话密钥对内容进行 AES 加密
- 缺陷：没有前向保密性，也就是说如果 Server 的私钥一旦泄露，之前所有通信内容都被解密了

### DH 密钥交换
- DH 算法的特点是 C、S 双方的都可以通过自己的私钥和对方的公钥计算出相同的会话密钥
- 缺陷：1）运算速度慢；2）如果不使用数字证书，还会存在中间人攻击

### ECDH 密钥交换
- 基于 ECC 椭圆曲线，y^2 = x^3 + ax + b，4a^3 + 27b^2 != 0
- 第一步，C 选定大整数 Ka 作为私钥，选定曲线以及曲线上的共享 P 点，计算出 Qa = Ka * P，将 Qa、选定曲线、P 发给 S
- 第二步，S 选定大整数 Kb 作为私钥，计算出 Qb = Kb * P，将 Qb 发给 C
- 

## TLS

### TLS 设计目的
- 保密性
- 身份验证
- 完整性

## TLS1.2

## TLS1.3

## OpenSSL 实战

## Wireshark 抓包 tls

第一步，通过以下方式启动一个新的 Chrome
```bash
$ /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --user-data-dir=/tmp/chrome --ssl-key-log-file=/tmp/.ssl-key.log
```

第二步，Wireshark 中 Preferences → Protocols → TLS → (Pre)-Master-Secret log filename 设置为 `/tmp/.ssl-key.log`

## References
- [《深入浅出 HTTPS：从原理到实战》](https://book.douban.com/subject/30250772/) by 虞卫东
- [HTTPS 温故知新（一） —— 开篇](https://halfrost.com/https-begin/)
- [HTTPS 温故知新（二） —— TLS 记录层协议](https://halfrost.com/https_record_layer/)
- [HTTPS 温故知新（三） —— 直观感受 TLS 握手流程（上）](https://halfrost.com/https_tls1-2_handshake/)
- [HTTPS 温故知新（四） —— 直观感受 TLS 握手流程（下）](https://halfrost.com/https_tls1-3_handshake/)
- [HTTPS 温故知新（五） —— TLS 中的密钥计算](https://halfrost.com/https-key-cipher/)
- [HTTPS 温故知新（六） —— TLS 中的 Extensions](https://halfrost.com/https-extensions/)

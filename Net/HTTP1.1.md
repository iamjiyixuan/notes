# HTTP/1.1
<!-- TOC -->

- [定义](#%E5%AE%9A%E4%B9%89)
- [特性](#%E7%89%B9%E6%80%A7)
    - [无状态 Stateless](#%E6%97%A0%E7%8A%B6%E6%80%81-stateless)
    - [文本协议](#%E6%96%87%E6%9C%AC%E5%8D%8F%E8%AE%AE)
    - [请求响应模式](#%E8%AF%B7%E6%B1%82%E5%93%8D%E5%BA%94%E6%A8%A1%E5%BC%8F)
        - [请求格式](#%E8%AF%B7%E6%B1%82%E6%A0%BC%E5%BC%8F)
        - [响应格式](#%E5%93%8D%E5%BA%94%E6%A0%BC%E5%BC%8F)
    - [长连接](#%E9%95%BF%E8%BF%9E%E6%8E%A5)
    - [分块传输](#%E5%88%86%E5%9D%97%E4%BC%A0%E8%BE%93)
    - [缓存控制](#%E7%BC%93%E5%AD%98%E6%8E%A7%E5%88%B6)
    - [内容协商](#%E5%86%85%E5%AE%B9%E5%8D%8F%E5%95%86)
- [HSTS 安全机制](#hsts-%E5%AE%89%E5%85%A8%E6%9C%BA%E5%88%B6)
- [同源策略](#%E5%90%8C%E6%BA%90%E7%AD%96%E7%95%A5)
- [表单提交](#%E8%A1%A8%E5%8D%95%E6%8F%90%E4%BA%A4)
- [文件上传](#%E6%96%87%E4%BB%B6%E4%B8%8A%E4%BC%A0)
- [断点续传](#%E6%96%AD%E7%82%B9%E7%BB%AD%E4%BC%A0)
- [视频点播](#%E8%A7%86%E9%A2%91%E7%82%B9%E6%92%AD)
- [视频直播](#%E8%A7%86%E9%A2%91%E7%9B%B4%E6%92%AD)
- [痛点](#%E7%97%9B%E7%82%B9)
    - [安全方面](#%E5%AE%89%E5%85%A8%E6%96%B9%E9%9D%A2)
    - [性能方面](#%E6%80%A7%E8%83%BD%E6%96%B9%E9%9D%A2)
- [REST 架构](#rest-%E6%9E%B6%E6%9E%84)
- [References](#references)

<!-- /TOC -->
## 定义
HyperText Transfer Protocol 超文本传输协议

## 特性
### 无状态 Stateless
- 优点：有利于扩容
- 缺点：报文每次都需要携带完整的头部信息，牺牲一部分性能

### 文本协议
- ASCII 编码，8 bits 表示一个字符

### 请求响应模式
#### 请求格式
```
GET / HTTP/1.1          # 方法 URI 协议版本
Host: www.google.com    # 必须携带 HOST 头部
```
- 方法：
    - GET / HEAD
    - POST
    - PUT
    - DELETE
    - CONNECT
    - OPTIONS
- GET 与 POST 的区别
    - 语义不同。GET 表示获取资源，POST 表示提交或修改资源
    - GET 幂等，POST 非幂等
    - GET 会被缓存，POST 不会
    - 一般 GET 参数采用 querystring 拼接在请求行的 URI 中，POST 参数放在 body 中，通过 Content-Type 指定格式（这是浏览器的规范，RFC 中并没有规定 GET 不能用 body，POST 不能用 querystring）

#### 响应格式
```
HTTP/1.1 200 OK         # 协议版本 响应码 消息
Content-Length: 3059
Server: GWS/2.0
Content-Type: text/html
Cache-control: private
Connection: keep-alive
```
响应码
- 1xx：服务器需要进一步处理
    - 101 Switching Protocol。协议升级，例如 WebSocket
- 2xx：成功
- 3xx：重定向
    - 301 Moved Permanently。永久重定向
    - 307 Temporary Redirect。临时重定向
    - 307 Internal Redirect。浏览器内部重定向，一般用于 http 转 https。详见 [HSTS 机制](#hsts-%E5%AE%89%E5%85%A8%E6%9C%BA%E5%88%B6)
- 4xx：客户端错误
    - 400 Bad Request。服务器认为客户端出现了错误，但不能明确是哪种错误，例如 HTTP 请求格式错误
    - 403 Forbidden。没有权限
    - 404 Not Found。服务器没有找到对应的资源
- 5xx：服务器错误
    - 500 Internal Server Error。服务器内部错误，但不能明确是哪种错误
    - 504 Gateway Timeout。网关超时

### 长连接
```
Connection: keep-alive
```
- 开启 keep-alive 后，完成一次请求响应后，TCP 连接不会断开
- 浏览器只能通过 Content-Length 来判断响应内容的边界，如果 Content-Length 不传或大于实际内容，浏览器会一直 pending

### 分块传输
```
HTTP/1.1 200 OK
Content-Type: text/plain
Transfer-Encoding: chunked

7\r\n            # 长度 + CRLF
Mozilla\r\n      # 数据 + CRLF
9\r\n
Developer\r\n
7\r\n
Network\r\n
0\r\n           # 终止块是一个特殊的数据块, 其长度为 0
\r\n
```
解决一些场景下 Content-Length 无法获取到的问题

### 缓存控制

### 内容协商

## HSTS 安全机制
HSTS 全称 HTTP Strict Transport Security，作用是只要浏览器曾经与服务器创建过一次安全连接，之后浏览器会强制使用 HTTPS。例如：

1）首次访问 `https://www.google.com/`，返回的响应携带头部 `strict-transport-security: max-age=31536000`，表示服务器告知浏览器开启 HSTS

2）浏览器地址栏中输入 `http://www.google.com` 时，浏览器会自动返回 `307 Internal Redirect`，并携带响应头部 `Non-Authoritative-Reason: HSTS`

```
GET / HTTP/1.1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 11_2_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
```

```
HTTP/1.1 307 Internal Redirect
Location: https://www.google.com/
Non-Authoritative-Reason: HSTS
```

如何解决首次访问不受 HSTS 保护的问题？预置列表（Preload List）

参考：[Understanding the HTTP 307 Temporary Redirect Status Code in Depth](https://kinsta.com/knowledgebase/307-redirect/)

## 同源策略

## 表单提交
```html
<form method="POST" action="http://localhost:3000/upload-profile-pic">
    <div>
        <input name="a" />
        <input name="b" />
    </div>
    <div>
        <input type="submit" name="btn_upload_profile_pic" value="Upload" />
    </div>
</form>
```

> \<form\> 是唯一可以通过 HTML 而不是 ajax 或 fetch 发出 POST 请求的方式

```
POST http://www.example.com HTTP/1.1
Content-Type: application/x-www-form-urlencoded;charset=utf-8

a=1&b=2
```

## 文件上传
```html
<form method="POST" action="http://localhost:3000/upload-profile-pic" enctype="multipart/form-data">
    <div>
        <label>Select your profile picture:</label>
        <input type="file" name="profile_pic" />
    </div>
    <div>
        <input type="submit" name="btn_upload_profile_pic" value="Upload" />
    </div>
</form>
```

```
POST http://www.example.com HTTP/1.1
Content-Type:multipart/form-data; boundary=----WebKitFormBoundaryrGKCBY7qhFd3TrwA

------WebKitFormBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="text"

title
------WebKitFormBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="file"; filename="chrome.png"
Content-Type: image/png

PNG ... content of chrome.png ...
------WebKitFormBoundaryrGKCBY7qhFd3TrwA--
```

## 断点续传

## 视频点播

## 视频直播

## 痛点
### 安全方面
- 明文传输
- 无法验证通信双方的身份
- 无法防止报文被篡改
### 性能方面
- 不能并行，一个 TCP 连接只能处理一个 HTTP 请求，如果该请求一直未响应，TCP 连接会一直被占用
- 为了保证无状态的特性，报文中有大量重复的头部信息，例如 User-Agent
- 文本编码传输效率低？？

## REST 架构
- [《Architectural Styles and the Design of Network-based Software Architectures》](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm) by Roy Thomas Fielding

## References
- [RFC 7230 - Message Syntax and Routing](https://tools.ietf.org/html/rfc7230)
- [RFC 7231 - Semantics and Content](https://tools.ietf.org/html/rfc7231)
- [RFC 7232 - Conditional Requests](https://tools.ietf.org/html/rfc7232)
- [RFC 7233 - Range Requests](https://tools.ietf.org/html/rfc7233)
- [RFC 7234 - Caching](https://tools.ietf.org/html/rfc7234)
- [RFC 7235 - Authentication](https://tools.ietf.org/html/rfc7235)
- [HTTP 的前世今生](https://coolshell.cn/articles/19840.html)
- [HTTP API 认证授权术](https://coolshell.cn/articles/19395.html)
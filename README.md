# Daily-Basic-Knowledge
[02-06-2021: 从输入 URL 到展现页面的全过程](#02-06-2021-从输入-url-到展现页面的全过程)
[02-07-2021: TCP 协议如何保证可靠传输](#02-07-2021-tcp-协议如何保证可靠传输)
## 02-06-2021: 从输入 URL 到展现页面的全过程
* 在浏览器输入www.google.com
* 首先访问的是离你最近的 DNS 服务器：  
  * Domain Name Service
  * DNS 服务器记录了www.google.com这个域名的 IP 地址是什么
* 你的浏览器然后向该 IP 发送 http/https 请求，通过 IP 地址就能找到该 服务器/计算机
* 服务器(Web Server)收到请求，将请求递交给正在 80 端口监听的HTTP Server
  * 比较常用的 HTTP Server 有 Apache, Unicorn, Gunicorn, Uwsgi
* HTTP Server 将请求转发给 Web Application
  * 最火的三大Web Application Framework: Django, Ruby on Rails, NodeJS
* Web Application 处理请求
  * 根据当前路径 “/”找到对应的逻辑处理模块
  * 根据用户请求参数(GET+POST)决定如何获取/存放数据
  * 从数据存储服务(数据库或者文件系统)中读取数据
  * 组织数据成一张 html 网页作为返回结果
* 浏览器得到结果，展示给用户
## 02-07-2021: TCP 协议如何保证可靠传输
1. 应用数据被分割成 TCP 认为最适合发送的数据块。
2. TCP 给发送的每一个包进行编号，接收方对数据包进行排序，把有序数据传送给应用层。
3. 校验和: TCP 将保持它首部和数据的检验和。这是一个端到端的检验和，目的是检测数据在传
输过程中的任何变化。如果收到段的检验和有差错，TCP 将丢弃这个报文段和不确认收到此报文
段。
4. TCP 的接收端会丢弃重复的数据。
5. 流量控制: TCP 连接的每一方都有固定大小的缓冲空间，TCP的接收端只允许发送端发送接收端
缓冲区能接纳的数据。当接收方来不及处理发送方的数据，能提示发送方降低发送的速率，防止 包丢失。TCP 使用的流量控制协议是可变大小的滑动窗口协议。 (TCP 利用滑动窗口实现流量 控制)
6. 拥塞控制: 当网络拥塞时，减少数据的发送。
7. ARQ协议: 也是为了实现可靠传输的，它的基本原理就是每发完一个分组就停止发送，等待对方
   确认。在收到确认后再发下一个分组。
8. 超时重传: 当 TCP 发出一个段后，它启动一个定时器，等待目的端确认收到这个报文段。如果
   不能及时收到一个确认，将重发这个报文段。

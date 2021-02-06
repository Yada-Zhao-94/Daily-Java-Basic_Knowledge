- [Daily-Basic-Knowledge](#daily-basic-knowledge)
  * [02-07-2021: 从输入 URL 到展现页面的全过程](#02-07-2021------url----------)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# Daily-Basic-Knowledge
## 02-07-2021: 从输入 URL 到展现页面的全过程
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

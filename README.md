# Daily-Basic-Knowledge
## 计算机网络  
[02-06-2021: 从输入 URL 到展现页面的全过程](#02-06-2021-从输入-url-到展现页面的全过程)  
[02-07-2021: TCP 协议如何保证可靠传输](#02-07-2021-tcp-协议如何保证可靠传输)  
[02-07-2021: TCP 中常见的拥塞控制算法有哪些？](#02-07-2021-tcp-中常见的拥塞控制算法有哪些)  
[02-08-2021: HTTP与HTTPS有哪些区别？（包括对称加密与非对称加密的概念）](#02-08-2021-http与https有哪些区别)  
[02-08-2021: 简述 HTTPS 的加密与认证过程](#02-08-2021-简述-https-的加密与认证过程)    
[02-08-2021: 简述TCP三次握手以及四次挥手的流程。为什么需要三次握手以及四次挥手？](#02-08-2021-简述tcp三次握手以及四次挥手的流程为什么需要三次握手以及四次挥手)  
## Java & Java框架 
[02-08-2021: HashMap 与 ConcurrentHashMap 的实现原理是怎样的？ConcurrentHashMap 是如何保证线程安全的？](#02-08-2021-hashmap-与-concurrenthashmap-的实现原理是怎样的concurrenthashmap-是如何保证线程安全的)  
[02-08-2021: synchronized 关键字底层是如何实现的？它与 Lock 相比优缺点分别是什么？](#02-08-2021-synchronized-关键字底层是如何实现的它与-lock-相比优缺点分别是什么)  
[02-08-2021:volatile底层原理](#02-08-2021volatile底层原理)  
[02-08-2021: Java 常见锁有哪些？ReetrantLock 是怎么实现的？](#02-08-2021-java-常见锁有哪些reetrantlock-是怎么实现的)  
[02-08-2021: CAS 实现原理是什么？](#02-08-2021-cas-实现原理是什么)  

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
3. 校验和: TCP 将保持它首部和数据的检验和。这是一个端到端的检验和，目的是检测数据在传输过程中的任何变化。如果收到段的检验和有差错，TCP 将丢弃这个报文段和不确认收到此报文段。
4. TCP 的接收端会丢弃重复的数据。
5. 流量控制: TCP 连接的每一方都有固定大小的缓冲空间，TCP的接收端只允许发送端发送接收端缓冲区能接纳的数据。当接收方来不及处理发送方的数据，能提示发送方降低发送的速率，防止包丢失。TCP 使用的流量控制协议是可变大小的滑动窗口协议。(TCP 利用滑动窗口实现流量控制)
6. 拥塞控制: 当网络拥塞时，减少数据的发送。
7. ARQ协议: 也是为了实现可靠传输的，它的基本原理就是每发完一个分组就停止发送，等待对方确认。在收到确认后再发下一个分组。
8. 超时重传: 当 TCP 发出一个段后，它启动一个定时器，等待目的端确认收到这个报文段。如果不能及时收到一个确认，将重发这个报文段。
## 02-07-2021: TCP 中常见的拥塞控制算法有哪些？
在某段时间，若对网络中某一资源的需求超过了该资源所能提供的可用部分，网络的性能就要变坏。这种情况就叫拥塞。拥塞控制就是为了防止过多的数据注入到网络中，这样就可以使网络中的路由器或链路不致过载。拥塞控制所要做的都有一个前提，就是网络能够承受现有的网络负荷。拥塞控制是一个全局性的过程，涉及到所有的主机，所有的路由器，以及与降低网络传输性能有关的所有因素。相反，流量控制往往是点对点通信量的控制，是个端到端的问题。流量控制所要做到的就是抑制发送端发送数据的速率，以便使接收端来得及接收。  
  
为了进行拥塞控制，TCP 发送方要维持一个 **拥塞窗口(cwnd)** 的状态变量。拥塞控制窗口的大小取决于网络的拥塞程度，并且动态变化。发送方让自己的发送窗口取为拥塞窗口和接收方的接受窗口中较小的一个。  
  
TCP的拥塞控制采用了四种算法，即**慢开始、拥塞避免、快重传和快恢复**。在网络层也可以使路由器采用适当的分组丢弃策略(如主动队列管理 AQM)，以减少网络拥塞的发生。  
  
**慢开始**: 慢开始算法的思路是当主机开始发送数据时，如果立即把大量数据字节注入到网络，那么可能会引起网络阻塞，因为现在还不知道网络的符合情况。经验表明，较好的方法是先探测一下，即由小到大逐渐增大发送窗口，也就是由小到大逐渐增大拥塞窗口数值。cwnd初始值为1，每经过一个传播轮次，cwnd加倍。  
**拥塞避免**: 拥塞避免算法的思路是让拥塞窗口cwnd缓慢增大，即每经过一个往返时间RTT就把发送放的cwnd加1.  
**快重传与快恢复**: 在 TCP/IP 中，快速重传和恢复(fast retransmit and recovery，FRR)是 一种拥塞控制算法，它能快速恢复丢失的数据包。没有 FRR，如果数据包丢失了，TCP 将会使用定时器来要求传输停。在暂停的这段时间内，没有新的或复制的数据包被发送。有了 FRR，如果接收机接收到一个不按顺序的数据段，它会立即给发送机发送一个重复确认。如果发送机接收到三个重复确认，它会假定确认件指出的数据段丢失了，并立即重传这些丢失的数据段。有了 FRR，就不会因为重传时要求的暂停被耽误。当有单独的数据包丢失时，快速重传和恢复 (FRR)能最有效地工作。当有多个数据信息包在某一段很短的时间内丢失时，它则不能很有效地工作。

## 02-08-2021: HTTP与HTTPS有哪些区别？
1. 端口: HTTP的URL由 “http://” 起始且默认使用端口80，而HTTPS的URL由 “https://” 起始且默认使用端口443。 
2. 安全性和资源消耗: HTTP协议运行在TCP之上，所有传输的内容都是明文，客户端和服务器端都无法验证对方的身份。HTTPS是运行在SSL/TLS之上的HTTP协议，SSL/TLS运行在TCP之上。所有传输的内容都经过加密，加密采用对称加密，但对称加密的密钥用服务器方的证书进行了非对称加密。所以说HTTP安全性没有HTTPS高，但是HTTPS比HTTP耗费更多服务器资源。  
 - 对称加密/共享密钥加密: 密钥只有一个，加密解密为同一个密码，且加解密速度快，典型的对称加密算法有DES、AES等;
 - 非对称加密/公开密钥加密: 有一把私有密钥和一把公开密钥。发送密文的一方使用对方的公开密钥进行加密，对方受到被加密的信息后，使用自己的私有密钥进行解密。利用这种方式，不需要发送用来解密的私有密钥，也不必担心密钥被窃听盗走。相对对称加密速度较慢，典型的非对称加密算法有RSA、DSA等。
 
## 02-08-2021: 简述 HTTPS 的加密与认证过程
在交换密钥环节**利用证书**使用非对称加密，之后建立通信交换报文使用对称加密。  
HTTPS的加密过程：
1. 客户端请求服务器获取证书公钥
2. 客户端(SSL/TLS)解析证书（无效会弹出警告）
3. 生成随机值
4. 用证书的公钥加密随机值
5. 客户端将加密后的密钥发送给服务器
6. 服务端用私钥解密得到随机值
7. 将信息和随机值混合在一起进行对称加密
8. 将加密的内容发送给客户端
9. 客户端用密钥解密信息

## 02-08-2021: 简述TCP三次握手以及四次挥手的流程。为什么需要三次握手以及四次挥手？
三次握手流程：
1. 客户端–发送带有 SYN（建立连接） 标志的数据包，一次握手
2. 服务端–发送带有 SYN/ACK（响应） 标志的数据包，二次握手
3. 客户端–发送带有带有 ACK 标志的数据包，三次握手
***
为什么需要三次握手：  
三次握手的目的是建立可靠的通信信道，说到通讯，简单来说就是数据的发送与接收，而三次握手最主要的目的就是双方确认自己与对方的发送与接收是正常的。  
第一次握手:Client什么都不能确认；Server确认了对方发送正常，自己接收正常  
第二次握手:Client确认了:自己发送、接收正常，对方发送、接收正常；Server确认了:对方发送正常，自己接收正常  
第三次握手:Client 确认了:自己发送、接收正常，对方发送、接收正常；Server确认了:自己发送、接收正常，对方发送、接收正常  
所以三次握手就能确认双发收发功能都正常。  
***
四次挥手流程：
1. 客户端-发送一个FIN，用来关闭客户端到服务器的数据传送  
2. 服务器-收到这个FIN，它发回一个ACK，确认序号为收到的序号加1。和SYN一样，一个FIN将占用一个序号  
3. 服务器-关闭与客户端的连接，发送一个FIN给客户端  
4. 客户端-发回ACK报文确认，并将确认序号设置为收到序号加1  
***
为什么需要四次挥手：  
任何一方都可以在数据传送结束后发出连接释放的通知，待对方确认后进入半关闭状态。当另一方也没有数据再发送的时候，则发出连接释放通知，对方确认后就完全关闭了TCP连接。  
举个例子: A和B打电话，通话即将结束后，A说“我没啥要说的了”，B回答“我知道了”，但是B可能还会有要说的话，A不能要求B跟着自己的节奏结束通话，于是B可能又巴拉巴拉说了一通，最后B说“我说完了”，A回答“知道了”，这样通话才算结束。

## 02-08-2021: HashMap 与 ConcurrentHashMap 的实现原理是怎样的？ConcurrentHashMap 是如何保证线程安全的？
HashMap的实现：  
[我实现的HashMap](https://github.com/Yada-Zhao-94/Daily-Java-Basic_Knowledge/blob/main/MyHashMap.java)

**JDK1.8之后**  
相比于之前的版本，JDK1.8之后在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为8)时，将链表转化为红黑树，以减少搜索时间。
***
ConcurrentHashMap的实现原理：（更详细：JavaGuide p58）
 - 底层数据结构：JDK1.7的 ConcurrentHashMap 底层采用分段的数组+链表实现，JDK1.8 采用的数据结构跟HashMap1.8的结构一样，数组+链表/红黑二叉树。
 - 实现线程安全的方式：在 JDK1.7 的时候，ConcurrentHashMap(分段锁) 对整个桶数组进行了分割分段(Segment)，每一把锁只锁容器其中一部分数据，多线程访问容器里不同数据段的数据，就不会存在锁竞争，提高并发访问率。到了 JDK1.8 的时候已经摒弃了Segment的概念，而是直接用Node数组+链表+红黑树的数据结构来实现，并发控制使用 synchronized 和 CAS 来操作。synchronized只锁定当前链表或红黑二叉树的首节点，这样只要hash不冲突，就不会产生并发。
 
## 02-08-2021: synchronized 关键字底层是如何实现的？它与 Lock 相比优缺点分别是什么？
**synchronized 关键字底层是如何实现的？**   
预备知识：  
**CAS**.   
**对象内存布局**，JOL(Java Object Layout)工具.   
1. markword: 锁的状态，GC标记信息，hashCode.  
2. klasspointer  
3. 实例变量  
4. padding: 8的倍数  

**锁升级过程:**  
早期jdk，synchronized属于重量级锁，因为申请锁必须通过kernel, 系统调用.  
**无锁态**  
**偏向锁**  
**轻量级，自旋锁**：只要有线程来抢就会升级。执行地块，线程少比较适合。否则很容易大量消耗CPU资源  
**重量级锁**：不需要消耗CPU资源  
***

## 02-08-2021:volatile底层原理

## 02-08-2021: Java 常见锁有哪些？ReetrantLock 是怎么实现的？
 
## 02-08-2021: CAS 实现原理是什么？
追踪到最后是 **lock cmpxchg 汇编指令**

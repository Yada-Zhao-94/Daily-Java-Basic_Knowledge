# Daily-Basic-Knowledge
## 计算机网络  
[02-06-2021: 从输入 URL 到展现页面的全过程](#02-06-2021-从输入-url-到展现页面的全过程)  
[02-07-2021: TCP 协议如何保证可靠传输](#02-07-2021-tcp-协议如何保证可靠传输)  
[02-07-2021: TCP 中常见的拥塞控制算法有哪些？](#02-07-2021-tcp-中常见的拥塞控制算法有哪些)  
[02-08-2021: HTTP与HTTPS有哪些区别？（包括对称加密与非对称加密的概念）](#02-08-2021-http与https有哪些区别)  
[02-08-2021: 简述 HTTPS 的加密与认证过程](#02-08-2021-简述-https-的加密与认证过程)    
[02-08-2021: 简述TCP三次握手以及四次挥手的流程。为什么需要三次握手以及四次挥手？](#02-08-2021-简述tcp三次握手以及四次挥手的流程为什么需要三次握手以及四次挥手)  
[02-13-2021: RestFul 与 RPC 的区别是什么？RestFul 的优点在哪里？](#02-13-2021-restful-与-rpc-的区别是什么restful-的优点在哪里)  
[02-14-2021: RestFul 是什么？RestFul 请求的 URL 有什么特点？](#02-14-2021-restful-是什么restful-请求的-url-有什么特点)  
[02-15-2021: TCP 与 UDP 在网络协议中的哪一层，他们之间有什么区别？](#02-15-2021-tcp-与-udp-在网络协议中的哪一层他们之间有什么区别)  
[02-16-2021: 从系统层面上，UDP如何保证尽量可靠？](#02-16-2021-从系统层面上udp如何保证尽量可靠)  
[02-17-2021: 简述 HTTP 1.0，1.1，2.0 的主要区别](#02-17-2021-简述-http-101120-的主要区别)  
[02-19-2021: Cookie 和 Session 的关系和区别是什么？](#02-19-2021-cookie-和-session-的关系和区别是什么)  
[DNS 查询服务器的基本流程是什么？DNS 劫持是什么？](#dns-查询服务器的基本流程是什么dns-劫持是什么)

## Java基础、多线程、JVM、Spring
**Java基础：**  
[02-08-2021: HashMap(1.7, 1.8区别) 与 ConcurrentHashMap 的实现原理是怎样的？ConcurrentHashMap 是如何保证线程安全的？](#02-08-2021-hashmap-与-concurrenthashmap-的实现原理是怎样的concurrenthashmap-是如何保证线程安全的)  
[02-09-2021: hashmap 和 hashtable 的区别是什么？](#02-09-2021-hashmap-和-hashtable-的区别是什么)  
[02-12-2021: 简述 Java 的反射机制及其应用场景](#02-12-2021-简述-java-的反射机制及其应用场景)  
[02-20-2021: 简述动态代理与静态代理](#02-20-2021-简述动态代理与静态代理)  
[实现单例设计模式（懒汉，饿汉）](#实现单例设计模式懒汉饿汉)  
[简述 ArrayList 与 LinkedList 的底层实现以及常见操作的时间复杂度]()  
[简述 BIO, NIO, AIO 的区别]()  

***
**多线程：**  
[02-08-2021: synchronized 关键字底层是如何实现的？它与 Lock 相比优缺点分别是什么？](#02-08-2021-synchronized-关键字底层是如何实现的它与-lock-相比优缺点分别是什么)  
[02-08-2021: CAS 实现原理是什么？](#02-08-2021-cas-实现原理是什么)  
[02-09-2021: volatile底层原理](#02-09-2021-volatile底层原理)    
[02-09-2021: Java 常见锁有哪些？ReetrantLock 是怎么实现的？](#02-09-2021-java-常见锁有哪些reetrantlock-是怎么实现的)  
[02-10-2021: 简述 Synchronized，volatile，可重入锁的不同使用场景及优缺点](#02-10-2021-简述-synchronizedvolatile可重入锁的不同使用场景及优缺点)  
[02-11-2021: Java 线程间有多少通信方式？](#02-11-2021java-线程间有多少通信方式)  
[Java 是如何实现线程安全的，哪些数据结构是线程安全的？](#java是如何实现线程安全的哪些数据结构是线程安全的)  
[TODO:线程池是如何实现的？简述线程池的任务策略]()  
***
**JVM：**  
[02-18-2021: Java 中垃圾回收机制中如何判断对象需要回收？常见的 GC 回收算法有哪些？](#02-18-2021-java-中垃圾回收机制中如何判断对象需要回收常见的-gc-回收算法有哪些)   
[02-21-2021: 简述 JVM 的内存区域](#02-21-2021-简述-jvm-的内存区域)  
[02-22-2021: Java 类的加载流程是怎样的？什么是双亲委派机制？](#02-22-2021-java-类的加载流程是怎样的什么是双亲委派机制)  
[02-23-2021: 简述堆的新生代与老年代的区别？](#02-23-2021-简述堆的新生代与老年代的区别)  
[TODO: 简述 JVM 的内存模型，JVM 内存是如何对应到操作系统内存的？]()   

***
**Spring：**  
[简述 Spring bean 的生命周期](#简述-spring-bean-的生命周期)  
[简述 Spring AOP 的原理](#简述-spring-aop-的原理)  

## 数据库
**MySQL:**  
[MySQL为什么使用B+树来作索引，对比B树它的优点和缺点是什么？](#mysql为什么使用b树来作索引对比b树它的优点和缺点是什么)  

***
**Redis:**


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
2. 安全性和资源消耗: HTTP协议运行在TCP之上，所有传输的内容都是明文，客户端和服务器端都无法验证对方的身份。HTTPS是运行在SSL/TLS(Secure Sockets Layer/Transport Layer Security, 解决明文问题)之上的HTTP协议，SSL/TLS运行在TCP之上。所有传输的内容都经过加密，加密采用对称加密，但对称加密的密钥用服务器方的证书进行了非对称加密。所以说HTTP安全性没有HTTPS高，但是HTTPS比HTTP耗费更多服务器资源。  
 - 对称加密/共享密钥加密: 密钥只有一个，加密解密为同一个密码，且加解密速度快，典型的对称加密算法有DES、AES等;
 - 非对称加密/公开密钥加密: 有一把私有密钥和一把公开密钥。发送密文的一方使用对方的公开密钥进行加密，对方受到被加密的信息后，使用自己的私有密钥进行解密。利用这种方式，不需要发送用来解密的私有密钥，也不必担心密钥被窃听盗走。相对对称加密速度较慢，典型的非对称加密算法有RSA、DSA等。
 
## 02-08-2021: 简述 HTTPS 的加密与认证过程
在交换密钥环节**利用证书**使用非对称加密，之后建立通信交换报文使用对称加密。  
HTTPS的加密过程：
1. 客户端明文传输TLS版本信息、加密套件候选列表、压缩算法等信息，还有一个随机数。
2. 服务器端返回选择使用的协议版本、加密套件、压缩算法以及一个随机数。
3. 客户端请求服务器返回证书。
4. 客户端(SSL/TLS)验证证书（用权威机构CA公钥解密证书，若成功证明证书中公钥可信）。
5. 生成随机数字，用证书的公钥加密随机值，客户端将加密后的密钥发送给服务器。
6. 服务端用私钥解密得到随机值。
7. 客户端和服务端都有了三个随机数，可以在客户端和服务器端**产生相同的对称密钥**。
8. 使用对称密钥进行加密传输

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

**锁升级过程/JDK1.6后对synchronized的优化:**  
早期jdk，synchronized属于重量级锁，因为申请锁必须通过kernel, 系统调用.  
**无锁态**  
**偏向锁**  
**轻量级，自旋锁**：只要有线程来抢就会升级。执行地块，线程少比较适合。否则很容易大量消耗CPU资源  
**重量级锁**：不需要消耗CPU资源  
***
**（1）synchronized同步语句块的情况：**  
synchronized 同步语句块的实现使用的是 **monitorenter** 和 **monitorexit** 指令，其中 monitorenter 指令指向同步代码块的开始位置，monitorexit指令则指明同步代码块的结束位置。当执行  monitorenter 指令时，线程试图获取锁也就是获取 monitor(monitor对象存在于每个Java对象的对象头中，synchronized 锁便是通过这种方式获取锁的，也是为什么Java中任意对象可以作为锁的原因) 的持有权。当计数器为0则可以成功获取，获取后将锁计数器设为1也就是加1。相应的在执行 monitorexit 指令后，将锁计数器设为0，表明锁被释放。如果获取对象锁失败，那当前线程就要阻塞等待，直到锁被另外一个线程释放为止。  
**（2）synchronized 修饰方法的的情况：**  
ACC_SYNCHRONIZED 标识，该标识指明了该方法是一个同步方法，JVM 通过该 ACC_SYNCHRONIZED 访问标志来辨别一个方法是否声明为同步方法，从而执行相应的同步调用。
***
**它与 Lock 相比优缺点分别是什么？**  
代码结构比较复杂时使用，更灵活  
Lock接口：Lock接口提供了与synchronized相似的同步功能，和synchronized（隐式的获取和释放锁，主要体现在线程进入同步代码块之前需要获取锁退出同步代码块需要释放锁）不同的是，Lock在使用的时候是显示的获取和释放锁。虽然Lock接口缺少了synchronized隐式获取释放锁的便捷性，但是对于锁的操作具有更强的可操作性、可控制性以及提供可中断操作和超时获取锁等机制。

## 02-08-2021: CAS 实现原理是什么？
追踪到最后是 **lock cmpxchg 汇编指令**  
ABA原理：加版本号
## 02-09-2021: Java 常见锁有哪些？ReetrantLock 是怎么实现的？
1. 从锁的公平性来区分，可以分为公平锁和非公平锁；（锁申请顺序）
2. 从锁是否可重复获取可分为可重入锁和不可重入锁；（比如一个线程获得了某个对象的锁，此时这个对象锁还没有释放，当其再次想要获取这个对象的锁的时候还是可以获取的）
3. 从资源已被锁定，线程是否阻塞可以分为自旋锁；（自旋锁，就是一个线程尝试去获取某一把锁的时候不会立即阻塞，而是采用循环的方式去尝试获取。自己在那儿一直循环获取，就像“自旋”一样。）
4. 从线程是否对资源加锁可以分为悲观锁和乐观锁；
 - （在其持有数据/资源的时候，将其锁住，到这另一个线程过来时发生阻塞，知道悲观锁将数据/资源释放为止）
 - （在读取上不会上锁，但是在写入操作的时候，他会进行判断当前数据是否被修改过）
5. 从那个多个线程能否获取同一把锁分为共享锁和排他锁。
 - 共享锁，又称读锁，指的是允许多个线程同时获取一个锁，一个锁可以同时被多个线程拥有。  
如果某个线程对资源加上共享锁后，则其他线程只能对资源再加共享锁，不能加排它锁。获得共享锁的线程只能读数据，不能修改数据。
 - 排他锁，又称独占锁，指的是一个锁在某一时刻只能被一个线程占有，其它线程必须等待锁被释放之后才可能获取到锁。
6. 多Jvm环境下多线程操作多个资源类分为分布式锁。
***
ReentrantLock也是mutual exclusive的锁，类似于synchronized这种隐式锁，但有更多的功能，比如可以指定是公平锁。

## 02-09-2021: volatile底层原理
相关知识：
1. 主存和线程的本地内存（在CPU的寄存器上）
2. volatile作用：
 - 保证变量可见性，每次使用前必须到主存读取
 - 防止指令重排序
3. 懒汉式的singleton中必须使用volatile: 防止JVM指令重排序
4. happens-before原则（JVM规定指令重排序必须遵守的规则）

**volatile底层原理**：  
JVM层面，声明为volatile的变量在读写之前之后都加**内存屏障**，屏障两边的指令不可以重排

## 02-09-2021: hashmap 和 hashtable 的区别是什么？
1. 线程是否安全: HashMap 是非线程安全的，HashTable 是线程安全的; HashTable 内部的方法基本都经过synchronized修饰。(如果你要保证线程安全的话就使用 ConcurrentHashMap 吧!);
2. 效率: 因为线程安全的问题，HashMap 要比 HashTable 效率高一点。另外，HashTable 基本被淘汰，不要在代码中使用它;
3. 对Null key和Null value的支持: HashMap 中，null 可以作为键，这样的键只有一个，可以有一个或多个键所对应的值为null。但是在 HashTable 中 put 进的键值只要有一个null，直接抛出NullPointerException。
4. 初始容量大小和每次扩充容量大小的不同 : 
 - （1）创建时如果不指定容量初始值，Hashtable 默认的初始大小为11，之后每次扩充，容量变为原来的2n+1。HashMap 默认的初始化大小为16。之后每次扩充，容量变为原来的2倍。
 - （2）创建时如果给定了容量初始值，那么 Hashtable 会直接使用你给定的大小，而 HashMap 会将其扩充为2的幂次方大小。也就是说 HashMap 总是使用2的幂作为哈希表的大小。
5. 底层数据结构: JDK1.8 以后的 HashMap 在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为8)时，将链表转化为红黑树，以减少搜索时间。Hashtable 没有这样的机制。

## 02-10-2021: 简述 Synchronized，volatile，可重入锁的不同使用场景及优缺点
**ReentrantLock 比 synchronized 增加了一些高级功能**  
主要来说主要有三点:
1. 等待可中断; 正在等待的线程可以选择放弃等待，改为处理其他事情。
2. 可实现公平锁; ReentrantLock可以指定是公平锁还是非公平锁。而synchronized只能是非公平锁。所谓的公平锁就是先等待的线程先获得锁。
3. 可实现选择性通知(锁可以绑定多个条件). 线程对象可以注册在指定的Condition(对象监视器)中，从而可以有选择性的进行线程通知，在调度线程上更加灵活。在使用notify()/notifyAll()方法进行通知时，被通知的线程是由JVM选择的，用ReentrantLock类结合Condition实例可以实现“选择性通知”。
***
**synchronized关键字和volatile关键字比较**
1. volatile关键字是线程同步的轻量级实现，所以volatile性能肯定比synchronized关键字要好。 但是**volatile关键字只能用于变量而synchronized关键字可以修饰方法以及代码块**。synchronized关键字在JavaSE1.6之后进行了主要包括为了减少获得锁和释放锁带来的性能消耗而引入的偏向锁和轻量级锁以及其它各种优化之后执行效率有了显著提升，实际开发中使用synchronized关键字的场景还是更多一些。
2. 多线程访问volatile关键字不会发生阻塞，而synchronized关键字可能会发生阻塞
3. volatile关键字能保证数据的可⻅性，但不能保证数据的原子性。synchronized关键字两者都能保证。（可⻅性:当一个变量对共享变量进行了修改，那么另外的线程都是立即可以看到修改后的最新值。volatile 关键字可以保证共享变量的可⻅性。）
4. volatile关键字主要用于解决变量在多个线程之间的可⻅性，而synchronized关键字解决的是多个线程之间访问资源的同步性。

## 02-11-2021：Java 线程间有多少通信方式？
[There are three ways for threads to communicate with each other.](https://cse.iitkgp.ac.in/~dsamanta/java/ch6.htm#Synchronization%20and%20Inter-Thread%20Communication)
1. 共享数据。多个线程共享同一块内存空间
2. 使用线程控制方法。有三种
 - suspend()：线程可暂停自己，等待其他线程resume它
 - resume()：唤醒其他等待的线程（使用了suspend），然后并发执行
 - join()：保证该线程在这行之后执行完成
3. 条件同步：
 - wait()：进入线程的等待列表
 - notify()：随机通知一个等待的线程进入ready-to-run状态
 - notifyAll()：通知所有等待的线程

## 02-12-2021: 简述 Java 的反射机制及其应用场景
注解：也叫元数据。一种代码级别的说明。它是JDK1.5及以后版本引入的一个特性，与类、接口、枚举是在同一个层次。它可以声明在包、类、字段、方法、局部变量、方法参数等的前面，用来对这些元素进行说明，注释。  
内置注解，元注解，自定义注解。  
***
反射，Class对象，类加载时候的方法区和堆的变化。类加载过程：加载 -> 链接 -> 初始化  
[反射机制及应用场景](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/basis/%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6.md)

## 02-14-2021: RestFul 是什么？RestFul 请求的 URL 有什么特点？
REST描述的是在网络中client和server的一种交互形式。RESTful API中，URL定位资源，用HTTP协议动词（GET,POST,DELETE）来实现资源的添加，修改，删除等操作。  
URL中只使用名词来指定资源，原则上不使用动词。

## 02-13-2021: RestFul 与 RPC 的区别是什么？RestFul 的优点在哪里？
RPC：远程过程调用。RPC要解决的两个问题：  
1. 解决分布式系统中，服务之间的调用问题。
2. 远程调用时，要能够像本地调用一样方便，让调用者感知不到远程调用的逻辑。
***
RestFul和RPC的区别  
1. RPC不一定是基于HTTP实现的（常用：TCP），RESTFUL是基于HTTP来实现的。  
2. 从传输速度上来看，因为HTTP封装的数据量更多所以数据传输量更大，所以RPC的传输速度是比RESTFUL更快的。
3. 因为HTTP协议是各个框架都普遍支持的。在toC情况下，因为不知道情况来源的框架、数据形势是什么样的，所以在网关可以使用Restful利用http来接受。而在微服务内部的各模块之间因为各协议方案是公司内部自己定的，所以知道各种数据方式，可以使用TCP传输以使各模块之间的数据传输更快。所以可以网关和外界的数据传输使用RESTFUL，微服务内部的各模块之间使用RPC。

## 02-15-2021: TCP 与 UDP 在网络协议中的哪一层，他们之间有什么区别？
运输层。  
UDP 在传送数据之前不需要先建立连接，远地主机在收到 UDP 报文后，不需要给出任何确认。虽然 UDP 不提供可靠交付，但在某些情况下 UDP 确是一种最有效的工作方式(一般用于即时通信)。  
TCP 提供面向连接的服务。在传送数据之前必须先建立连接，数据传送结束后要释放连接。 TCP 不提供广播或多播服务。由于 TCP 要提供可靠的，面向连接的传输服务(TCP的可靠体现在TCP在传递数据之前，会有三次握手来建立连接，而且在数据传递时，有确认、窗口、重传、拥塞控制机制，在数据传完后，还会断开连接用来节约系统资源)，这一难以避免增加了许多开销，如确认，流量控制，计时器以及连接管理等。这不仅使协议数据单元的首部增大很多，还要占用许多处理机资源。TCP 一般用于文件传输、发送和接收邮件、远程登录等场景。

## 02-16-2021: 从系统层面上，UDP如何保证尽量可靠？
可以在应用层模拟TCP的可靠机制：
1. 发送方每次发出的数据进行编号，同时保持顺序的正确。
2. 每次接收方接收到数据，发出应答信号。同时发送方在规定的时间检测是否接收到应答，如果没有接收到应答，重发，三次后还未收到应答直接判断发送失败。
3. 发送数据时，发送方增加校验位。如果接收方校验出错，请求重发。

## 02-17-2021: 简述 HTTP 1.0，1.1，2.0 的主要区别
https://blog.csdn.net/ailunlee/article/details/97831912  
**HTTP 1.0 和 1.1 的区别**  
1. ⻓连接:  在HTTP 1.0中，默认使用的是短连接，也就是说每次请求都要重新建立一次连接。 HTTP 是基于TCP/IP协议的,每一次建立或者断开连接都需要三次握手四次挥手的开销，如果每次请求都要这样的话，开销会比较大。因此最好能维持一个⻓连接，可以用个⻓连接来发多个请求。HTTP 1.1起，默认使用⻓连接 ,默认开启Connection: keep-alive。HTTP/1.1的持续连接有非流水线方式和流水线方式。流水线方式是客户在收到 HTTP 的响应报文之前就能接着发送新的请求报文。与之相对应的非流水线方式是客户在收到前一个响应后才能发送下一个请求。
2. 错误状态响应码 :在HTTP1.1中新增了24个错误状态响应码，如409(Conflict)表示请求的资源与资源的当前状态发生冲突; 410(Gone)表示服务器上的某个资源被永久性的删除。
3. 缓存处理 :在HTTP1.0中主要使用header里的If-Modified-Since,Expires来做为缓存判断的标准，HTTP1.1 则引入了更多的缓存控制策略例如Entity tag，If-Unmodified-Since, If-Match, If-None-Match等更多可供选择的缓存头来控制缓存策略。
4. 带宽优化及网络连接的使用 :HTTP1.0中，存在一些浪费带宽的现象，例如客户端只是需要某个对象的一部分，而服务器却将整个对象送过来了，并且不支持断点续传功能，HTTP1.1则在请求头引入了range头域，它允许只请求资源的某个部分，即返回码是206(Partial Content)，这样就方便了开发者自由的选择以便于充分利用带宽和连接。
***
**1.1 和 2.0 的区别**
1. 多路复用，做到同一个连接并发处理多个请求
2. 头部数据压缩
3. 服务器推送

## 02-18-2021: Java 中垃圾回收机制中如何判断对象需要回收？常见的 GC 回收算法有哪些？
如何判断对象不再被引用：
1. 引用计数法（不能解决循环引用）
2. 可达性分析算法：GC roots  
***
常见的GC回收算法:(参考图:JavaGuide P109)  
标记-清除算法  
复制算法：分为两块，一块清理完后整理到另一半区域  
标记-整理算法  
分代收集算法(当前虚拟机的垃圾收集都采用分代收集算法): 只是根据对象存活周期的不同将内存分为几块。一般将java堆分为新生代和老年代，这样我们就可以根据各个年代的特点选择合适的垃圾收集算法。  
比如在新生代中，每次收集都会有大量对象死去，所以可以选择复制算法，只需要付出少量对象的复制成本就可以完成每次垃圾收集。而老年代的对象存活几率是比较高的，而且没有额外的空间对它进行分配担保，所以我们必须选择“标记-清除”或“标记-整理”算法进行垃圾收集。

## 02-19-2021: Cookie 和 Session 的关系和区别是什么？
Cookie 和 Session都是用来跟踪浏览器用户身份的会话方式，但是两者的应用场景不太一样。  
**Cookie 一般用来保存用户信息**，比如  
我们在 Cookie 中保存已经登录过得用户信息，下次访问网站的时候⻚面可以自动帮你登录的一些基本信息给填了;  
一般的网站都会有保持登录也就是说下次你再访问网站的时候就不需要重新登录了，这是因为用户登录的时候我们可以存放了一个 Token 在 Cookie 中，下次登录的时候只需要根据 Token 值来查找用户即可(为了安全考虑，重新登录一般要将 Token 重写);  
登录一次网站后访问网站其他⻚面不需要重新登录。  
**Session 的主要作用就是通过服务端记录用户的状态** 典型的场景是购物⻋，当你要添加商品到购物⻋的时候，系统不知道是哪个用户操作的，因为 HTTP 协议是无状态的。服务端给特定的用户创建特定的 Session 之后就可以标识这个用户并且跟踪这个用户了。  
Cookie 数据保存在客户端(浏览器端)，Session 数据保存在服务器端。  
Cookie 存储在客户端中，而Session存储在服务器上，相对来说 Session 安全性更高。如果要在 Cookie 中存储一些敏感信息，不要直接写入 Cookie 中，最好能将 Cookie 信息加密然后使用到的时候再去服务器端解密。

## 02-20-2021: 简述动态代理与静态代理
静态代理类的源代码由程序员创建或由特定工具自动生成，再对其编译。在程序运行前，代理类的.class文件就已经存在了。  
动态代理类：在程序运行时，运用反射机制动态创建而成。作用：  
Proxy类的代码量被固定下来，不会因为业务的逐渐庞大而庞大；  
可以实现AOP编程  

## 02-21-2021: 简述 JVM 的内存区域
线程共享：方法区，堆  
线程私有：虚拟机栈，本地方法栈，程序计数器  
**程序计数器（Program Counter Register）**  
是一块较小的内存空间，它可以看作是当前线程所执行的字节码的行号指示器。在虚拟机概念模型里，字节码解释器工作时就是通过改变这个计数器的值来选取下一条需要执行的字节码指令：分支、跳转、循环、异常处理、线程恢复等基础操作都会依赖这个计数器来完成。每个线程都有独立的程序计数器，用来在线程切换后能恢复到正确的执行位置，各条线程之间的计数器互不影响，独立存储。所以它是一个“线程私有”的内存区域。此内存区域是唯一一个在JVM规范中没有规定任何OutOfMemoryError情况的区域。  
**虚拟机栈（VM Stack）**  
JVM栈是线程私有的内存区域。它描述的是java方法执行的内存模型，每个方法执行的同时都会创建一个栈帧（Stack Frame）用于存储局部变量表、操作数栈、动态链接、方法出口等信息。每个方法从调用直至完成的过程，都对应着一个栈帧从入栈到出栈的过程。每当一个方法执行完成时，该栈帧就会弹出栈帧的元素作为这个方法的返回值，并且清除这个栈帧，Java栈的栈顶的栈帧就是当前正在执行的活动栈，也就是当前正在执行的方法。局部变量表存放了编译器可知的各种基本数据类型（int、short、byte、char、double、float、long、boolean）、对象引用（reference类型，它不等同于对象本身，可能是一个指向对象起始地址的引用指针，也可能是指向一个代表对象的句柄或其他与此对象相关的位置）和returnAddress类型（指向字节码的指针）。在JVM规范中，对这个区域规定了两种异常情况：如果线程请求的栈深度大于虚拟机允许的深度，将抛出StackOverflowError异常；如果虚拟机栈可以动态扩展，在扩展时无法申请到足够的内存，就会抛出OutOfMemoryError异常。  
**本地方法栈（ Native Method Stack）**  
本地方法栈和虚拟机栈所发挥的作用是很相似的，它们之间的区别不过是虚拟机栈为虚拟机执行Java方法（字节码）服务，而本地方法栈则为虚拟机使用到的Native方法服务。Sun HotSpot直接就把本地方法栈和虚拟机栈合二为一。本地方法栈也会抛出StackOverflowError和OutOfMemoryError异常。  
**堆（Heap）**  
Heap是OOM故障最主要的发源地，它存储着几乎所有的实例对象，堆由垃圾收集器自动回收，堆区由各子线程共享使用；通常情况下，它占用的空间是所有内存区域中最大的，但如果无节制地创建大量对象，也容易消耗完所有的空间；堆的内存空间既可以固定大小，也可运行时动态地调整，通过参数-Xms设定初始值、-Xmx设定最大值。  
**方法区（Method Area）**          
方法区是被所有线程共享的内存区域，用来存储已被虚拟机加载的类信息、常量、静态变量、JIT（just in time,即时编译技术）编译后的代码等数据。运行时常量池是方法区的一部分，用于存放编译期间生成的各种字面常量和符号引用。  

## 02-22-2021: Java 类的加载流程是怎样的？什么是双亲委派机制？
类加载过程:加载 > 连接 > 初始化。连接过程又可分为三步:验证 > 准备 > 解析。  
1. 加载：程序运行之前jvm会把编译完成的.class二进制文件加载到内存，供程序使用，用到的就是类加载器classLoader   
2. 连接：　
 - 验证：确保类加载的正确性。一般情况由javac编译的class文件是不会有问题的，但是可能有人的class文件是自己通过其他方式编译出来的，这就很有可能不符合jvm的编译规则，这一步就是要过滤掉这部分不合法文件　

 - 准备：为类的静态变量分配内存，将其初始化为默认值。我们都知道静态变量是可以不用我们手动赋值的，它自然会有一个初始值。比如int类型的初始值就是0；boolean类型初始值为false，引用类型的初始值为null。这里注意，只是为静态变量分配内存，此时是没有对象实例的　

 - 解析：把类中的符号引用转化为直接引用。符号引用以一组符号来描述所引用的目标，符号可以是任何形式的字面量，只要使用时能够无歧义的定位到目标即可。在编译时，java类并不知道所引用的类的实际地址，因此只能使用符号引用来代替。

3. 初始化：为类的静态变量赋予正确的初始值，上述的准备阶段为静态变量赋予的是虚拟机默认的初始值，此处赋予的才是程序编写者为变量分配的真正的初始值
***
双亲委派机制：当某个类加载器需要加载某个.class文件时，它首先把这个任务委托给他的上级类加载器，递归这个操作，如果上级的类加载器没有加载，自己才会去加载这个类。  
BootstrapClassLoader（启动类加载器）  
c++编写，加载java核心库 java.*,构造ExtClassLoader和AppClassLoader。由于引导类加载器涉及到虚拟机本地实现细节，开发者无法直接获取到启动类加载器的引用，所以不允许直接通过引用进行操作  
ExtClassLoader （标准扩展类加载器）  
java编写，加载扩展库，如classpath中的jre ，javax.*或者java.ext.dir 指定位置中的类，开发者可以直接使用标准扩展类加载器。  
AppClassLoader（系统类加载器）  
java编写，加载程序所在的目录

## 02-23-2021: 简述堆的新生代与老年代的区别？
JVM在程序运行过程当中，会创建大量的对象，这些对象，大部分是短周期的对象，小部分是长周期的对象，对于短周期的对象，需要频繁地进行垃圾回收以保证无用对象尽早被释放掉，对于长周期对象，则不需要频率垃圾回收以确保无谓地垃圾扫描检测。为解决这种矛盾，Sun JVM的内存管理采用分代的策略。-> 分代收集算法  
新生代：又被划分为三个区域：Eden、From Survivor、To Survivor。  
大部分情况，对象都会首先在 Eden 区域分配，在一次新生代垃圾回收后，如果对象还存活，则会进入 s0 或者 s1，并且对象的年龄还会加1(Eden区 -> Survivor区后对象的初始年龄变为1)，当它的年龄增加到一定程度(默认为15岁)，就会被晋升到老年代中。

## 简述 Spring bean 的生命周期
https://www.cnblogs.com/zrtqsk/p/3735273.html 还包括了**容器的创建流程**  
1. Spring容器从XML文件中读取Bean的定义，并实例化Bean。   
2. Spring根据Bean的定义填充所有的属性。  
3. (**3~4：Aware**) 如果Bean实现了BeanNameAware接口，Spring传递Bean的ID到setBeanName()方法。 (Aware接口：当需要在普通对象中获取容器中相关的内部对象时，可以使用Aware接口)  
4. 与上面的类似，如果实现了其他 *.Aware 接口，就调用相应的方法。  
5. **Before前置增强**: 如果有任何与Bean相关联的**BeanPostProcessor**s，Spring会在postProcesserBeforeInitialization()方法内调用它们。(AOP,动态代理)  
6. 如果Bean实现InitializingBean接口，调用它的afterPropertySet()方法。  
7. 如果Bean在配置文件中的定义包含init-method属性，执行指定的方法。  
8. **After后置增强**: 如果有BeanPostProcessors和Bean关联，这些bean的postProcessAfterInitialization() 方法将被调用。(AOP,动态代理)   

    得到完整对象，context.getBean()   
    关闭容器   
    
 9. 如果Bean实现了DisposableBean接口，它将调用destroy()方法。  
 10. 当要销毁Bean的时候，如果Bean在配置文件中的定义包含destroy-method属性，执行指定的方法。

## 简述 Spring AOP 的原理
1. IOC容器得到目标代理对象：Spring AOP就是基于动态代理的，如果要代理的对象实现了某个接口，那么Spring AOP会使用JDK Proxy，去创建代理对象。而对于没有实现接口的对象，Spring AOP会使用 Cglib生成一个被代理对象的子类来作为代理。  
2. proxy调用方法触发CglibAopProxy.intercept()  
3. intercept()：获取所有的拦截器，排好序后做出拦截器链（拦截器为增强代码的包装）。传入拦截器链和目标对象，new CglibMethodInvocation()并调用proceed()  
4. proceed()先执行全部拦截器，最后执行目标方法  
5. 关键在与**拦截器invoke()方法**，Before拦截器先执行advice方法再调用proceed()，After拦截器先proceed()后执行advice方法  
6. 由于拦截器invoke()的递归调用，便出现 before -> 目标对象调用 -> after AOP执行顺序  

## 实现单例设计模式（懒汉，饿汉）
饿汉式：
```Java
public class HungrySingleton {

  private final static HungrySingleton hungrySingleton = new HungrySingleton();

  private HungrySingleton() {

  }

  public static HungrySingleton getInstance() {
    return hungrySingleton;
  }

}
```
双重检测锁模式，DCL懒汉：  
**volatile**必须加，防止test = new Test() 该句指令重排序  
1. 分派内存空间
2. 执行构造方法，初始化对象
3. 把对象指向这个空间  
1 -> 3 -> 2 导致其他线程得到一个还未完成初始化的对象  
```Java
class Test {
	public volatile static Test test;
	
	private Test() {
		System.out.println(Thread.currentThread().getName() + " is newing instance");
	}
	
	public static Test getInstance() {
		if (test == null) {
			synchronized(Test.class) {
				if (test == null) {
					test = new Test();
				}
			}
		}
		return test;
	}
	
	public static void main(String[] args) {
		for(int i = 0; i < 10; i++) {
			new Thread(() -> {
				Test.getInstance();
			}).start();
		}
	}
}
```
静态内部类：
静态内部类在使用时才加载。StaticInnerClassSingleton类在类加载时不会实例化StaticInnerClassSingleton对象，而在第一次调用getInstance()方法时，将加载静态内部类StaticInnerClass，并初始化静态成员变量staticInnerClassSingleton，由java虚拟机保证其线程安全，使得成员变量staticInnerClassSingleton只能初始化一次。且getInstance()方法没有线程锁定，因此不会影响性能  
通过这种方式实现的懒汉单例模式，既实现了延迟加载，也保证了线程安全，且不影响系统性能
```Java
public class StaticInnerClassSingleton {
 
    private StaticInnerClassSingleton(){
 
    }
 
    private static class StaticInnerClass{
        private static StaticInnerClassSingleton staticInnerClassSingleton = new StaticInnerClassSingleton();
    }
 
    public static StaticInnerClassSingleton getInstance(){
        return StaticInnerClass.staticInnerClassSingleton;
    }
}
```

## Java是如何实现线程安全的，哪些数据结构是线程安全的？
Java是如何实现线程安全的?
 - synchronized关键字
 - volatile关键字
 - 使用Atomic变量: 如AtomicInteger，使用这些类来声明变量可以保证对其操作具有原子性来保证线程安全。
 - 使用Lock
 - ThreadLocal: 如果你创建了一个ThreadLocal变量，那么访问这个变量的每个线程都会有这个变量的本地副本。
***
哪些数据结构是线程安全的?  
**HashTable，ConcurrentHashMap，CopyOnWriteArrayList，CopyOnWriteArraySet，ConcurrentLinkedQueue，Vector，StringBuffer**等  
它们的功能和应用场景参考：https://blog.csdn.net/qq_29229567/article/details/87799838

## MySQL为什么使用B+树来作索引，对比B树它的优点和缺点是什么？
B+树有读写上的性能优点，适配磁盘的访问模式。（减少磁盘读取页的寻址时间）  

mysql为什么使用B+树而不是B树作为索引？  
 - 由于mysql通常将数据存放在磁盘中，读取数据就会产生磁盘IO消耗。而B+树的非叶子节点中不保存数据，B树中非叶子节点会保存数据，通常一个节点大小会设置为磁盘页大小，这样B+树每个节点可放更多的key，B树则更少。这样就造成了，B树的高度会比B+树更高，从而会产生更多的磁盘IO消耗。
 - B+树叶子节点构成链表，更利用范围查找和排序。而B树进行范围查找和排序则要对树进行递归遍历。


## DNS 查询服务器的基本流程是什么？DNS 劫持是什么？
DNS服务器树状层次结构：
 - 根DNS服务器 :返回顶级域DNS服务器的IP地址
 - 顶级域DNS服务器:返回权威DNS服务器的IP地址（分为.com .net .cn ...）
 - 权威DNS服务器:返回相应主机的IP地址
  
DNS 解析流程
为了提高DNS的解析性能，很多网络都会就近部署DNS缓存服务器。于是，就有了以下的DNS解析流程。
1. 电脑客户端会发出一个 DNS 请求，问 www.163.com 的 IP 是啥啊，并发给本地域名服务器(本地 DNS)。那本地域名服务器(本地 DNS)是什么呢?如果是通过DHCP配置，本地 DNS 由你的网络服务商(ISP)，如电信、移动等自动分配，它通常就在你网络服务商的某个机房。
2. 本地 DNS 收到来自客户端的请求。你可以想象这台服务器上缓存了一张域名与之对应 IP 地址的大表格。如果能找到 www.163.com 它直接就返回 IP 地址。如果没有，本地 DNS 会去问它的根域名服务器:“老大，能告诉我 www.163.com 的 IP 地址吗?”根域名服务器是最高层次的，全球共有13套。它不直接用于域名解析，但能指明一条道路。
3. 根 DNS 收到来自本地 DNS 的请求，发现后缀是.com，说:“哦，www.163.com 啊，这个域名是由.com 区域管理，我给你它的顶级域名服务器的地址，你去问问它吧。”
4. 本地 DNS 转向问顶级域名服务器:“老二，你能告诉我 www.163.com 的 IP 地址 吗?”顶级域名服务器就是大名鼎鼎的比如 .com .net .org 这些一级域名，它负责管理二级域名，比如163.com，所以它能提供一条更清晰的方向。
5. 顶级域名服务器说:“我给你负责 www.163.com 区域的权威 DNS 服务器的地址，你 去问它应该能问到。”
6. 本地 DNS 转向问权威 DNS 服务器:“您好，www.163.com 对应的 IP 是啥呀?”163.com 的权威 DNS 服务器，它是域名解析结果的原出处。
7. 权威 DNS 服务器查询后将对应的 IP 地址 X.X.X.X 告诉本地 DNS。
8. 本地 DNS 再将 IP 地址返回客户端，客户端和目标建立连接。
***
DNS劫持又称域名劫持，是指在劫持的网络范围内拦截域名解析的请求，分析请求的域名，把审查范围以外的请求放行，否则返回假的IP地址或者什么都不做使请求失去响应，其效果就是对特定的网络不能反应或访问的是假网址。

## 简述 ArrayList 与 LinkedList 的底层实现以及常见操作的时间复杂度
LinkedList由双向链表实现，并包装了size、head、tail信息。  
ArrayList：
 - 通过数组实现，一旦我们实例化ArrayList无参数构造函数默认为数组初始化长度为10
 - add方法底层实现：如果增加的元素个数超过了10个，那么ArrayList底层会新生成一个数组，长度为原数组的1.5倍+1，然后将原数组的内容复制到新数组当中，并且后续增加的内容都会放到新数组当中。当新数组无法容纳增加的元素时，重复该过程。是一旦数组超出长度，就开始扩容数组。(均摊复杂度)  

## 简述 BIO, NIO, AIO 的区别

## 简述 JVM 的内存模型 JVM 内存是如何对应到操作系统内存的？

## 线程池是如何实现的？简述线程池的任务策略

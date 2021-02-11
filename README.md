# Daily-Basic-Knowledge
## 计算机网络  
[02-06-2021: 从输入 URL 到展现页面的全过程](#02-06-2021-从输入-url-到展现页面的全过程)  
[02-07-2021: TCP 协议如何保证可靠传输](#02-07-2021-tcp-协议如何保证可靠传输)  
[02-07-2021: TCP 中常见的拥塞控制算法有哪些？](#02-07-2021-tcp-中常见的拥塞控制算法有哪些)  
[02-08-2021: HTTP与HTTPS有哪些区别？（包括对称加密与非对称加密的概念）](#02-08-2021-http与https有哪些区别)  
[02-08-2021: 简述 HTTPS 的加密与认证过程](#02-08-2021-简述-https-的加密与认证过程)    
[02-08-2021: 简述TCP三次握手以及四次挥手的流程。为什么需要三次握手以及四次挥手？](#02-08-2021-简述tcp三次握手以及四次挥手的流程为什么需要三次握手以及四次挥手)  
## Java & Java框架 
[02-08-2021: HashMap(1.7, 1.8区别) 与 ConcurrentHashMap 的实现原理是怎样的？ConcurrentHashMap 是如何保证线程安全的？](#02-08-2021-hashmap-与-concurrenthashmap-的实现原理是怎样的concurrenthashmap-是如何保证线程安全的)  
[02-09-2021: hashmap 和 hashtable 的区别是什么？](#02-09-2021-hashmap-和-hashtable-的区别是什么)  
[02-08-2021: synchronized 关键字底层是如何实现的？它与 Lock 相比优缺点分别是什么？](#02-08-2021-synchronized-关键字底层是如何实现的它与-lock-相比优缺点分别是什么)  
[02-08-2021: CAS 实现原理是什么？](#02-08-2021-cas-实现原理是什么)  
[02-09-2021: volatile底层原理](#02-09-2021-volatile底层原理)    
[02-09-2021: Java 常见锁有哪些？ReetrantLock 是怎么实现的？](#02-09-2021-java-常见锁有哪些reetrantlock-是怎么实现的)  
[02-10-2021: 简述 Synchronized，volatile，可重入锁的不同使用场景及优缺点](#02-10-2021-简述-synchronizedvolatile可重入锁的不同使用场景及优缺点)  
[02-11-2021：Java 线程间有多少通信方式？](#02-11-2021java-线程间有多少通信方式)
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

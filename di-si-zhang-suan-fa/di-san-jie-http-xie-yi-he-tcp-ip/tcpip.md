## tcp/ip 传输协议

**定义：**Transmission Control Protocol/Internet Protocol的简写，中译名为传输控制协议/因特网互联协议，又名**网络通讯协议**，是Internet最基本的协议、Internet国际互联网络的基础，由网络层的**IP协议**和**传输层的TCP协议**组成

![](/assets/import.png)

1. TCP/IP参考模型的层次结构

   ![](/assets/import2.png)

TCP/IP报文格式  
1、IP报文格式

IP协议是TCP/IP协议族中最为核心的协议。它提供不可靠、无连接的服务，也即依赖其他层的协议进行差错控制。在局域网环境，IP协议往往被封装在以太网帧中传送。而所有的TCP、UDP、ICMP、IGMP数据都被封装在IP数据报中传送。如图2-3所示：

![](http://images.cnblogs.com/cnblogs_com/bluetzar/IPPackage.jpg)

```
    图2-3　 TCP/IP报文封装
```

![](/assets/import3.png)  
                                             图2-4　 IP头部格式

---

* ## TCP连接建立、释放时的握手过程

TCP会话通过三次握手来初始化。三次握手的目标是使数据段的发送和接收同步。同时也向其他主机表明其一次可接收的数据量（窗口大小），并建立逻辑连接。这三次握手的过程可以简述如下：

● **源主机**发送一个同步标志位（SYN）置1的TCP数据段。此段中同时标明初始序号（Initial Sequence Number，ISN）。ISN是一个随时间变化的随机值。

● **目标主机**发回确认数据段，此段中的同步标志位（SYN）同样被置1，且确认标志位（ACK）也置1，同时在确认序号字段表明目标主机期待收到源主机下一个数据段的序号（即表明前一个数据段已收到并且没有错误）。此外，此段中还包含目标主机的段初始序号。

● **源主机**再回送一个数据段，同样带有递增的发送序号和确认序号。

至此为止，TCP会话的三次握手完成。接下来，源主机和目标主机可以互相收发数据。整个过程可用图2-8表示。

![](/assets/import7.png)

![](/assets/import6.png)


原文地址：http://www.javaworld.com/article/2077963/open-source-tools/distributed-transactions-in-spring--with-and-without-xa.html

当习惯于使用spring中的JTA 和 XA协议实现分布式事务的时候，你也许还有其他的选择。
可选的实现方式 取决于应用使用的资源和你在性能、安全、可靠性、数据一致性方面的权衡。
在这篇JavaWorld的文章里面，SpringSource的David 引导你去看看spring实现的7种事务模式，3种是使用了XA接口的，4种是没有的

Spring框架 支持在脱离J2EE容器的情况下使用JTA和XA协议来处理分布式事务，即使这样，使用XA的代价还是很高的，使用起来还是很笨重或者不可靠；也许会发生一个乐于接受的惊喜，
因此这一类应用应该避免使用XA协议

为了帮助理解不同分布式事务的实现方式的初衷，我会解析7种事务模式，并且通过代码使他们更加具体。
在安全性、可靠性

1、通过2阶段提交的Full  XA ，如果你需要保证 在发生断电故障、包括服务宕机的时候，事务仍然能够回复，那么可以使用Full XA模式

在这种情况下用于同步事务的共享资源是一个用于协调使用XA协议的进程信息的特殊的事务管理器，从开发的角度来看，协议通过JTA中的UserTranscation接口进行暴露

2、XA 和1PC优化，事务中只是包含单个资源





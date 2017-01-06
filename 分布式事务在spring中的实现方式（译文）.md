原文地址：http://www.javaworld.com/article/2077963/open-source-tools/distributed-transactions-in-spring--with-and-without-xa.html

当习惯于使用spring中的JTA 和 XA协议实现分布式事务的时候，你也许还有其他的选择。
可选的实现方式 取决于应用使用的资源和你在性能、安全、可靠性、数据一致性方面的权衡。
在这篇javaWorld的文章里面，SpringSource的David 引导你去看看spring实现的7种事务模式，4种是使用了XA接口的，剩下的是没有使用XA接口的
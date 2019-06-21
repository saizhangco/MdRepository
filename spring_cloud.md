## 比较spring cloud和dubbo，各自的优缺点

| 特性 | Spring Cloud | Dubbo |
| :------ | ------| ------|
| 传输 | http协议传输，带宽占用比较多，使用http协议一般会使用JSON报文，消耗会更大 | 二进制传输，占用带宽更少 |
| 注册中心 | 只能使用Eureka或者自研 | 可以选择zk，Redis等多种 |
| 接口协议 | 比较自由且松散，需要有强有力的行政措施来限制接口无序升级 |  |
| 开发难度 |  | 较大，因为dubbo的jar包依赖问题，很多大型工程无法解决 |
| 维护 |  | 很久没有人维护 |
| 开发人员 | 比较容易招聘 |  |
| 系统结构 | 系统结构更简单，“注册+springmvc=springcloud” | 各种复杂的URL，protocol，register，invocation，dubbofilter，dubboSPI，dubbo序列化……炫技的成分更多一些 |
| 性能 | 网络消耗小 | 可以通过压缩、二进制、高速缓存、分段降级等方法解决 |
| 扩展性 | 自带很多监控、限流措施、但是功能可能和欧美习惯相同，国内需要进行适当改造 | 很多东西都没有，需要自己集成，如监控，日志，限流，追踪。

## Spring Cloud常用组件

| 组件名称 | 功能 | 描述 | 实现方式 |
| ------ | ------ | ------ | ------ |
| Netflix Eureka | 实现服务治理（服务注册与发现） | 由Eureka服务端和Eureka客户端组成。Eureka服务端用作注册中心。**支持集群部署**。Eureka客户端是一个java客户端，用来处理服务注册与发现。 | 在应用启动时，Eureka客户端向服务端注册自己的服务信息，同时将服务端的服务信息缓存到本地。客户端会和服务端周期性的进行心跳交互，以更新服务租约和服务信息。 |
| Netflix Ribbon | 提供客户侧的软件负载均衡算法 | Spring Cloud是一个基于HTTP和TCP的客户端负载均衡工具，它基于Netflix Ribbon实现。通过Spring Cloud的封装，可以让我们轻松地将面向服务的REST模板请求自动转换成客户端负载均衡的服务调用 | 将外界的rest调用，根据负载均衡策略转换为微服务调用。 |
| Netflix Hystrix | 断路器，保护系统，控制故障范围 | 如果单个服务出现问题，调用这个服务就会出现线程阻塞，此时若有大量的请求涌入，Servlet容器的线程资源会被消耗完毕，导致服务瘫痪。 | 服务与服务之间的依赖性，故障会传播，会对整个微服务系统造成灾难性的严重后果，这就是服务故障的“雪崩”效应。 |
| Netflix Zuul | API网关，路由，负载均衡 | 类似nginx，反向代理的功能。 | 在微服务架构中，后端服务往往不直接开放给调用端，而是通过一个API网关根据请求的URL，路由到响应的服务。当添加API网关后，在第三方调用端和服务提供方之间就创建了一面墙，这面墙直接与调用方通信进行权限控制，后将请求均衡分发给后端服务端。
| Spring Cloud Config | 分布式配置，配置管理 | SpringCloud Config提供服务端和客户端。服务器存储后端的默认实现使用git，因此它轻松支持标签版本的配置环境，已经可以访问用于管理内容的各种工具。 | 配合Spring Cloud Bus实现动态的配置更新。 |

## Eureka
![Eureka的高可用架构图](image/eureka_architecture.png "Eureka的高可用架构图")

### 参考链接
[Netflix Eureka Wike](https://github.com/Netflix/eureka/wiki "Netflix Eureka Wiki")

# Springboot 框架

## Springboot 框架梳理

### springboot配置文件

- application-dev.properties
- application-prod.properties
- application-test.properties

### springboot事件接口

- org.springframework.context.ApplicationListener
    ApplicationEnvironmentPreparedEvent
    ApplicationPreparedEvent
    ApplicationStartingEvent
    ApplicationStartedEvent
    中间会执行ApplicationRunner、CommandLineRunner接口实现类
    ApplicationReadyEvent
    ApplicationFailedEvent ?

```log
2019-12-10 18:59:14.203  INFO 84427 --- [           main] licationEnvironmentPreparedEventListener : ......ApplicationEnvironmentPreparedEvent......

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.0.0.RELEASE)

2019-12-10 18:59:24.266  INFO 84427 --- [           main] com.didispace.Application                : Starting Application on IT-C02Z163PLVDL.local with PID 84427 (/Users/saizhang/Documents/myproject/SpringBoot-Learning/Chapter2-1-2/target/classes started by saizhang in /Users/saizhang/Documents/myproject/SpringBoot-Learning/Chapter2-1-2)
2019-12-10 18:59:24.267  INFO 84427 --- [           main] com.didispace.Application                : No active profile set, falling back to default profiles: default
2019-12-10 18:59:24.293  INFO 84427 --- [           main] c.d.ApplicationPreparedEventListener     : ......ApplicationPreparedEvent......
2019-12-10 18:59:24.293  INFO 84427 --- [           main] ConfigServletWebServerApplicationContext : Refreshing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@1198b989: startup date [Tue Dec 10 18:59:24 CST 2019]; root of context hierarchy
2019-12-10 18:59:24.803  INFO 84427 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-12-10 18:59:24.816  INFO 84427 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-12-10 18:59:24.816  INFO 84427 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/8.5.28
2019-12-10 18:59:24.820  INFO 84427 --- [ost-startStop-1] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [/Users/saizhang/Library/Java/Extensions:/Library/Java/Extensions:/Network/Library/Java/Extensions:/System/Library/Java/Extensions:/usr/lib/java:.]
2019-12-10 18:59:24.874  INFO 84427 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-12-10 18:59:24.874  INFO 84427 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 581 ms
2019-12-10 18:59:24.946  INFO 84427 --- [ost-startStop-1] o.s.b.w.servlet.ServletRegistrationBean  : Servlet dispatcherServlet mapped to [/]
2019-12-10 18:59:24.949  INFO 84427 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'characterEncodingFilter' to: [/*]
2019-12-10 18:59:24.949  INFO 84427 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2019-12-10 18:59:24.949  INFO 84427 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'httpPutFormContentFilter' to: [/*]
2019-12-10 18:59:24.949  INFO 84427 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'requestContextFilter' to: [/*]
2019-12-10 18:59:25.114  INFO 84427 --- [           main] s.w.s.m.m.a.RequestMappingHandlerAdapter : Looking for @ControllerAdvice: org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@1198b989: startup date [Tue Dec 10 18:59:24 CST 2019]; root of context hierarchy
2019-12-10 18:59:25.148  INFO 84427 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
2019-12-10 18:59:25.149  INFO 84427 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2019-12-10 18:59:25.166  INFO 84427 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-12-10 18:59:25.166  INFO 84427 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-12-10 18:59:25.184  INFO 84427 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-12-10 18:59:25.265  INFO 84427 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2019-12-10 18:59:25.296  INFO 84427 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-12-10 18:59:25.299  INFO 84427 --- [           main] com.didispace.Application                : Started Application in 16.23 seconds (JVM running for 21.617)
2019-12-10 18:59:25.300  INFO 84427 --- [           main] c.d.ApplicationStartedEventListener      : ......ApplicationStartedEvent......
2019-12-10 18:59:25.300  INFO 84427 --- [           main] com.didispace.Application$DataLoader     : Loading data...
2019-12-10 18:59:25.300  INFO 84427 --- [           main] c.d.ApplicationReadyEventListener        : ......ApplicationReadyEvent......
2019-12-10 18:59:26.306  INFO 84427 --- [           main] ConfigServletWebServerApplicationContext : Closing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@1198b989: startup date [Tue Dec 10 18:59:24 CST 2019]; root of context hierarchy
2019-12-10 18:59:26.308  INFO 84427 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Unregistering JMX-exposed beans on shutdown

Process finished with exit code 0
```

### SpringBoot对SPI的支持，META-INF/spring.factories

```java
org.springframework.context.ApplicationListener=com.kenny.ApplicationEnvironmentPreparedEventListener,\
  com.kenny.ApplicationFailedEventListener,\
  com.kenny.ApplicationPreparedEventListener,\
  com.kenny.ApplicationReadyEventListener,\
  com.kenny.ApplicationStartedEventListener,\
  com.kenny.ApplicationStartingEventListener
```

### SpringBoot 2.0 新特性，配置绑定(2.0.0.RELEASE)

```log
com.kenny.foo=bar
com.kenny.database-platform=sql

com.kenny.post[0]=Why Spring Boot
com.kenny.post[1]=Why Spring Cloud

com.kenny.posts[0].title=Why Spring Boot
com.kenny.posts[0].content=It is perfect!
com.kenny.posts[1].title=Why Spring Cloud
com.kenny.posts[1].content=It is perfect too!
```

```java
ApplicationContext context = SpringApplication.run(Application.class, args);

Binder binder = Binder.get(context.getEnvironment());

// 绑定简单配置
FooProperties foo = binder.bind("com.kenny", Bindable.of(FooProperties.class)).get();
System.out.println(foo.getFoo());

// 绑定List配置
List<String> post = binder.bind("com.kenny.post", Bindable.listOf(String.class)).get();
System.out.println(post);

List<PostInfo> posts = binder.bind("com.kenny.posts", Bindable.listOf(PostInfo.class)).get();
System.out.println(posts);
```

### SpringBoot对模板引擎的支持

- Thymeleaf
- freemarker
- velocity

### Swagger2（接口文档，在线维护）

[Java效率工具之Swagger2](https://juejin.im/post/5afe490ff265da0b8c253411)

### Spring统一异常处理

### 扩展XML请求和影响的支持

```java
@PostMapping(value = "/user", consumes = MediaType.APPLICATION_XML_VALUE, produces = MediaType.APPLICATION_XML_VALUE)
```

### 使用JdbcTemplate

### 使用LDAP来统一管理用户信息

### 使用Spring-data-jpa简化数据访问层

```maven
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.1.21</version>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
```

- 实体类上标记@Entity
- 主键属性上标记@Id、@GeneratedValue
- 普通属性上标记@Column(nullable = false)

### 多数据源配置，JdbcTemplate

### 多数据源配置，Spring-data-jpa

### 使用NoSQL，Redis

### 使用NoSQL，MongoDB

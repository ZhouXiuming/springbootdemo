# springboot 入门学习

## Spring Boot 概述

首先，Spring Boot是一个框架，主要理念就是消除项目中大量的配置文件，约定胜于配置。使项目更加短小精悍。我们知道 java 的开发显得很笨重：繁多的配置、开发效率低下、复杂的布署流程以及第三方技术集成难度大。所以说，spring boot就是在此环境下产生的。

## Spring Boot 的核心功能
1. 独立运行的Spring 项目  
Spring Boot 可以以jar包的形式独立运行，运行一个Spring Boot 项目只需要通过 java -jar xx.jar 来运行。
2. 内嵌Servlet 容器  
Spring Boot 可以选择内嵌Tomcat、Jetty或Undertow，这样我们无须以war包形式部署项目。
3. 提供starter简化Maven 配置  
Spring 提供了一系列的starter pom 来简化Maven 的依赖加载。
4. 自动配置Spring  
Spring Boot 会根据在类路径中的jar包、类，为jar包里的类自动配置Bean，这样会极大地减少我们要使用的配置。Spring Boot只考虑了大多数的场景，并不是所有的场景。
5. 准生产的应用监控  
Spring Boot 提供基于http、ssh、telnet对运行时的项目进行监控。
5. 无代码生成和xml配置  
Spring Boot不是借助代码生成来实现的，而是通过条件注解来实现的，这是spring 4.x的新特性。Spring 4.x提倡使用Java配置和注解配置组合，而Spring Boot不需要任何xml配置即可实现Spring 的所有配置。

## Spring Boot 的优缺点
### Spring Boot优点：
1. 快速构建；
2. 对主流开发框架的无配置集成；
3. 独立运行，无须外部依赖Servlet容器；
4. 运行时的应用监控；
5. 开发效率、部署效率；
6. spring cloud天然集成。

### Spring Boot缺点：
1. 中文书籍文档较少；


## 学习网站

1. 英文官网 https://spring.io/projects/spring-boot  
2. 中文翻译 http://spring.cndocs.ml/  https://springcloud.cc/  https://www.breakyizhan.com/springboot/3028.html
3. Github https://github.com/spring-projects/spring-boot
4. https://github.com/aalansehaiyang/technology-talk
5. https://github.com/aalansehaiyang/SpringBoot-Learning


## 最新版本
   * 2.1.0     GA  CURRENT   https://docs.spring.io/spring-boot/docs/current/reference/html/
   *  2.1.1   
   *  2.0.7   
   *  2.0.6   
   *  1.5.18   
   *  1.5.17  GA  

## 系统要求
Spring Boot 2.1.0.RELEASE requires Java 8 or 9 and Spring Framework 5.1.2.RELEASE or above.

Explicit build support is provided for the following build tools:

| Build Tool | Version | 
| ------ | ------ | 
| Maven |3.3+|
| Gradle|4.4+|


## 容器支持 Servlet Containers
Spring Boot supports the following embedded servlet containers:

| Name	| Servlet Version| 
| ------ | ------ | 
| Tomcat 9.0| 4.0| 
| Jetty 9.4| 3.1| 
| Undertow 2.0| 4.0| 

You can also deploy Spring Boot applications to any Servlet 3.1+ compatible container.



## Maven安装与配置
   https://www.cnblogs.com/eagle6688/p/7838224.html

 ```
   mvnw spring-boot:run
   mvnw clean package
   java -jar target/gs-securing-web-0.1.0.jar 
   java -jar target/myproject-0.0.1-SNAPSHOT.jar   
   
   curl localhost:8080

 ```

## sqljdbc4 sqlserver mvn 安装
   https://www.cnblogs.com/pangguoming/p/7246241.html

   mvn install:install-file -Dfile=sqljdbc4-4.0.jar -Dpackaging=jar -DgroupId=com.microsoft.sqlserver -DartifactId=sqljdbc4 -Dversion=4.0
   
## 构建 spring boot项目
使用Intellij中的Spring Initializr来快速构建Spring Boot/Cloud工程

## spring-boot 配置 与自定义配置
application.properties

 ```
com.rongzi.microservice.content.name=程序猿DD
com.rongzi.microservice.title=Spring Boot教程
 ```

 ```
 @Value("${com.rongzi.microservice.content.name}")注解

 ```

### application.properties 文件和 application.yml
     树状结构

### application.yml application.properties 优先级
    application.yml 优先加载
    application.properties 后加载，会覆盖yml的相同配置

### 多套环境的配置方法 开发 qa 生产
 ```
spring:
  profiles:
    active: prod 
     ```
     application_prod.yml
     application_dev.yml,
     application_bat.yml

   启动的时候也可以设置 Java -jar xxxxxx.jar spring.profiles.actiove=prod

## spring-boot 注解 与自定义注解
  1. @SpringBootApplication
  2. @Configuration
  3. @ComponentScan
  4. @Autowired
  5. @GetMapping
  6. @requestMapping
  7. @RestController
  8. @Service

  9. @Api @ApiOperation
  10. @ApiImplicitParams @ApiImplicitParam


## Security 安全
   spring mvc 用的比较多，略
   https://spring.io/guides/gs/securing-web/   


## lombok 代码简化与优雅
   http://projectlombok.org/features/index
   https://www.jianshu.com/p/b7094a0f6ebe

    
## configration processor
    https://docs.spring.io/spring-boot/docs/2.1.0.RELEASE/reference/htmlsingle/#configuration-metadata-annotation-processor

## session 会话
   使用redis 持久化 session
   https://blog.csdn.net/niugang0920/article/details/79644842

   pom.xml配置
   
 ```
      <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-data-redis</artifactId>
      </dependency>
      <dependency>
      <groupId>org.springframework.session</groupId>
      <artifactId>spring-session-data-redis</artifactId>
      </dependency>
```

## 集成 log4j
sprongboot使用的默认日志框架是Logback

https://blog.csdn.net/V_Come_On/article/details/79408773

grep-console 彩色日志

## 集成 redis

https://www.cnblogs.com/zeng1994/p/03303c805731afc9aa9c60dbbd32a323.html
https://blog.csdn.net/plei_yue/article/details/79362372
https://blog.csdn.net/gfd54gd5f46/article/details/78606062

redisTemplate
StringRedisTemplate

## 集成 Elasticsearch 

https://github.com/spring-projects/spring-data-elasticsearch/wiki/Spring-Data-Elasticsearch---Spring-Boot---version-matrix
https://www.cnblogs.com/technologykai/p/9202801.html
https://blog.csdn.net/weixin_39835887/article/details/84103715

## 集成 Swagger2


## 集成 AOP 面向切面编程
   https://www.cnblogs.com/aston/p/7257657.html

## 集成 cache

  https://www.cnblogs.com/yueshutong/p/9381540.html


## 集成 邮件


## 集成 MyBatis 


## 集成常用工具类，如 Copiers、CsvUtils、DateUtils


## 全局异常捕获
http://www.cnblogs.com/topfish/p/9573635.html

## Druid 介绍及配置
   源码： https://github.com/alibaba/druid
   Druid是Java语言中最好的数据库连接池。Druid能够提供强大的监控和扩展功能。

   介绍：https://www.cnblogs.com/niejunlei/p/5977895.html

## Retry 重试机制
https://www.cnblogs.com/EasonJim/p/7684649.html
https://www.jianshu.com/p/314059943f1c
https://www.cnblogs.com/zgghb/p/7828069.html

@EnableRetry
@Retryable(RemoteAccessException.class)
@Retryable(value = { RemoteAccessException.class }, maxAttempts = 3, backoff = @Backoff(delay = 5000l, multiplier = 1))

## 异步

  @EnableAsync
  Application

  @Async
  Controller
  @Async

  https://blog.csdn.net/v2sking/article/details/72795742


## springboot+mybatis 集成多数据源 MySQL/Oracle/SqlServer
## spring-boot-starter-aop 面向切面编程
## spring-boot-starter-data-jpa  持久化规范
    JPA(Java Persistence API)是Sun官方提出的Java持久化规范。
     https://blog.csdn.net/zmx729618/article/details/80771871


# Spring-boot-starter 详解
  https://www.jianshu.com/p/2093dd0168b9


## mapper https://github.com/abel533/Mapper  暂时不考虑


## pagehelper 分页插件

 
## mybatis-generator
## mybatis-generator-gui
  https://github.com/zouzg/mybatis-generator-gui
# Spring Boot Admin  1.5.5
## 1.搭建 Spring Admin项目
```xml
<dependencies>
    <dependency>
            <groupId>de.codecentric</groupId>
            <artifactId>spring-boot-admin-server</artifactId>
            <version>${admin.version}</version>
        </dependency>
        <dependency>
            <groupId>de.codecentric</groupId>
            <artifactId>spring-boot-admin-server-ui</artifactId>
            <version>${admin.version}</version>
        </dependency>
</dependencies>
```
## 2.配合 eureka 使用
```properties
eureka.instance.leaseRenewalIntervalInSeconds=10
eureka.client.registryFetchIntervalSeconds=5
# eureka 注册中心地址
eureka.client.serviceUrl.defaultZone=http://192.168.206.208:8888/eureka/
```
## 2.整合了 Spring Security 及 server-ui-login 
```properties
# 关闭原有的 basic 认证
management.security.enabled=false
# 用户名密码
security.user.name=admin
security.user.password=admin
security.basic.enabled=false
```
```xml
<!-- 集成 Spring Security-->
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-security</artifactId>
    </dependency>
    
    <!-- ui -->
    <dependency>
        <groupId>de.codecentric</groupId>
        <artifactId>spring-boot-admin-server-ui-login</artifactId>
        <version>${admin.version}</version>
    </dependency>
</dependencies>
```
## 3.客户端使用
- 添加配置文件
```properties
# 配置Admin Server的地址
spring.boot.admin.url=http://localhost:8000
# 集成 SpringSecurity 之后需要配置用户名密码
spring.boot.admin.username=admin
spring.boot.admin.password=admin
#false 关闭安全验证
management.security.enabled=false
# 开启actuator 全部端点权限
endpoints.sensitive=false
```
- 增加 maven 依赖,项目基于 SpringCloud  Dalston.SR5 版本,Spring Boot 版本 1.5.9.RELEASE ，对应 Spring Boot Admin 版本 1.5.5 
```xml
<dependency>
    <groupId>de.codecentric</groupId>
    <artifactId>spring-boot-admin-starter-client</artifactId>
    <version>1.5.5</version>
</dependency>
```
- 客户端增加日志实时显示
```properties
#添加开启admin的日志实时监控,配置地址为 logback 对应日志位置
logging.file=/data/logs/omni-trade/omni-trade-adaptation-service/console.log
```

## TODO ...

## 参考资料：
- admin 1.x : https://www.jianshu.com/p/8e43726cc7cd
- admin 1.x : https://www.cnblogs.com/duanxz/p/9559385.html
- admin 2.x : https://juejin.im/post/5c774737e51d4539982f3f6e#heading-23
- 日志刷新： https://my.oschina.net/sean1989/blog/1519498
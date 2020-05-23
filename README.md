# Spring Boot Admin 
## 1.监控 Spring Cloud 项目
## 2.整合了 Spring Security 及 server-ui-login 
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

## TODO ...

## 参考资料：
- https://www.jianshu.com/p/8e43726cc7cd
- https://www.cnblogs.com/duanxz/p/9559385.html
- https://juejin.im/post/5c774737e51d4539982f3f6e#heading-23
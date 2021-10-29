# Spring Boot



###  1.1、微服务

+ 微服务是一种架构风格
+ 一个应用被拆分成多个小服务
+ 每个服务都运行在自己的进程内，也就是可以独立部署和升级
+ 服务之间使用轻量级HTTP交互
+ 服务围绕业务功能拆分
+ 可以由全自动部署独立部署
+ 去中心化，服务自治。服务可以使用不同的语言，不同的技术

### 1.2、 分布式

+ 远程调用

+ 服务发现

+ 负载均衡

+ 服务容错

+ 配置管理

+ 服务监控

  



## 问题



##### 打开后直接退出

没有web依赖

~~~java
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

~~~





# Spring Security

##### 排除SecurityAutoConfiguration 使得不再拦截请求

~~~java
@SpringBootApplication(exclude={SecurityAutoConfiguration.class})
~~~

##### 配置密码

~~~java

@Configuration
@EnableWebSecurity
public class MyWebSecurityConfig extends WebSecurityConfigurerAdapter {

    @Override
    public void configure(AuthenticationManagerBuilder auth) throws Exception {
        PasswordEncoder pe = PasswordEncoder();
        auth.inMemoryAuthentication()
                .withUser("admin")
                .password(pe.encode("123456"))
                .roles();
    }
    @Bean
    public PasswordEncoder PasswordEncoder (){
        return new BCryptPasswordEncoder();
    }
}

~~~



> 报错  java.lang.IllegalArgumentException: There is no **PasswordEncoder** mapped for the id "null"

密码必须加密


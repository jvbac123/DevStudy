# Spring Boot





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


### SpringMVC

SpringMVC是基于Spring的一个框架，专门用于Web开发

#### 配置Web解析

~~~ xml
        <servlet>
            <servlet-name>SpringMVC</servlet-name>
            <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
            <!-- Springmvc默认配置文件路径为 WEB-INF/SpringMVC-servlet.xml -->
            <init-param>
                <param-name>contextConfigLocation</param-name>
                <param-value>classpath:SpringMVC-servlet.xml</param-value>
            </init-param>
        </servlet>
        <servlet-mapping>
            <servlet-name>SpringMVC</servlet-name>
            <url-pattern>*.do</url-pattern>
<!--            使用“/”如果不放行其他路径将被拦截-->
<!--            <url-pattern>/</url-pattern>-->
        </servlet-mapping>
~~~

#### 控制器 Controller

##### 简单实例

~~~java
package com.jvbac.mishop.controller;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.servlet.ModelAndView;

@Controller
public class MainController
{
    @RequestMapping("/show.do")
    public ModelAndView login(){
        System.out.println("Show");
        ModelAndView mv = new ModelAndView();
        mv.addObject("msg","ok");
        mv.setViewName("/WEB-INF/jsp/show.jsp");
        return mv;
    }
}

~~~

##### 返回值

###### ModelAndView

若处理器方法处理完后，需要跳转到其它资源，且又要在跳转的资源间传递数据，此时处理器方法返回ModelAndView 比较好。

###### String

用于返回指定逻辑视图名称 ，但不涉及数据传递，可以用String，类似于404页面 公共的

#### 常见问题

+ 进入控制器页面 控制台不报错但是页面显示404

  springmvc.xml没有配置扫描包

  ~~~xml
  <context:component-scan base-package="${base-package}" />
  ~~~

  


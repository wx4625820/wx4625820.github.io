---
title: bean与component的区别
date: 2019-04-20 18:47:52
tags:
---
![](http://posw9yxeh.bkt.clouddn.com/images/common/gratisography-157-thumbnail-small.jpg)
                                <!-- more -->
首先我们看看这两个注解的作用：
* @Component注解表明一个类会作为组件类，并告知Spring要为这个类创建bean。
* @Bean注解告诉Spring这个方法将会返回一个对象，这个对象要注册为Spring应用上下文中的bean。通常方法体中包含了最终产生bean实例的逻辑。

两者的目的是一样的，都是注册bean到Spring容器中。
@Component（@Controller、@Service、@Repository）通常是通过类路径扫描来自动侦测以及自动装配到Spring容器中，而@Bean注解通常是我们在标有该注解的方法中定义产生这个bean的逻辑。
举个例子：
```Java
@Controller
//在这里用Component，Controller，Service，Repository都可以起到相同的作用。
@RequestMapping(″/web/controller1″)
public class WebController {
    .....
}
```
而@Bean则更加灵活，当我们引用第三方库中的类库需要转配到Spring容器时，则只能通过@Bean实现。
举个例子
```Java
@Bean
public OneService getService(status) {
    case (status)  {
        when 1:
                return new serviceImpl1();
        when 2:
                return new serviceImpl2();
        when 3:
                return new serviceImpl3();
    }
}
```
以上这个例子是无法用Component以及其具体实现注解（Controller、Service、Repository）来实现的。
总结：@Component和@Bean都是用来注册Bean并装配到Spring容器中，但是Bean比Component的自定义性更强。可以实现一些Component实现不了的自定义加载类。

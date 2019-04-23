---
title: jar包和war包的区别
date: 2019-04-22 14:54:06
tags: 打包
categories: Java
---
![](http://pouz2irgz.bkt.clouddn.com/
gratisography-plam-trees-summer.jpg)
gratisography-plam-trees-summer.jpg)
<!-- more -->
1. JAR（Java Archive，Java归档文件）是与平台无关的文件格式，它允许将许多文件组合成一个压缩文件。
>JAR 文件格式以流行的 ZIP 文件格式为基础。与 ZIP 文件不同的是，JAR 文件不仅用于压缩和发布，而且还用于部署和封装库、组件和插件程序，并可被像编译器和JVM这样的工具直接使用。在JAR中包含特殊的文件，如manifests和部署描述符，用来指示工具如何处理特定的JAR。简单来说，jar包就是别人已经写好的一些类，然后对这些类进行打包。可以将这些jar包引入到你的项目中，可以直接使用这些jar包中的类和属性，这些jar包一般放在lib目录下。
2. war是一个可以直接运行的web模块，通常用于网站，打成包部署到容器中。以Tomcat来说，将war包放置在其\webapps\目录下，然后启动Tomcat，这个包就会自动解压，就相当于发布了。
>war包是Sun提出的一种web应用程序格式，与jar类似，是很多文件的压缩包。war包中的文件按照一定目录结构来组织。根据其根目录下包含有html和jsp文件，或者包含有这两种文件的目录，另外还有WEB-INF目录。通常在WEB-INF目录下含有一个web.xml文件和一个classes目录，web.xml是这个应用的配置文件，而classes目录下则包含编译好的servlet类和jsp，或者servlet所依赖的其他类（如JavaBean）。通常这些所依赖的类也可以打包成jar包放在WEB-INF下的lib目录下。简单来说，war包是JavaWeb程序打的包，war包里面包括写的代码编译成的class文件，依赖的包，配置文件，所有的网站页面，包括html，jsp等等。一个war包可以理解为是一个web项目，里面是项目的所有东西。
3. 区别：（WAR文件代表了一个Web应用程序，JAR是类的归档文件。）
>如果一个Web应用程序的目录和文件非常多，那么将这个Web应用程序部署到另一台机器上，就不是很方便了，这时可以将Web应用程序打包成Web 归档（WAR）文件，这个过程和把Java类文件打包成JAR文件的过程类似。利用WAR文件，可以把Servlet类文件和相关的资源集中在一起进行发布。在这个过程中，Web应用程序就不是按照目录层次结构来进行部署了，而是把WAR文件作为部署单元来使用。

#### 总结：虽然WAR文件和JAR文件的文件格式是一样的，并且都是使用jar命令来创建，但就其应用来说，WAR文件和JAR文件是有根本区别的。JAR文件的目的是把类和相关的资源封装到压缩的归档文件中，而对于WAR文件来说，一个WAR文件代表了一个Web应用程序，它可以包含 Servlet、HTML页面、Java类、图像文件，以及组成Web应用程序的其他资源，而不仅仅是类的归档文件。














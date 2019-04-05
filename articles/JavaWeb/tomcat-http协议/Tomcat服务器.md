**Tomcat是Apache 软件基金会（Apache Software Foundation）的Jakarta 项目中的一个核心项目，由[Apache](https://baike.baidu.com/item/Apache/6265)、Sun 和其他一些公司及个人共同开发而成。由于有了Sun 的参与和支持，最新的Servlet 和JSP 规范总是能在Tomcat 中得到体现，Tomcat 5支持最新的Servlet 2.4 和JSP 2.0 规范。因为Tomcat 技术先进、性能稳定，而且免费，因而深受Java 爱好者的喜爱并得到了部分软件开发商的认可，成为目前比较流行的Web 应用服务器。**
接下来，我们需要使用这个Tomcat服务器，必须要先从它的官网获取它!

### 下载安装tomcat
#### 如何下载和安装tomcat服务器
1. 下载安装

   apache官网：https://www.apache.org/

   tomcat：https://tomcat.apache.org/

   ![Apache Tomcat官网首页](https://i.loli.net/2019/03/19/5c90850839da2.jpg)

根据需求下载相应的版本，并解压

#### tomcat目录介绍

![](https://i.loli.net/2019/03/19/5c9085ad0c2e9.jpg)

1. **bin:启动和关闭命令**

   注意四个重要的文件：***startup.bat、startup.sh、shutdown.bat、shutdown.sh***

   ***startup.bat:***  windows下启动

   ***startup.sh:*** linux下在bin目录通过命令脚本： ***./startup.sh***或者***sh startup.sh***启动服务

   ***shutdown.bat:***windows下关闭

   ***shutdown.sh：***linux下在bin目录通过命令脚本： ***./shutdown.sh***或者***sh shutdown.sh***启动服务

2. **conf:配置文件**



#### 配置环境变量

Tomcat软件运行它需要依赖Java的运行环境。需要在电脑中配置JAVA_HOME环境变量。

注意:`jdk`和`tomcat`要对应版本，太高和太低的搭配会出现不兼容的问题

我的公司电脑采用以下两种搭配方式，根据需要在8和6两个版本之间切换，且JAVA_HOME和CATALINA_HOME同时切换

JAVA_HOME   	  = `%JAVA6_HOME%`           or   JAVA_HOME = `%JAVA8_HOME%` 
CATALINA_HOME    = `%CATALINA6_HOME%`  or   CATALINA_HOME = `%CATALINA8_HOME%`

`tomcat8.5`-`jdk1.8`

`tomcat6`-`jdk1.6` 

#### 启动服务器

- 进入tomcat的安装目录中，在bin目录下有startup.bat文件，双击运行???
- dos命令：进入bin目录，然后运行批处理文件： `D:\javahtc\apache-tomcat-8.5.0\bin\startup.bat`

**注**：

- `startup/startup.bat`均可启动tomcat,`shutdown/shutdown.bat`均可结束tomcat进程
- Tomcat启动之后，不要关闭，关闭了就不能访问了！

DOS命令如下：

![启动tomcat](https://i.loli.net/2019/03/19/5c9089cc5f01d.jpg)

#### 测试

打开浏览器在，在浏览器的地址栏中输入：

` http://127.0.0.1:8080`

` http://localhost:8080`

 注意：`localhost`相当于`127.0.0.1`

效果：

![tomcat服务启动首页](https://i.loli.net/2019/03/19/5c9088512ffdf.jpg)

#### 结束tomcat进程

![结束tomcat进程](https://i.loli.net/2019/03/19/5c908a41e0e39.jpg)





#### tomcat服务器使用常见问题

参考：https://www.cnblogs.com/godtrue/p/4339045.html

**问题1**：上述启动命令是进入bin目录下直接执行`stratup.bat`，或者给系统一个路径`D:\javahtc\apache-tomcat-8.5.0\bin\startup.bat`来执行，不能在其他路径启动tomcat

解决：

1. 首次运行startup.bat的情况（`startup.bat/startup`）

![](https://i.loli.net/2019/03/19/5c90a0005f35d.jpg)

2. 配置对应的系统环境变量--Path

```
path				
%CATALINA_HOME%\bin;
%JAVA_HOME%\bin;
C:\Program Files (x86)\Common Files\Oracle\Java\javapath;
C:\ProgramData\Oracle\Java\javapath;
%SystemRoot%\system32;
%SystemRoot%;
%SystemRoot%\System32\Wbem;
%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\;
C:\Users\ks08pc23\AppData\Local\Programs\Python\Python36;
C:\Program Files (x86)\Canon\Easy-WebPrint EX\bin;
```

3. 配置CATALINA_HOME环境变量-之前已经配置过，现在单独拿出来（以tomcat8为例）

   ```
   变量    		   值
   CATALINA_HOME   %CATALINA8_HOME%
   CATALINA8_HOME  D:\javahtc\apache-tomcat-8.5.0
   ```

4. 配置好后测试

![](https://i.loli.net/2019/03/19/5c90a27690993.jpg)



**问题2**：DOS命令按照上述命令可以再任意在任意路径启动tomcat，但是直接双击startup.bat执行，tomcat的窗口仍然一闪而过

解决：

1. 对`startup.bat`进行编辑，在最后添加pause后调试看报什么错误？？？



#### Tomcat启动小结

- tomcat软件运行它需要依赖Java的运行环境。需要在电脑中配置JAVA_HOME环境变量

- tomcat的启动：dos命令下直接给出bin路径,或者配置Path系统变量，以使在任意路径通过startup直接启动

- tomcat需要配置CATALINA_HOME环境变量

- 目前我的电脑上有`tomcat 6`和`tomcat8`，`jdk1.6` 和`jdk1.8`,经过测试:

  - `tomcat6`配合`jdk1.8`可以正常启动

  ![](https://i.loli.net/2019/03/19/5c90a82a2978f.jpg)

  - `tomcat8`配合`jdk1.7`正常启动
  - ![](https://i.loli.net/2019/03/19/5c90acdd66e27.jpg)
  - `tomcat8`配合`jdk1.6`启动不了，说明jdk1.6不支持tomcat8

![](https://i.loli.net/2019/03/19/5c90aa0b468a9.jpg)









### 修改端口和web资源（项目）发布

#### 修改端口

Tomcat服务器的`配置`，全部都需要在tomcat的安装目录下`conf`目录下完成,修改端口编辑`conf`目录下的`server.xml`

tomcat的**默认端口**为`8080`

```
<Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
```

修改tomcat的端口为8088，修改完`server.xml`文件必须重启服务器才能有效。    

通过浏览器的地址栏访问：http://localhost:8080

![](https://i.loli.net/2019/03/20/5c919d4a28885.jpg)

#### 项目(web资源)发布

##### 在`webapps`下面直接发布

重要：只需要把开发好的**项目复制到`webapps`下面即可**。这时不用重启tomcat服务器，**tomcat服务器会自动的加载复制到`webapps`下面的所有项目资源**。

***使用普通文件夹发布资源:***

1.创建test文件夹

![](https://i.loli.net/2019/04/02/5ca2f8210528c.jpg)

2.创建一个`html`文件`1.html`,内容为“Hello Tomcat”



![](https://i.loli.net/2019/04/02/5ca2f8d457742.jpg)

3.Tomcat窗口：

![](https://i.loli.net/2019/04/02/5ca301f241b0a.jpg)

4.通过浏览器地址栏访问:

http://localhost:8080/test/1.html  或 http://127.0.0.1:8080/test/1.html

![](https://i.loli.net/2019/04/02/5ca2f9a0c7a73.jpg)

4.访问过程：

 http://127.0.0.1:8080/test/1.html

`http`:协议名称

`127.0.0.1`：	       本机`IP`，`localhost`=`127.0.0.1`）

`8080`:端口号		Tomcat服务器的8080端口

`test`:	   	         `webapps`下的test文件夹(apache-tomcat-8.0.9\webapps\test)

`1.html`:			test目录下的`html`文件

***使用压缩包发布项目，把压缩包发布到`webapps`下面:***

原因：直接复制，数据量大，文件多，管理不方便

**使用.war****发布好处**： **

- 文件在一个文件夹统一管理，数据进行压缩，数据量小
- .war文件可以被tomcat自动解压，直接访问就可以获取资源。

1. 新建文件夹`test2` ,并创建`2.html`
2. 将工程使用zip格式压缩，然后更改后缀名为 war
3. 把war包复制到`wabapps`面（注意只复制war文件）,如果不能自动生成，请重启服务器

 ![](https://i.loli.net/2019/04/02/5ca2ff0770a82.jpg)

4.自动生成的test2文件夹

![](https://i.loli.net/2019/04/02/5ca3005f20c88.jpg)

5.Tomcat窗口：

![](https://i.loli.net/2019/04/02/5ca3046156464.jpg)

6.访问：

http://localhost:8080/test2/test2/2.html

![](https://i.loli.net/2019/04/02/5ca30a6fa1260.jpg)





### Eclipse集成tomcat和开发web项目

#### Eclipse集成tomcat(重点)

1.Eclipse->preferences->server

![](https://i.loli.net/2019/04/02/5ca30b4623dcb.jpg)

![](https://i.loli.net/2019/04/02/5ca30c26db860.jpg)

2.填上tomcat名称、tomcat所在目录、运行的jdk版本

![](https://i.loli.net/2019/04/02/5ca30cd86cfc3.jpg)

3.调出server 视图

![](https://i.loli.net/2019/04/02/5ca30da15868d.jpg)

4.服务器配置完成

![](https://i.loli.net/2019/04/02/5ca30e1a2cf99.jpg)

5.配置tomcat信息

注意：

- 如果设置是灰色界面，先要卸载tomcat里的项目
- 设置完一定别忘了 `ctrl + s` 保存

![](https://i.loli.net/2019/04/02/5ca3127896aef.jpg)

6.启动服务器

![](https://i.loli.net/2019/04/02/5ca31479592f2.jpg)



#### Eclipse创建web项目（写代码，在服务器可以执行）

注意：

dynamic web module version 2.5与3.0的主要区别：

首先要说的是 

1. 这里的版本 值得是`Servlet`的版本；
2. 如果你本地`jdk`的版本 >= 1.7才会有3.0选项，并且默认为3.0；

主要区别：

1. 选择2.5的时候，会默认勾选创建`web.xml`文件，而3.0需要在下下一步中手动勾选
2. 选择2.5的时候，如果新建了`Servlet`文件，需要在`web.xml`文件中进行配置，而3.0版本在新建`Servlet`文件时会自动加上注解，不在需要额外的配置。

后续再研究研究。。。。。。

![](https://i.loli.net/2019/04/02/5ca31707cb1d6.jpg)



#### 项目目录介绍

![](https://i.loli.net/2019/04/02/5ca31da13839b.jpg)

新建一个`html`页面并发布到tomcat上,对外发布资源

![](https://i.loli.net/2019/04/02/5ca320a1a0973.jpg)

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>Insert title here</title>
</head>
<body>
<h1><a href="http://www.baidu.com">百度</a></h1>
</body>
</html>
```

启动服务器访问：

![](https://i.loli.net/2019/04/02/5ca32150a4e11.jpg)

#### 使用eclipse将项目发布到tomcat都做了那些事呢？

1. `elipse` 会把**`src`**中`java`文件编译成class文件,放到 `WebRoot`(同`WebContent`) /WEB-INF/classes 目录下.
2. `eclipse`将`WebRoot`(同`WebContent`) 复制粘贴到`tomcat/webapps`目录下, 并且将 `WebRoot` 改名为 项目名(如test).
3. 待续。。。。。。。。。


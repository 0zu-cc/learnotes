# 一、入门小结(前后端不分离)

### <font color=#69bad9>1.框架标准结构</font>
<u>基本</u>:<br>
　　a.**控制层controller**,负责和前端交互,进行逻辑判断,返回字符串(API结果)<br>
　　b.**服务层service**,负责写业务逻辑,实现具体功能并返回结果.如果项目较大或需要多种实现,建议在service包下单独用impl包实现.

　　c.**实体类entity**<br>
　　实体类叫法因习惯而异,常见的有:pojo简单JavaBean(区别于EJB企业JavaBean),domain,bean  
　　主要分为:PO持久层对象,DTO传输层对象,VO视图层对象,DO数据对象,AO应用对象,(BO业务对象)<br>
　　d.**数据访问层dao(data access)**<br>
　　两种叫法:dao/mapper,类名规范为entity类名+Mapper<br>

>工具类utils　　配置类config　　异常类exception　　 拦截器interceptor　　过滤器filter　　常量类constant

　　最简单的目录结构:<br>![入门目录](../../Img/SpringBootStructure.png)

### <font color=#69bad9>2.涉及工具</font>
a.SpringBoot　　b.Lombok　　c.MySQL8.0　　d.Mybatis　　e.Maven　　f.H5

### <font color=#69bad9>3.基本知识</font>
-   springboot的默认启动页面为index.html,没有名为index.html的文件,访问路径localhost:8080就会白页报错.
-   test是单元测试(JUnit)文件夹,pom.xml是配置文件(依赖引入文件).
-   web应用的配置尽量用application.yml
-   如果引入thymeleaf模板,html文件放在templates文件夹下,css/js/image放在static文件夹下.没有引入全部放static文件夹

### <font color=#69bad9>4.SpringBoot的相关思想</font>
a.IoC控制反转(Inversion of Control)　　b.AOP面向切面编程(Apect Oriented Programming)

### <font color=#69bad9>5.SpringBoot做的几件事</font>
A.封装**Servlet**容器(默认tomcat,可自行替换成jetty)  
B.自动配置Spring相关文件,无需web.xml  
C.SpringBoot和Django/Flask(pyWeb框架)一样,都是关于某种语言的wbe框架

### <font color=#69bad9>6.相关工具</font>
A.**Maven**:jar包/依赖导入和管理工具,负责统一管理需要的<mark>外部文件(压缩包)</mark>  
B.**Tomcat**:SpringBoot默认集成Tomcat(tomcat需了解)  
C.**VCS**(Version Control System)  
　分类:LVCS(Local),CVCS(Centralized),DVCS(Distributed)  
　L:本地,很少用于协作  
　C:集中式,典型代表CVS,Subversion(SVN),Perforce  
　D:分布式,典型代表**Git**,Mercurial,Bazzar,Darcs  
　此外还有很多专用的付费VCS

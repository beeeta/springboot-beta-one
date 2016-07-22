# spring boot 笔记-项目构建 


this is a spring boot demo project

https://github.com/beeeta/springboot-beta-one.git
## 命令行建立项目

1. 安装jdk,eclipse,mvn。然后
做好相应的环境变量配置:/etc/profile 环境变量配置
something like:

````shell
export GOROOT=/usr/local/go
export SPRING_HOME=/usr/local/spring-1.3.0.BUILD-SNAPSHOT
export PATH=$SPRING_HOME/bin:/usr/local/apache-maven-3.3.9/bin:$GOROOT/bin:$PATH
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
`````
2. source /etc/profile :刷新编辑的配置项，使其立即生效
3. 编辑app.groovy文件  并用 spring run app.groovy执行

## eclipse创建项目

1. 创建mvn项目
2. 引入pom.xml配置文件
3. 创建java源代码
4. 应为spring boot 项目内嵌了tomcat,讲项目直接以本地应用的方式启动即可

## 将项目打包为jar

pom.xml需要增加构建插件

~~~~~ shell

<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>

~~~~~~

遇到的一个问题：
当JAVA_HOME指向jdk目录时，在命令窗口执行 mvn package 会报错，错误大概的意思是你是不是把java_home配置成了jre目录而不是jdk目录？

事实上，是写反了，这个错误的原因是有一些lib目录下的jar包没有加载到，而lib目录是在jre目录下的。
所以当修改JAVA_HOME执行jre目录的时候，就正常了。

这样在target目录下会生成一个可执行的jar文件，方便微服务化的部署。

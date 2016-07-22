# spring boot 笔记-项目构建 

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


#遇到关于gradle的一些tips

### speed up your build 
- org.gradle.daemon = true
- org.gradle.parallel = true
- set proxy 
- org.gradle.jvmargs=-Xmx6114m -XX\:MaxPermSize\=2048m


daemon设置对本机有效，如果是build服务器可能反而会导致build速度减慢。

parallel设置的话需要保证task执行之间的时序，可以用task的dependOn来设置，或者mustRunAfter

设置代理同样可以加速或者降低拉取依赖的速度。


### 2016-05-06
近期在做一个对文件夹中的某些文件进行签名的task，需要对文件夹中文件循环读取，并且对每个文件进行签名，用到了[task的循环](https://github.com/tonyzzz/Gradle/blob/master/loopTask.gradle)。
> python的standardOutput和errorOutput太坑了。。。
> 


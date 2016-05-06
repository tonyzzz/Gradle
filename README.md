#遇到关于gradle的一些tips

### speed up your build 
- org.gradle.daemon = true
- org.gradle.parallel = true
- set proxy 
- org.gradle.jvmargs=-Xmx6114m -XX\:MaxPermSize\=2048m


daemon设置对本机有效，如果是build服务器可能反而会导致build速度减慢。
parallel设置的话需要保证task执行之间的时序，可以用task的dependOn来设置，或者mustRunAfter
设置代理同样可以加速或者降低拉取依赖的速度。


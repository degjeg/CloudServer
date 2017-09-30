# 本文演示在centos6.9安装jdk

## 1. 先列出jdk相关的包

```
[root@jdu4e00u53f7 soft]# yum -y  list java*
```

先列出各版本的jdk列表

```
Available Packages
java-1.5.0-gcj.x86_64                        1.5.0.0-29.1.el6
java-1.5.0-gcj-devel.x86_64                  1.5.0.0-29.1.el6
java-1.5.0-gcj-javadoc.x86_64                1.5.0.0-29.1.el6
java-1.5.0-gcj-src.x86_64                    1.5.0.0-29.1.el6
java-1.6.0-openjdk.x86_64                    1:1.6.0.41-1.13.13.1.el6_8
java-1.6.0-openjdk-demo.x86_64               1:1.6.0.41-1.13.13.1.el6_8
java-1.6.0-openjdk-devel.x86_64              1:1.6.0.41-1.13.13.1.el6_8
java-1.6.0-openjdk-javadoc.x86_64            1:1.6.0.41-1.13.13.1.el6_8
java-1.6.0-openjdk-src.x86_64                1:1.6.0.41-1.13.13.1.el6_8
java-1.7.0-openjdk.x86_64                    1:1.7.0.151-2.6.11.0.el6_9
java-1.7.0-openjdk-demo.x86_64               1:1.7.0.151-2.6.11.0.el6_9
java-1.7.0-openjdk-devel.x86_64              1:1.7.0.151-2.6.11.0.el6_9
java-1.7.0-openjdk-javadoc.noarch            1:1.7.0.151-2.6.11.0.el6_9
java-1.7.0-openjdk-src.x86_64                1:1.7.0.151-2.6.11.0.el6_9
java-1.8.0-openjdk.x86_64                    1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-debug.x86_64              1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-demo.x86_64               1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-demo-debug.x86_64         1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-devel.x86_64              1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-devel-debug.x86_64        1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-headless.x86_64           1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-headless-debug.x86_64     1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-javadoc.noarch            1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-javadoc-debug.noarch      1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-src.x86_64                1:1.8.0.141-3.b16.el6_9
java-1.8.0-openjdk-src-debug.x86_64          1:1.8.0.141-3.b16.el6_9
java_cup.x86_64                              1:0.10k-5.el6
java_cup-javadoc.x86_64                      1:0.10k-5.el6
java_cup-manual.x86_64                       1:0.10k-5.el6
javacc.x86_64                                4.1-0.5.el6
javacc-demo.x86_64                           4.1-0.5.el6
javacc-manual.x86_64                         4.1-0.5.el6
javassist.noarch                             3.9.0-6.el6
javassist-javadoc.noarch                     3.9.0-6.el6
```

## 2.安装jdk8

```
yum -y install java-1.8.0-openjdk.x86_64
```

## 3.验证是否安装成功

```
[root@jdu4e00u53f7 soft]# java -version
openjdk version "1.8.0_141"
OpenJDK Runtime Environment (build 1.8.0_141-b16)
OpenJDK 64-Bit Server VM (build 25.141-b16, mixed mode)
```

##  4. java的真实位置

```
[root@jdu4e00u53f7 soft]# which java
/usr/bin/java
[root@jdu4e00u53f7 soft]# ls -l /usr/bin/java
lrwxrwxrwx 1 root root 22 Sep 30 10:23 /usr/bin/java -> /etc/alternatives/java
[root@jdu4e00u53f7 soft]# ls -l /etc/alternatives/java
lrwxrwxrwx 1 root root 46 Sep 30 10:23 /etc/alternatives/java -> /usr/lib/jvm/jre-1.8.0-openjdk.x86_64/bin/java
[root@jdu4e00u53f7 soft]# ls -l /usr/lib/jvm/jre-1.8.0-openjdk.x86_64/bin/java 
-rwxr-xr-x 1 root root 5128 Aug 23 06:09 /usr/lib/jvm/jre-1.8.0-openjdk.x86_64/bin/java
[root@jdu4e00u53f7 soft]# 

```


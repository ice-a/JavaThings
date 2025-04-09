# JavaThings - Java安全漫谈笔记相关

《Java安全漫谈》是我在写的一点Java学习相关的随笔，不是很严谨，也不是啥高科技。这个Repository主要是记录并整理一下，附加一些代码。

## Java安全漫谈目录

- [Java安全漫谈 - 01.Java的动态特性——反射](https://t.zsxq.com/iyJiAMJ)
- [Java安全漫谈 - 02.反射的简单利用](https://t.zsxq.com/iIa2B2j)
- [Java安全漫谈 - 03.反射的几个进阶技巧](https://t.zsxq.com/MNRbayr)
- [Java安全漫谈 - 04.RMI的通信过程分析](https://t.zsxq.com/FMJiUrV)
- [Java安全漫谈 - 05.利用codebase攻击RMI Registry](https://t.zsxq.com/BuFy3zF)
- [Java安全漫谈 - 06.深入理解RMI协议与序列化对象](https://t.zsxq.com/vZjaiuR)
- [Java安全漫谈 - 07.不同语言中的反序列化漏洞](https://t.zsxq.com/NF2NfQf)
- [Java安全漫谈 - 08.认识最简单的Gadget——URLDNS](https://t.zsxq.com/ieMZBQj)
- [Java安全漫谈 - 09.初识CommonsCollections](https://t.zsxq.com/BmIIAy3)
- [Java安全漫谈 - 10.用TransformedMap编写真正的POC](https://t.zsxq.com/ZNZrJMZ)
- [Java安全漫谈 - 11.LazyMap详解](https://t.zsxq.com/FufUf2B)
- [Java安全漫谈 - 12.简化版CommonsCollections6](https://t.zsxq.com/A2j2beE)
- [Java安全漫谈 - 番外篇1. BCEL ClassLoader去哪了？](https://www.leavesongs.com/PENETRATION/where-is-bcel-classloader.html)
- [Java安全漫谈 - 13.Java中动态加载字节码的那些方法](https://t.zsxq.com/E2VfUVB)
- [Java安全漫谈 - 14.为什么需要CommonsCollections3](https://t.zsxq.com/i6Y7QN7)
- [Java安全漫谈 - 15.TemplatesImpl在Shiro中的利用](https://t.zsxq.com/JAUBmMz)
- [Java安全漫谈 - 16.commons-collections4与漏洞修复](https://t.zsxq.com/ZBQj2FE)
- [Java安全漫谈 - 17.CommonsBeanutils与无commons-collections的Shiro反序列化利用](https://t.zsxq.com/IqBmuF6)
- [Java安全漫谈 - 18.原生反序列化利用链JDK7u21](https://t.zsxq.com/neMbuJa)
- [Java安全漫谈 - 19.Java反序列化协议构造与分析](https://t.zsxq.com/ZfiEeEY)

## Demo代码

字节码：

- 远程字节码加载Demo：[HelloClassLoader](jdk8/src/main/java/com/govuln/bytes/HelloClassLoader.java)
- 系统默认defineClass加载字节码Demo：[HelloDefineClass](jdk8/src/main/java/com/govuln/bytes/HelloDefineClass.java)
- 使用TemplatesImpl加载字节码Demo：[HelloTemplatesImpl](jdk8/src/main/java/com/govuln/bytes/HelloTemplatesImpl.java)
- 使用BCEL加载字节码Demo：[HelloBCEL](jdk8/src/main/java/com/govuln/bytes/HelloBCEL.java)

反序列化：

- 最简单的Transformer Demo：[CommonsCollectionsIntro.java](jdk8/src/main/java/com/govuln/deserialization/CommonsCollectionsIntro.java)
- 我简化的[CommonsCollections6](jdk8/src/main/java/com/govuln/deserialization/CommonsCollections6.java)，更方便大家理解
- 利用TemplatesImpl构造的Transformer Demo：[CommonsCollectionsIntro2.java](jdk8/src/main/java/com/govuln/deserialization/CommonsCollectionsIntro2.java)
- 无InvokerTransformer的Transformer Demo：[CommonsCollectionsIntro3.java](jdk8/src/main/java/com/govuln/deserialization/CommonsCollectionsIntro3.java)
- 我简化的[CommonsCollections3](jdk8/src/main/java/com/govuln/deserialization/CommonsCollections3.java)
- CommonsCollections6一次执行多个命令：[CommonsCollections6Multiple](jdk8/src/main/java/com/govuln/deserialization/CommonsCollections6Multiple.java)
- 支持commons-collections4.0版本的CommonsCollections6利用链：[CommonsCollections6For4](jdk8/src/main/java/com/govuln/deserialization/CommonsCollections6For4.java)
- 我简化的CommonsBeanutils1利用链：[CommonsBeanutils1](jdk8/src/main/java/com/govuln/deserialization/CommonsBeanutils1.java)
- 简化版Java原生利用链 [JDK7u21](jdk8/src/main/java/com/govuln/deserialization/JDK7u21.java)

Shiro反序列化：

- 一个最简单的Shiro Web应用：[shirodemo](shirodemo/)
- 使用CommonsCollections6与Shiro默认Key构造Payload：[Client0.java](shiroattack/src/main/java/com/govuln/shiroattack/Client0.java)、[CommonsCollections6.java](shiroattack/src/main/java/com/govuln/shiroattack/CommonsCollections6.java)，在Tomcat中可能会无法成功反序列化
- 使用CommonsCollections、TemplatesImpl与Shiro默认Key构造Payload：[Client.java](shiroattack/src/main/java/com/govuln/shiroattack/Client.java)、[CommonsCollectionsShiro.java](shiroattack/src/main/java/com/govuln/shiroattack/CommonsCollectionsShiro.java)，解决上述问题
- 使用Shiro默认自带的commons-beanutils构造的反序列化利用链：[CommonsBeanutils1Shiro.java](shiroattack/src/main/java/com/govuln/shiroattack/CommonsBeanutils1Shiro.java)

自研反序列化分析工具：

- zkar: <https://github.com/phith0n/zkar>
- 如何使用zkar修复SerialVersionUID不匹配的问题：<https://t.zsxq.com/Yz3B6yJ>

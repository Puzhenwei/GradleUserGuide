# 什么是 Gradle 的守护进程

维基百科中守护进程的解释

> *守护进程是一个运行后台进程, 非交互式用户直接控制的在计算机程序*

Gradle 守护进程是一个后台进程, 
它运行着繁重的构建, 然后在构建等待下一次构建的之间保持自身存在. 这使得数据和代码在下一次构建前已经准备好,并存入内存中. 这*显著*的提高了后续构建的性能. 启用Gradle守护进程是一种节约构建时间的廉价方式. 

*强烈建议在所有开发机器上启用Gradle的守护进程*.但是*不推荐*在持续集成和构建服务器环境下启用守护进程(参见 [Section 18.3, “When should I not use the Gradle Daemon?”](https://docs.gradle.org/current/userguide/gradle_daemon.html#when_should_i_not_use_the_gradle_daemon)).

Gradle自动管理守护进程.如果构建环境配置为利用后台程序,如果在没有可用守护进程,就会自动启动一个守护进程,或者使用现有的空闲的*兼容*守护进程.如果一个守护进程在3个小时内没有使用,它将会自我终结.一旦配置开发环境为使用的守护进程,守护进程通常是隐形的,容易被遗忘的.





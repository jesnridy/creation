# creation
first of  all

#Demo
* [1 前言](#1)
* [2 目标](#2)
* [2 需要解决的点](#2)
	* [2.1 多进程通信](#2.1)
		* [2.1.1 gunicorn的解决方式](#2.1.1)
		* [2.1.2 进程管理](#2.1.2)
	* [2.2 epoll的调用实现](#2.2)
	* [2.3 异步调用epoll](#2.3)


<h2 id="1">1. 前言</h2>

>

<h2 id="2">2. 目标</h2>

异步并行
<h2 id="2">2. 需要解决的点</h2>

<h3 id="2.1">2.1 多进程通信</h3>
<h4 id="2.1.1">2.1.1 gunicorn的解决方式</h4>
<h4 id="2.1.2">2.1.2 进程管理</h4>
考虑采用[nginx](https://blog.csdn.net/yusiguyuan/article/details/40924415)的方式，使用一个master进程，多个work子进程。

master进程只做监控，重启服务，更换日志文件，reload配置文件。

master通过信号机制掉用worker子进程进行和后端服务具体操作。



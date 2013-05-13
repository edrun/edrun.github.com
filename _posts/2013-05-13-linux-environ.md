---
layout: post
title: 'LINUX环境变量介绍'
category: shell
tags:
   -shell
---

LINUX环境变量介绍
=================
环境变量相关文件
----------------

### 背景

>
>环境变量是和Shell紧密相关的，用户登录系统后就启动了一个Shell。对于Linux来说一般是bash，但也可以重新设定或切换到其它的 Shell。对于UNIX，>可能是CShelll。环境变量是通过Shell命令来设置的，设置好的环境变量又可以被所有当前用户所运行的程序所使用。对于bash这个Shell程序来说，可以通过变量名来访问相应的环境变量，通过export来设置环境变量。下面通过几个实例来说明。
>

- [etc/profile
此文件为系统的每个用户设置环境信息,当用户第一次登录时,该文件被执行.
并从/etc/profile.d目录的配置文件中搜集shell的设置.
注：在这里我们设定是为所有用户可使用的全局变量。

- ]/etc/bashrc:为每一个运行bash shell的用户执行此文件.当bash shell被打开时,该文件被读取.

- ]~/.bash_profile
每个用户都可使用该文件输入专用于自己使用的shell信息,当用户登录时,该文件仅仅执行一次!默认情况下,他设置一些环境变量,执行用户的.bashrc文件.
注：~在LINUX下面是代表HOME这个变量的。
另外在不同的LINUX操作系统下，这个文件可能是不同的，可能是~/.bash_profile； ~/.bash_login或 ~/.profile其中的一种或几种，如果存在几种的话，那么执行的顺序便是：~/.bash_profile、 ~/.bash_login、 ~/.profile。比如我用的是Ubuntu，我的用户文件夹下默认的就只有~/.profile文件。

- ]~/.bashrc:
该文件包含专用于你的bash shell的bash信息,当登录时以及每次打开新的shell时,该文件被读取.
(注：这个文件是 .开头的，所以在文件夹中被隐藏了)

- ]~/.bash_logout
当每次退出系统(退出bash shell)时,执行该文件.
另外,/etc/profile中设定的变量(全局)的可以作用于任何用户,而~/.bashrc等中设定的变量(局部)只能继承/etc/profile中的变量,他们是\"父子\"关系.

### 注意
- ]~/.bash_profile 是交互式、login 方式进入 bash 运行的
- ]~/.bashrc 是交互式 non-login 方式进入 bash 运行的
- ]通常二者设置大致相同，所以通常前者会调用后者。
- ] 当启动一个交互的bash时,它将执行~/.bashrc文件中的命令(如果该文件存在并且可读).当非交互地启动以运行一个shell脚本时,bash将查找bash_env环境变量,确定执行文件的名称.

### 执行顺序
- ] login--->shell---->bash-->/etc/profile--->~ /.bash_profile--->~/.bash_login or ~/.profile 并执行找到的第一个可读文件中的命令
- ] logout-->~/.bash_logout
- ]执行顺序为：/etc/profile -> (~/.bash_profile | ~/.bash_login | ~/.profile) -> ~/.bashrc -> /etc/bashrc -> ~/.bash_logout










---
layout: post
title: Centos 使用阿里云或网易163国内源
category: Linux
tags: [Centos]
---

由于国内网络环境的限制，使用Centos yum安装包时，下载速度缓慢。目前可以通过修改源的方式解决这个问题，步骤如下：

1. 备份原有源

        mv /etc/yum.repo.d/CentOS-Base.repo /etc/yum.repo.d/CentOS-Base.repo.backup

2. 查看当前 CentOS 版本

        cat /etc/redhat-release

3. 根据 CentOS 系统版本下载国内源

    - 阿里云

        * CentOS 5

                wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-5.repo

        * CentOS 6

                wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo

    - 网易163

        * CentOS 5

                wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.163.com/.help/CentOS5-Base-163.repo

        * CentOS 6

                wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.163.com/.help/CentOS6-Base-163.repo

4. 更新缓存

        yum clean all
        yum makecache

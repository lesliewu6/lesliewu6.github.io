---
title: 个人博客搭建（Hexo+Github)
description: 个人博客搭建（Hexo+Github)，使用hexo主题为Maupassant。
categories: tech
toc: true
comments: true
---

### 环境准备

参考自[知乎博客](https://zhuanlan.zhihu.com/p/675680355)

#### node.js安装

​	[node.js官网](https://nodejs.org/en/)下载对应系统版本即可

> nodejs对于JavaScript进行了一定程度的改进，是一个工具包，使其能够适用于后端服务器开发。
>
> 为了解决服务器常见的问题，nodejs引入了并发、线程池、I\O阻塞等机制

#### git安装

#### hexo安装

​	git bash上安装

```git
npm config set registry  https://registry.npmmirror.com  # 将npm源替换为镜像，安装更快
npm install hexo-cli -g # 安装Hexo
hexo -v # 返回Hexo版本，确定安装成功
```

### 博客搭建

```git
hexo generate #生成模板页面
hexo server #运行服务器程序，默认端口为http://localhost:4000/，可用于本地查看
```

#### 主题设置

使用hexo的[Maupassant](https://www.haomwei.com/technology/maupassant-hexo.html)主题

#### 博文格式

通常使用md格式进行书写，在博文最前配置front-matter，其对应格式为

```
---
title: 标题
description: 简介
categories: 分类
toc: true #是否显示目录
comments: true #是否启用评论
---
```

### 推送至github

#### 创建repositoriy

仓库名字必须设定为相同，权限public

![image-20240716130940959](C:\Users\10261\AppData\Roaming\Typora\typora-user-images\image-20240716130940959.png)

#### hexo配置

基础配置：

修改网页标题、时区等

```
# Site
title: Wu Zhonghao
subtitle: ''
description: ''
keywords:
author: Wu Zhonghao
language: zh-CN 
timezone: 'Asia/Shanghai'
```

修改博客根目录下的_config.yml文件中的deploy配置项：

```yaml
 deploy:
   type: git
   repository: git@github.com:username/username.github.io.git  # 你的仓库地址
   branch: gh-pages
```

常见hexo命令

```git bash
 hexo clean # 清除缓存
 hexo generate # 生成网站
 hexo deploy # 部署至远程网络
 ​
 # 简写
 hexo cl
 hexo g
 hexo d
 ​
 # 简简写
 hexo cl
 hexo g -d  # hexo d -g
```

#### pages设置

选择source为远程部署，选择对应分支。

![image-20240716131145966](C:\Users\10261\AppData\Roaming\Typora\typora-user-images\image-20240716131145966.png)


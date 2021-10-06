---
layout: post
title:  "更新blog模版"
date:   2021-10-06 19:28:00
categories: write
tags: Github-pages
excerpt: 
mathjax: true
typora-root-url: ../../blog
---

原来使用hugo做静态blog框架，但hugo框架要发布到github pages前，还需要用hugo构建一把，我比较懒，这一步都不想做。


## 使用hugo框架

在选择blog框架时，因为不想再本机安装过多的框架依赖，所以没有选择jekyll这类框架。而我是个golang开发者，本机已有golang相关环境，自然就看上了同样是使用golang的hugo。

使用过程就是参考hugo官网及其他用户的分享，很顺利就安装完成，搭建了一个自己的blog主页。

![image-20211006184032103](/assets/2021-10-06-update-githubpages.assets/image-20211006184032103.png)

但是使用hugo有一点不好，就是写完文章，需要用hugo构建一次，生成了网页，再把网页推送到github。写文章就不能专心一点么？（实际就是我很懒。）

其实也可以通过github action配置自动构建，但就没有更原生一点到方法？



## github与jekyll

实际上github pages原生就支持jekyll构建，只要搭建好了基本的模板，后面就是直接把文章推送上去，github就自动使用jekyll构建并托管完成。 

我要做的就是写文章，然后push，完美。

等等，最初的模板怎么来？github pages帮助里面说，要安装jekyll，然后使用jekyll创建初始模板，再进一步配置themes等。这个我也不想做，而且我不懂前端，装一大堆东西，还不是就用默认配置，自己也不改。 那么是不是直接找个好看模板拿过来改个名字就ok了。

于是我找到了   

[浩阳的blog]: https://gaohaoyang.github.io

, 风格简洁大方，关键元素：主页的文章概览、分类、tag、访问计数、comment都有，就这个了。

## 配置的坑

### 不显示样式
当直接clone下来放到自己的库内，修改相关配置后，push到github。这时pages上只显示文字，没有样式。
这个其实是在_config.yml中漏配了一项：
``` yaml
baseurl: "/tmpfile"
```

要把baseurl配置成自己仓库名，当然如果github内直接使用xxx.github.io创建的仓库，那么这里就直接是根目录"/"了。

### 显示图片

之前都是把文章用到的图片都放在当前路径的 articlename.assets目录内。但放到github pages上后，路径就不一样了，需要使用从仓库目录开始的相对路径。比如这样：

``` markdown
![udohbd0u3x](/tmpfile/assets/2021-07-08-ebpf-in-hids.assets/udohbd0u3x-1696044.png)
```

这里我是将图片目录放到了根目录到assets目录下，因为放到_port目录下，推上去后图片路径不对，不显示。

也有人建议把图片放其它图床，因为直接访问github的图片可能会失败。 这个后面再看，如果当前方式的确有问题再修改。

### 使用Typora时显示图片

如果按照上一节的设置，使用Typora写作时就需要设置一下，修改保存图片到目录。

![image-20211006183855092](/assets/2021-10-06-update-githubpages.assets/image-20211006183855092.png)


# Future-Imperfect Jekyll Template

> 一个基于[Future Imperfect](https://html5up.net/future-imperfect)制作的Jekyll模板.
>
> 我很喜欢它的风格，但是目前Github上关于它的Jekyll模板并不够实用，所以有了这个repo。

## 构建环境

* Windows 11 22H2 (x64)
* Ruby 3.2.2
* Jekyll 4.3.2
  * jekyll-feed 0.12
  * jekyll-paginate 1.1.0
* simple-jekyll-search 1.10.0

## 功能

* 基本功能
  * [x] 搜索文章(基于[simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search))
  * [x] 文章目录(基于[Jekyll-TOC](https://github.com/allejo/jekyll-toc))
  * [x] 文章分页(基于[jekyll-paginate](https://rubygems.org/gems/jekyll-paginate/versions/1.1.0))
  * [x] 文章归档与筛选(按照category或tag)
* 美化
  * [x] 代码高亮(基于[rouge](https://rubygems.org/gems/rouge/versions/4.1.2))
  * [x] 渲染公式(基于[MathJax](https://www.mathjax.org))
  * [x] 渲染mermaid图表(基于[jekyll-mermaid](https://github.com/jasonbellamy/jekyll-mermaid))
  * [x] 可定制的header
* 评论
  * [x] Gitalk评论
  * [ ] Disqus评论

## 使用

### (1) 配置

* `git clone`
* 修改`_config.yml`
  > 建议在部署前先在本地运行一下`jekyll serve`，检查是否有问题

### (2) 部署(GitHub Pages)

* 撰写文章(请保存在`_posts`文件夹中)
* 将整个项目上传到Github，仓库名为`<username>.github.io`
* 在仓库设置中找到`Pages`，点击。
  1. 在`Source`的选项中选择`Action`
  2. 在跳转页面中点击`GitHub Pages Jekyll`的`Configuration`按钮
  3. 随后会请求添加一个`.yml`文件，不用修改直接添加即可
  4. 稍等片刻，Github Pages将会完成部署，之后就可以通过`https://<username>.github.io`访问。

### (3) 关于头信息

> 哪怕你已经十分熟悉Jekyll了，也建议你再看看这一部分，这部分根据Future-Imperfect的样式做了一些改动

* 本项目中，一个典型的头信息如下所示：
  ```yaml
  ---
  layout: post
  title: "Test"
  subtitle: "This is a test article"
  author: "Your name"
  date: 2023-07-05 10:00:00 +0800
  cover: "/images/test_cover.jpg"
  stick: true
  tag:
    - test
    - article
  category: test
  ---
  ```
* `layout`：布局样式，请填**post**，表示让这篇文章应用“post”布局。
* `title`：标题，不能留空
* `subtitle`：副标题，可以留空或直接删除(允许不存在subtitle这一字段)。
* `author`：作者，留空或直接删除时，显示`_config.yml`中的`username`字段；若存在且与`username`不同，则使用所填的内容。
* `date`：发布日期，请按照示例的格式来写，最后的`+0800`表示时区为GMT+8(北京时间)
* `cover`：封面，留空或直接删除时会使用默认封面[/images/default_cover.jpg](./images/default_cover.jpg)
* `stick`：是否固定到首页左侧，留空或删除等同于false，不建议stick的文章过多。
* `tag`：标签，用于筛选文章，允许多个tag。
* `category`：类别，用于筛选文章，不建议多个category，在设计之初就是按照单个category设计的。

## 问题

* ~~部分情况下，顶栏可能不会固定在顶部而是出现在页面侧边，导致整个页面的样式出现问题~~
  > 已解决，详见[注意事项](#注意事项)第1项

## 注意事项

1. 在使用AdGuard或同类浏览器插件时，不要启用**Web Annoyances Ultralist**(`过滤器 > 扰人的 > Web Annoyances Ultralist`)，该规则会使部分样式被浏览器默认样式覆盖，导致页面样式异常。

## 来自HTML5 UP的原始README

    Future Imperfect by HTML5 UP
    html5up.net | @ajlkn
    Free for personal and commercial use under the CCA 3.0 license (html5up.net/license)

    It's been a long time coming, but I've finally gotten around to creating a brand new
    blog-style template (and the first since Striped, which came out waaaaay back in 2013).
    Anyway, Future Imperfect features a clean, expansive layout, a toggleable search box,
    and -- because pretty much all modern browsers can use it now -- a whole lot of flexbox
    action. Enjoy it :)

    Demo images* courtesy of Unsplash, a radtastic collection of CC0 (public domain) images
    you can use for pretty much whatever.

    (* = not included)

    AJ
    <aj@lkn.io> | @ajlkn

    Credits:

    Demo Images:
    Unsplash (unsplash.com)

    Icons:
    Font Awesome (fortawesome.github.com/Font-Awesome)

    Other:
    jQuery (jquery.com)
    html5shiv.js (@afarkas @jdalton @jon_neal @rem)
    Misc. Sass functions (@HugoGiraudel)
    Respond.js (j.mp/respondjs)
    Skel (skel.io)

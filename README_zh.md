# Future-Imperfect Jekyll Template

> 一个基于[Future Imperfect](https://html5up.net/future-imperfect)制作的Jekyll模板.
>
> 我很喜欢它的风格，但是目前GitHub上关于它的Jekyll模板并不够好用，所以有了这个repo。

## 构建环境

* Windows 11 22H2 (x64) / Ubuntu 23.10 (x64)
* Ruby 3.2.2 (Windows) / Ruby 3.1.2p20 (Ubuntu)

* Jekyll 4.3.2
  * addressable 2.8.1
  * concurrent-ruby 1.1.6
  * em-websocket 0.5.1
  * http_parser.rb 0.6.0
  * i18n 1.10.0
  * jekyll-feed 0.17.0
  * jekyll-paginate 1.1.0
  * jekyll-sass-converter 2.2.0
  * jekyll-seo-tag 2.8.0
  * listen 3.7.0
  * minima 2.5.1
  * pathutil 0.16.1
  * public_suffix 4.0.6
  * rouge 4.1.2
  * sassc 2.4.0
  * unicode-display_width 1.6.1
  * webrick 1.8.1

* simple-jekyll-search 1.10.0

## 功能

* 基本功能
  * [x] 搜索文章(基于[simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search))
  * [x] 文章目录(基于[Jekyll-TOC](https://github.com/allejo/jekyll-toc))
  * [x] 文章分页(基于[jekyll-paginate](https://rubygems.org/gems/jekyll-paginate/versions/1.1.0))
  * [x] 文章归档与筛选(按照category或tags)
  * [x] 提供RSS订阅(基于[jekyll-feed](https://github.com/jekyll/jekyll-feed))
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

1. 通过`git clone`或通过下载压缩包保存到本地
2. 通过`gem`安装Jekyll及其依赖

    ```bash
    apt install ruby ruby-dev gem -y # Ubuntu，其他发行版请自行安装
    gem install bundler jekyll # 安装Jekyll及基本组件

    # 安装其他Jekyll插件
    bundle install
    ```

3. 修改`_config.yml`，使之符合你的需求

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

> 哪怕你已经十分熟悉Jekyll了，也建议你看看这一部分，本项目的头信息根据Future-Imperfect和Jekyll-Feed的要求有所改动，可能与通常的Jekyll模板的习惯有所不同。

* 本项目中，一个典型的头信息如下所示：

    ```yaml
    ---
    layout: post
    title: "Test"
    description: "This is a test article"
    author: "Your name"
    date: 2023-07-05 10:00:00 +0800
    image: "/images/test_cover.jpg"
    stick: true
    tags:
      - test
      - article
    category: test
    ---
    ```

* `layout`：布局样式，请填**post**，表示让这篇文章应用“post”布局。
* `title`：标题，不能留空
* `description`：本篇文章描述，可以留空或直接删除(允许不存在`description`这一字段)。
* `author`：作者，留空或直接删除时，显示`_config.yml`中的`username`字段；若存在且与`username`不同，则使用所填的内容。
* `date`：发布日期，请按照示例的格式来写，最后的`+0800`表示时区为GMT+8(北京时间)
* `image`：文章封面，留空或直接删除时会使用默认封面[/images/default_cover.jpg](./images/default_cover.jpg)
* `stick`：是否固定到首页左侧，留空或删除等同于false，不建议stick的文章过多。
* `tags`：标签，用于筛选文章，允许多个tag。
* `category`：类别，用于筛选文章，不建议多个category，在设计之初就是按照单个category设计的。

## 问题

* ~~部分情况下，顶栏可能不会固定在顶部而是出现在页面侧边，导致整个页面的样式出现问题~~
  > 已解决，详见[注意事项](#注意事项)第1项
* 页面中“统计信息”部分的标签未能按照预想的效果，分别按照“最新”和“最多”排序，也许是Liquid语法的问题，暂时无法解决。

## 注意事项

1. 在使用AdGuard或同类浏览器插件时，不要启用**Web Annoyances Ultralist**(`过滤器 > 扰人的 > Web Annoyances Ultralist`)
   规则集，该规则会使部分样式被浏览器默认样式覆盖，导致页面样式异常。
2. 可优化的细节：
   * 目前图片资源都是`jpg`格式，但对网页来说`jpg`并不是最优解——它的兼容性很好，但压缩率不高，鉴于当前的主流浏览器都已支持压缩率更高的`webp`格式的图片，您可以考虑使用`webp`代替`jpg`，以提高加载速度，同时节省流量。
       * 对于未指定封面路径的文章，会使用默认封面。您可以通过修改`_config.yml`的`default_cover_path`值来修改默认封面的路径。
   * 在目前的[main.css](./assets/css/main.css)中，`Source Sans Pro`字体使用Google Fonts的cdn加载，但通常来说谷歌的cdn在国内并不稳定。若您将该模板用于国内网站，您可以考虑换用其他cdn或直接下载到本地导入使用。

## 来自HTML5 UP的原始README

> 原始项目基于[CCA 3.0 license (Creative Cloud Attribution)](https://creativecommons.org/licenses/by/3.0/)开源。

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

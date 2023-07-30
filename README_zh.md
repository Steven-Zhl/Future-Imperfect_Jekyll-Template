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

* [x] 按类别组织文章(利用`Category`元属性)
* [x] 搜索文章(基于[simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search))
* [x] 文章目录(基于[Jekyll-TOC](https://github.com/allejo/jekyll-toc))
* [x] 文章分页(基于[jekyll-paginate](https://rubygems.org/gems/jekyll-paginate/versions/1.1.0))
* [x] 文章归档
* [x] 文章筛选(按照category或tag属性)
* [x] 代码高亮(基于[rouge](https://rubygems.org/gems/rouge/versions/4.1.2))
* [x] 渲染公式(基于[MathJax](https://www.mathjax.org)(JavaScript脚本))
* [x] 渲染mermaid图表(基于[jekyll-mermaid](https://github.com/jasonbellamy/jekyll-mermaid)的离线JavaScript脚本([mermaid.min.js](https://unpkg.com/browse/mermaid@10.2.4/dist/mermaid.min.js)))
* [ ] 评论
  * [x] Gitalk评论
  * [ ] Disqus评论

## 使用

### (1) 配置

* `git clone`
* 修改`_config.yml`
  > 建议在部署前先在本地运行一下`jekyll serve`，检查是否有问题

### (2) 部署

* 将整个项目上传到Github，仓库名为`<username>.github.io`
* 在仓库设置中找到`Pages`，点击。
  1. 在`Source`的选项中选择`Action`
  2. 在跳转页面中点击`GitHub Pages Jekyll`的`Configuration`按钮
  3. 随后会请求添加一个`.yml`文件，不用修改直接添加即可
  4. 稍等片刻，Github Pages将会完成部署，之后就可以通过`https://<username>.github.io`访问。

## 问题

* 在部分浏览器上，顶栏可能不会固定在顶部，而是出现在页面侧边。(该问题在Microsoft Edge 114.0.1823.67上出现，未确定原因，但与之同期的Chrome则没有该问题。)

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

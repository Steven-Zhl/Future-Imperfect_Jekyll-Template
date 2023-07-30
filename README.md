# Future-Imperfect Jekyll Template

[中文文档](./README_zh.md)
> A Jekyll template based on [Future Imperfect](https://html5up.net/future-imperfect).
>
> I really like its style, but the Jekyll templates for it on GitHub aren't practical enough, so I made this repo.

## Environment(Build)

* Windows 11 22H2 (x64)
* Ruby 3.2.2
* Jekyll 4.3.2
  * jekyll-feed 0.12
  * jekyll-paginate 1.1.0
* simple-jekyll-search 1.10.0

## Function

* [x] Organize articles by category (using the `Category` front matter)
* [x] Search articles (based on [simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search))
* [x] Article table of contents (based on [Jekyll-TOC](https://github.com/allejo/jekyll-toc))
* [x] Article pagination (based on [jekyll-paginate](https://rubygems.org/gems/jekyll-paginate/versions/1.1.0))
* [x] Article archive (baesd on JavaScript)
* [x] Article filtering (by category or tag)
* [x] Code highlighting (based on [rouge](https://rubygems.org/gems/rouge/versions/4.1.2))
* [x] Render formulas (based on [MathJax](https://www.mathjax.org)(JavaScript script))
* [x] Render mermaid charts (based on [jekyll-mermaid](https://github.com/jasonbellamy/jekyll-mermaid) offline JavaScript script ([mermaid.min.js](https://unpkg.com/browse/mermaid@latest/dist/mermaid.min.js)))
* [ ] Comments
  * [x] Gitalk comments
  * [ ] Disqus comments

## Usage

### (1) Configuration

* `git clone`
* Modify `_config.yml`
  > It is recommended to run `jekyll serve` locally before deployment to check for any issues.

### (2) Deployment

* Upload the entire project to GitHub, with the repository name `<username>.github.io`
* In the repository settings, find `Pages` and click it.
  1. In the `Source` option, select `Action`
  2. Click the `Configuration` button for `GitHub Pages Jekyll` on the redirected page
  3. You will then be prompted to add a `.yml` file, which you can add without modification.
  4. Wait a moment, and Github Pages will complete the deployment, after which you can access it via `https://<username>.github.io`.

## Issues

* In some browsers, the top bar may not be fixed to the top, but appear on the side of the page (This issue appears on Microsoft Edge 114.0.1823.67, the cause is unknown. But Chrome didn't have that problem).

## Original README from HTML5 UP

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

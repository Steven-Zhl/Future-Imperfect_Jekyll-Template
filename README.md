# Future-Imperfect Jekyll Template

> A Jekyll template based on [Future Imperfect](https://html5up.net/future-imperfect).
>
> I really like its style, but the Jekyll templates for it on GitHub aren't practical enough, so I made this repo.

[![中文文档](https://img.shields.io/badge/README-中文文档-blue)](./README_zh.md)
[![预览](https://img.shields.io/badge/Deployment-Steven's_Blog-yellow)](https://steven-zhl.github.io)

![语言](https://img.shields.io/github/languages/top/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![开源协议](https://img.shields.io/github/license/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![上次提交](https://img.shields.io/github/last-commit/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![仓库大小](https://img.shields.io/github/repo-size/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)

## Environment(Build)

* Windows 11 22H2 (x64)
* Ruby 3.2.2
* Jekyll 4.3.2
  * jekyll-feed 0.12
  * jekyll-paginate 1.1.0
* simple-jekyll-search 1.10.0

## Features

* Basic Features
  * [x] Article search (based on simple-jekyll-search)
  * [x] Article table of contents (based on Jekyll-TOC)
  * [x] Article pagination (based on jekyll-paginate)
  * [x] Article archiving and filtering (by category or tag)
* Styling
  * [x] Code highlighting (based on rouge)
  * [x] Formula rendering (based on MathJax)
  * [x] Rendered mermaid charts (based on jekyll-mermaid)
  * [x] Customizable header
* Comments
  * [x] Gitalk comments
  * [ ] Disqus comments

## Usage

### (1) Configuration

* `git clone`
* Modify `_config.yml`
  > It is recommended to run `jekyll serve` locally before deployment to check for any issues.

### (2) Deployment(GitHub Pages)

* Writing Articles (Please save them in the `_posts` folder)
* Upload the entire project to GitHub, with the repository name `<username>.github.io`
* In the repository settings, find `Pages` and click it.
  1. In the `Source` option, select `Action`
  2. Click the `Configuration` button for `GitHub Pages Jekyll` on the redirected page
  3. You will then be prompted to add a `.yml` file, which you can add without modification.
  4. Wait a moment, and Github Pages will complete the deployment, after which you can access it
     via `https://<username>.github.io`.

### (3) About Front Matter

> Even if you are already familiar with Jekyll, it is recommended to review this section. Some modifications have been
> made to this section based on the style of Future-Imperfect.

* In this project, a typical **Front Matter** is shown below:
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
* `layout`: Layout style, please fill in **post** to indicate that this article should use the "post" layout.
* `title`: Title, must not be left blank.
* `subtitle`: Subtitle, can be left blank or deleted directly (the absence of the `subtitle` field is allowed).
* `author`: Author, when left blank or deleted, it will display the `username` field in `_config.yml`; if provided and
  different from `username`, it will use the content you provide.
* `date`: Publication date, please follow the format in the example. The `+0800` at the end indicates the GMT+8 time
  zone (Beijing time).
* `cover`: Cover image, when left blank or deleted, the default cover
  image [/images/default_cover.jpg](./images/default_cover.jpg) will be used.
* `stick`: Whether to pin it to the left side of the homepage. Leaving it blank or deleting it is equivalent to `false`.
  It is not recommended to have too many articles pinned.
* `tag`: Tags, used for filtering articles, multiple tags are allowed.
* `category`: Category, used for filtering articles. It is not recommended to use multiple categories, as the design is
  based on a single category from the beginning.

## Issues

* ~~In some cases, the top bar may not stick to the top of the page and instead appear on the side of the page, causing
  issues with the overall page layout~~
  > This issue has been resolved, refer to [Notes](#notes) item 1 for details.

## Notes

1. When using AdGuard or similar browser extensions, do not enable **Web Annoyances Ultralist** (`Filters > Annoyances > Web Annoyances Ultralist`). This rule can cause certain styles to be overridden by the browser's default styles, leading to abnormal page styling.

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

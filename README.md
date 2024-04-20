# Future-Imperfect Jekyll Template

> A Jekyll template based on [Future Imperfect](https://html5up.net/future-imperfect).
>
> I really like its style, but the Jekyll templates for it on GitHub aren't practical enough, so I made this repo.

[![中文文档](https://img.shields.io/badge/README__zh-中文文档-blue)](./README_zh.md)
[![预览](https://img.shields.io/badge/Deployment-Steven's_Blog-yellow)](https://steven-zhl.github.io)

![语言](https://img.shields.io/github/languages/top/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![开源协议](https://img.shields.io/github/license/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![上次提交](https://img.shields.io/github/last-commit/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)
![仓库大小](https://img.shields.io/github/repo-size/Steven-Zhl/Future-Imperfect_Jekyll-Template.svg)

## Environment(Build)

* Windows 11 22H2 (x64) / Ubuntu 23.10 (x64)
* Ruby 3.2.2 (Windows) / Ruby 3.1.2p20 (Ubuntu)

* Jekyll 4.3.2
  * addressable 2.8.6
  * concurrent-ruby 1.2.2
  * em-websocket 0.5.3
  * ffi 1.16.3-x64-mingw-ucrt
  * google-protobuf 3.25.1-x64-mingw-ucrt
  * http_parser.rb 0.8.0
  * i18n 1.14.1
  * jekyll-feed 0.17.0
  * jekyll-paginate 1.1.0
  * jekyll-sass-converter 3.0.0
    * sass-embedded ~> 1.54
  * jekyll-seo-tag 2.8.0
  * listen 3.8.0
    * rb-fsevent ~> 0.10, >= 0.10.3
  * minima 2.5.1
  * pathutil 0.16.2
    * forwardable-extended ~> 2.6
  * public_suffix 5.0.4
  * rb-fsevent 0.11.2
  * rexml 3.2.6
  * rouge 4.2.0
  * sass-embedded 1.69.5-x64-mingw-ucrt
    * google-protobuf ~> 3.23
  * unicode-display_width 1.6.1
  * webrick 1.8.1
  * tzinfo 2.0.6
    * concurrent-ruby ~> 1.0
  * tzinfo-data 1.2023.3
    * tzinfo >= 1.0.0
  * unicode-display_width 2.5.0
  * wdm (0.1.1)
* Bundle 2.5.1
* Gem 3.5.1
* simple-jekyll-search 1.10.0

## Features

* Basic Features
  * [x] Article search (based on [simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search))
  * [x] Article table of contents (based on [Jekyll-TOC](https://github.com/allejo/jekyll-toc))
  * [x] Article pagination (based on [jekyll-paginate](https://rubygems.org/gems/jekyll-paginate/versions/1.1.0))
  * [x] Article archiving and filtering (by category or tags)
  * [x] RSS subscription (based on [jekyll-feed](https://github.com/jekyll/jekyll-feed))
* Styling
  * [x] Code highlighting (based on rouge)
  * [x] Formula rendering (based on MathJax)
  * [x] Rendered mermaid charts (based on jekyll-mermaid)
  * [x] Customizable header
* Comments
  * [x] [Gitalk](https://github.com/gitalk/gitalk) comments
  * [x] [Disqus](https://disqus.com/) comments
  * [x] [Livere](https://livere.com/) comments

## Usage

### (1) Configuration

1. Save it locally by `git clone` or downloading the zip file.
2. Install Jekyll and its dependencies via `gem`

  ```bash
  apt install ruby ruby-dev gem -y # Ubuntu, other linux distributions please install manually
  gem install bundler jekyll # Install Jekyll and its basic components.

  # Install dependencies
  bundle install
  ```

3. Modify `_config.yml`, make it meet your needs.

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

### (3) About Post's YAML Front Matter

> Even if you are already familiar with Jekyll, it is recommended to review this section. Some modifications have been made to this part based on the requirements of Future-Imperfect and Jekyll-Feed, which may be different from the usual Jekyll templates.

* In this project, a typical **Front Matter** is shown below:

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
  mathjax: true
  mermaid: false
  ---
  ```

> The following is an explanation of each field, fields marked as [optional] can be left blank or deleted directly (the absence of this field is allowed).

* `layout`: [Required]Layout style, please fill in **post** to indicate that this article should use the "post" layout.
* `title`: [Required]Title of this article.
* `description`: [Optional]Description of this article.
* `author`: [Optional]Author, when left blank or deleted, it will display the `username` field in `_config.yml`; if provided and different from `username`, it will use the content you provide.
* `date`: [Required]Publication date, please follow the format in the example. The `+0800` at the end indicates the GMT+8 time zone (Beijing time).
* `image`: [Optional]Cover image of the article, when left blank or deleted, the default cover image [/images/default_cover.jpg](./images/default_cover.jpg) will be used.
* `stick`: [Optional]Whether to pin it to the left side of the homepage. Leaving it blank or deleting it is equivalent to `false`. It is not recommended to have too many articles pinned.
* `tags`: [Optional]Tags, used for filtering articles, multiple tags are allowed.
* `category`: [Optional]Category, used for filtering articles. It can only be one category.
* `mathjax`: [Optional]Whether to enable MathJax rendering. If not configured, it will follow the global configuration (`mathjax.enable`) in `_config.yml`.
* `mermaid`: [Optional]Whether to enable rendering of mermaid charts. If not configured, it will follow the global configuration (`jekyll-mermaid.enable`) in `_config.yml`.

## Issues

* ~~In some cases, the top bar may not stick to the top of the page and instead appear on the side of the page, causing issues with the overall page layout~~
  > This issue has been resolved, refer to [Notes](#notes) item 1 for details.
* The tags in the "Statistics" section of the page do not sort as expected, either by "Latest" or "Most", perhaps due to a Liquid syntax issue that cannot be resolved at this time.

## Notes

1. When using AdGuard or similar browser extensions, do not enable **Web Annoyances Ultralist** (`Filters > Annoyances > Web Annoyances Ultralist`). This rule can cause certain styles to be overridden by the browser's default styles, leading to abnormal page styling.
2. Optimizable details:
   * Currently, the image resources are all in `jpg` format, but `jpg` is not the best solution for web -- it has good compatibility, but low compression ratio. You may consider using `webp` instead of `jpg`, which is a newer format with better compression ratio.
     * For articles without a specified cover path, the default cover will be used. You can specify specify the path by modify the `default_cover_path` in the `config.yml`.
   * At current [main.css](./assets/css/main.css), the `Source Sans Pro` font is loaded via Google Fonts' CDN, but Google's CDN is usually unstable in China. If you deploying it in China, you may consider using other CDNs or downloading font file to your local machine for use.

## Original README from HTML5 UP

> The origin project is open source under the [CCA 3.0 license (Creative Cloud Attribution)](https://creativecommons.org/licenses/by/3.0/)

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

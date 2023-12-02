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
  * [x] Gitalk comments
  * [ ] Disqus comments

## Usage

### (1) Configuration

* Save it locally by `git clone` or downloading the zip file.
* Install Jekyll and its dependencies via `gem`

  ```bash
  apt install ruby ruby-dev gem -y # Ubuntu, other linux distributions please install manually
  gem install bundler jekyll # Install Jekyll and its basic components.

  # Install dependencies
  ## 1. Install the latest version of the dependencies by the following command: This may conflict with the versions specified in Gemfile and Gemfile.lock. Please delete these two files directly at this time.
  gem install addressable concurrent-ruby em-websocket http_parser.rb i18n, jekyll-feed, jekyll-paginate jekyll-sass-converter jekyll-seo-tag listen minima pathutil, public_suffix rouge sassc unicode-display_width webrick
  ## 2. Install the dependencies specified in Gemfile and Gemfile.lock by the following command: This will not conflict with the versions specified in Gemfile and Gemfile.lock. But personally, I think that the new version is usually not worse than the old version, so I still recommend the previous method.
  gem install addressable:2.8.1, concurrent-ruby:1.1.6, em-websocket:0.5.1, http_parser.rb:0.6.0, i18n:1.10.0, jekyll-feed:0.17.0, jekyll-paginate:1.1.0, jekyll-sass-converter:2.2.0, jekyll-seo-tag:2.8.0, listen:3.7.0, minima:2.5.1, pathutil:0.16.1, public_suffix:4.0.6, rouge:4.1.2, sassc:2.4.0, unicode-display_width:1.6.1, webrick:1.8.1
  ```

* Modify `_config.yml`, make it meet your needs.

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
  ---
  ```

* `layout`: Layout style, please fill in **post** to indicate that this article should use the "post" layout.
* `title`: Title, must not be left blank.
* `description`: Description, can be left blank or deleted directly (the absence of the `description` field is allowed).
* `author`: Author, when left blank or deleted, it will display the `username` field in `_config.yml`; if provided and
  different from `username`, it will use the content you provide.
* `date`: Publication date, please follow the format in the example. The `+0800` at the end indicates the GMT+8 time
  zone (Beijing time).
* `image`: Cover image of the article, when left blank or deleted, the default cover
  image [/images/default_cover.jpg](./images/default_cover.jpg) will be used.
* `stick`: Whether to pin it to the left side of the homepage. Leaving it blank or deleting it is equivalent to `false`.
  It is not recommended to have too many articles pinned.
* `tags`: Tags, used for filtering articles, multiple tags are allowed.
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

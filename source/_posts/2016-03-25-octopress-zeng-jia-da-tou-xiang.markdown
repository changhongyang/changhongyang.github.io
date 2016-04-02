---
layout: post
title: "Octopress 增加大頭像"
date: 2016-03-25 23:39:14 +0800
comments: true
categories: Octopress
---
1. 將大頭像放到octopress/source/images/目錄下

2. 編輯octopress/source/_includes/custom/asides/about.html:
<!--more-->
``` ruby
<section>
  <img alt="me" src="/images/me.jpg">
  <p>這次不記下來，下次必定重頭找過。</p>
</section>
```
3. 編輯_config.yml :

``` ruby
default_asides: [custom/asides/about.html, ...(略)...]
```
這樣就可以在側邊欄裡面增加大頭像了

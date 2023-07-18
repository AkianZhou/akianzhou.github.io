---
layout: post
title: Quickly generate posts
date: 2023-07-18 20:17 +0800
---
# 快速生成帖子方法
## 安装插件
**Add this line to your application's Gemfile:**

```gem 'jekyll-compose', group: [:jekyll_plugins]```

**And then execute:**

`$ bundle`

## 用法
```
  draft      # Creates a new draft post with the given NAME
  post       # Creates a new post with the given NAME
  publish    # Moves a draft into the _posts directory and sets the date
  unpublish  # Moves a post back into the _drafts directory
  page       # Creates a new page with the given NAME
  rename     # Moves a draft to a given NAME and sets the title
  compose    # Creates a new file with the given NAME
```

---
layout: post
title: Quickly generate posts
date: 2023-07-18 20:17 +0800
---
# Jekyll::Compose
---
使用命令简化Jekyll写作
## 安装
---
在你应用程序的Gemfile文件添加此行命令：

```
gem 'jekyll-compose', group: [:jekyll_plugins]
```

然后执行：
```
$ bundle
```

## 用法
安装后（见上文），运行`bundle exec jekyll help`，你能看到：
帮助中将会列出可用的新命令：
```
  draft      # Creates a new draft post with the given NAME
  post       # Creates a new post with the given NAME
  publish    # Moves a draft into the _posts directory and sets the date
  unpublish  # Moves a post back into the _drafts directory
  page       # Creates a new page with the given NAME
  rename     # Moves a draft to a given NAME and sets the title
  compose    # Creates a new file with the given NAME
```
创建你的新页面使用：
```
$ bundle exec jekyll page "My New Page"
```
创建你的新帖子：
```
$ bundle exec jekyll post "My New Post"
# 或者为yaml元数据属性指定自定义格式
$ bundle exec jekyll post "My New Post" --timestamp-format "%Y-%m-%d %H:%M:%S %z"
```
```
# 或者使用撰写命令
$ bundle exec jekyll compose "My New Post"
```
```
# 或者使用撰写命令指定帖子
$ bundle exec jekyll compose "My New Post" --post
```
```
# 或者使用撰写命令指定帖子集
$ bundle exec jekyll compose "My New Post" --collection "posts"
```
创建新的草稿使用：
```
$ bundle exec jekyll draft "My new draft"
```
```
# 或者使用撰写命令指定草稿
$ bundle exec jekyll compose "My new draft" --draft
```
```
# 或者使用撰写命令指定草稿集
$ bundle exec jekyll compose "My new draft" --collection "drafts"
```
重命名你的稿子使用：
```
$ bundle exec jekyll rename _drafts/my-new-draft.md "My Renamed Draft"
```
```
# 或者重命名回来
$ bundle exec jekyll rename _drafts/my-renamed-draft.md "My new draft"
```
发布你的稿子使用：
```
$ bundle exec jekyll publish _drafts/my-new-draft.md
```
```
# 或者指定发布的具体日期
$ bundle exec jekyll publish _drafts/my-new-draft.md --date 2014-01-24
# 或者为yaml元数据日期属性指定自定义格式
$ bundle exec jekyll publish _drafts/my-new-draft.md --timestamp-format "%Y-%m-%d %H:%M:%S %z"
```
重命名你的帖子使用：
```
$ bundle exec jekyll rename _posts/2014-01-24-my-new-draft.md "My New Post"
```
```
# 或者指定具体的日期
$ bundle exec jekyll rename _posts/2014-01-24-my-new-post.md "My Old Post" --date "2012-03-04"
```
```
# 或者指定当前的日期
$ bundle exec jekyll rename _posts/2012-03-04-my-old-post.md "My New Post" --now
```
取消你的发布使用：
```
$ bundle exec jekyll unpublish _posts/2014-01-24-my-new-draft.md
```
在指定集合创建新文件使用：
```
$ bundle exec jekyll compose "My New Thing" --collection "things"
```
## 配置
---
如果需要自定义默认插件配置，请编辑jekyll配置文件的`jekyll_compose`部分
### 在你的编辑器中自动打开新的草稿或者帖子
```
  jekyll_compose:
    auto_open: true
```
并确保你设置了`EDITOR`, `VISUAL` or `JEKYLL_EDITOR`环境变量。例如，如果你想在Atom编辑器自动打开新的帖子和草稿，你能添加以下命令在你的脚本配置：
```
export JEKYLL_EDITOR=atom
```
`JEKYLL_EDITOR`将覆盖默认的`EDITOR`或`VISUAL`的值.`VISUAL`将会覆盖默认的`EDITOR`的值.
### 设置草稿和帖子默认的元数据
如果你希望添加默认的元数据到新创建的帖子和稿子，你可以在`default_front_matter`配置键下进行配置，例如：
```
jekyll_compose:
  default_front_matter:
    drafts:
      description:
      image:
      category:
      tags:
    posts:
      description:
      image:
      category:
      tags:
      published: false
      sitemap: false
```
以下也会自动添加
- date属性下的创建时间戳
- title属性下标题属性
对于集合，你使用`default_front_matter`添加默认的元数据到新创建的集合文件中，集合名称作为配置键，例如集合的`things`
```
jekyll_compose:
  default_front_matter:
    things:
      description:
      image:
      category:
      tags:
```
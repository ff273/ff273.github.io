---
layout: post
title: github pages+jekyll
date: 2024-03-12 17:14 +0800
---
### github pages  
ruby项目
### jekyll 
一个Ruby Gem
功能 ： Transform your plain text into static websites and blogs.   
在Gemfile中配置：`gem "jekyll-theme-chirpy", "~> 6.0"`   
### chirpy：
一种jekyll的主题
### jekyll-compose 
也是一个 Ruby Gem   
理解为一个插件用于post    
地址：<https://github.com/jekyll/jekyll-compose>   
在Gemfile中配置：`gem 'jekyll-compose', group: [:jekyll_plugins]`    

## Gemfile配置
参考：
* 别人的chirpy主题仓库<https://github.com/ProphetHJK/prophethjk.github.io/blob/master/Gemfile>
* 我的仓库fork from <https://github.com/cotes2020/chirpy-starter>

## HowToPost
参考chirpy官方文件：<https://chirpy.cotes.page/posts/write-a-new-post/>   
**jekyll-compose**使用 （方法见<https://github.com/jekyll/jekyll-compose>）to post   
bundle exec jekyll help ：查看jekyll指令   

## Running Local Server(更新后，先在本地预览网页)
bundle exec jekyll s



## 我的总结：
1.创建仓库命名为：username.github.io
注意！！如果使用chirpy scheme 可以按照https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter 中指引直接fork仓库

2.在仓库username.github.io的settings中设置Pages对应的branch
![image](https://github.com/ff273/ff273.github.io/assets/102291200/b30ce465-b1d9-4762-b3c1-8285cb233c2c)

3.clone到本地进行个性化配置：
 _config.yml 
 _data/contact.yml.
 ps.具体修改哪些内容可在https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter 中查看

4.下载 Node.js(https://nodejs.org/en), and then run the tool:
$ bash tools/init

5.push到github即完成配置和部署
 
注意settings->pages->branch设置
 _config.yml 中修改内容是否正确

 ## Getting started｜Chirpy
 https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter

# Chirpy Starter [![Gem Version](https://img.shields.io/gem/v/jekyll-theme-chirpy)](https://rubygems.org/gems/jekyll-theme-chirpy) [![GitHub license](https://img.shields.io/github/license/cotes2020/chirpy-starter.svg?color=blue)][mit]

When installing the [**Chirpy**][chirpy] theme through [RubyGems.org][gem], Jekyll can only read files in the folders `/_data`, `/_layouts`, `/_includes`, `/_sass` and `/assets`, as well as a small part of options of the `/_config.yml` file from the theme's gem. If you have ever installed this theme gem, you can use the command `bundle info --path jekyll-theme-chirpy` to locate these files.

The Jekyll team claims that this is to leave the ball in the user’s court, but this also results in users not being able to enjoy the out-of-the-box experience when using feature-rich themes.

To fully use all the features of **Chirpy**, you need to copy the other critical files from the theme's gem to your Jekyll site. The following is a list of targets:

```shell
.
├── _config.yml
├── _plugins
├── _tabs
└── index.html
```

To save you time, and also in case you lose some files while copying, we extract those files/configurations of the latest version of the **Chirpy** theme and the [CD][CD] workflow to here, so that you can start writing in minutes.

## Prerequisites

Follow the instructions in the [Jekyll Docs](https://jekyllrb.com/docs/installation/) to complete the installation of the basic environment. [Git](https://git-scm.com/) also needs to be installed.

## Installation

Sign in to GitHub and [**use this template**][use-template] to generate a brand new repository and name it `USERNAME.github.io`, where `USERNAME` represents your GitHub username.

Then clone it to your local machine and run:

```
$ bundle
```

## Usage

Please see the [theme's docs](https://github.com/cotes2020/jekyll-theme-chirpy#documentation).

## License

This work is published under [MIT][mit] License.

[gem]: https://rubygems.org/gems/jekyll-theme-chirpy
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[use-template]: https://github.com/cotes2020/chirpy-starter/generate
[CD]: https://en.wikipedia.org/wiki/Continuous_deployment
[mit]: https://github.com/cotes2020/chirpy-starter/blob/master/LICENSE

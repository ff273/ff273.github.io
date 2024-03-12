---
layout: post
title: Ruby生态（通过python生态角度理解）
date: 2024-03-12 17:18 +0800
---
## What's Ruby、Gem、Bundle？
Ruby、Gem 和 Bundle 是在 Ruby 生态系统中密切相关的三个概念，它们一起构成了 Ruby 开发的基本工具链。以下是它们之间关系的解释：
1. **Ruby:**   
  * 概述： Ruby 是一种动态、面向对象、通用的编程语言。它的设计注重简洁性和开发者友好性。   
2. **Gem:**   
  * **概述**： RubyGems 是 Ruby 的包管理系统，它允许开发者将他们的代码打包成 Gem，并且可以通过 RubyGems 官方仓库或其他仓库进行分发。每个 Gem 文件包含了一个或多个 Ruby 文件、文档、测试以及元信息。   
  * **角色**： 开发者可以使用 Gem 来打包和分享他们的代码，同时也可以通过 Gem 来安装和管理其他开发者创建的 Gem。Gem 管理了 Ruby 项目的依赖关系，使得代码的共享和复用更为方便。   
3. **Bundle:**   
  * **概述**： Bundle 是一个与 Ruby 项目的依赖关系管理工具，通常与 Gemfile 配合使用。它基于项目的 Gemfile 文件，确保在不同环境中安装和使用正确版本的 Gem。   
  * **角色**： 在 Ruby 项目中，开发者使用 Gemfile 文件列出项目所需的 Gem 和其版本。Bundle 确保这些 Gem 的正确版本被安装，避免由于不同环境中 Gem 版本不同而引发的问题。   
综合关系：   
* Ruby 提供了编程语言和执行环境。   
* Gem 是 Ruby 的包管理系统，用于分发和管理 Ruby 代码。   
* 在 Ruby 项目中，Bundle 通过管理 Gemfile 来确保项目的依赖关系得到满足。   
因此，这三者共同构成了 Ruby 开发的基础工具链，使得 Ruby 项目的创建、共享和维护变得更加方便。

## 类比python，解释Ruby生态
在 Ruby 中，我们有 Ruby、Gem、和 Bundle；在 Python 中，我们有 Python、pip、和 virtualenv 或 Poetry。
1. 编程语言和执行环境：
  * Ruby：提供了 Ruby 编程语言和执行环境。
  * Python：提供了 Python 编程语言和执行环境。
2. 包管理系统：
  * Gem（Ruby）：用于分发和管理 Ruby 库和程序。
  * pip（Python）：用于安装、管理和分发 Python 包。
3. 项目依赖管理：
- Bundle（Ruby）：用于管理 Ruby 项目的依赖关系，通过 Gemfile 确保正确的 Gem 版本被安装。
- virtualenv 或 Poetry（Python）
- - virtualenv：用于创建 Python 虚拟环境，确保项目有独立的 Python 环境，以防止依赖冲突。
- - Poetry：一个整合包管理、构建和发布功能的工具，简化 Python 项目的依赖管理和构建流程。
- - 在 Python 中，虚拟环境通常是通过使用 venv 模块或第三方工具如 virtualenv 来创建和管理的。这些虚拟环境的创建和管理工具使得你能够在不同的项目中使用不同的 Python 版本和包版本，避免了项目之间的依赖冲突。如果使用 Conda 虚拟环境，通常不需要再使用 Python 的传统虚拟环境管理工具。Conda 提供了一个独立的环境管理系统，能够更全面地处理包依赖关系，并且具有更强大的跨平台性。
4. 项目结构和共享代码：
  * Gem（Ruby）：Gem 通常包含 Ruby 代码、文档、测试等，通过 RubyGems 仓库共享。
  * Python 包（Python）：Python 包包含 Python 模块、库和工具，通过 PyPI（Python Package Index）仓库共享。   

综合而言，Ruby 和 Python 生态系统都有自己的编程语言、包管理系统以及项目依赖管理工具。Gem 和 pip 在各自的生态系统中扮演着类似的角色，用于简化代码的分发、共享和依赖管理。Bundle（Ruby）、virtualenv 和 Poetry（Python）用于确保项目的依赖关系得到满足，并提供项目隔离和独立的环境。

gem install Ruby包（Gem文件）   
pip install Python包    
 
bundle基于gemfile保证环境隔离   
conda环境（包含python虚拟环境） 

## gem&bundle指令
Gemfile<https://www.educative.io/answers/what-is-a-gemfile>   
bundle的常用命令<https://blog.csdn.net/Toml_/article/details/130831910>   
bundle==bundle install ： 安装所有在 Gemfile 中列出的 gem 包及其依赖项。   
bundle env : 查看bundle环境   

## 更换gem源
gem install 太慢——>尝试更换gem源：（参考<https://www.twle.cn/l/yufei/ruby/ruby-basic-gem-mirrors.html>）   
gem sources -l : 查看gem源   
gem sources --remove <https://rubygems.org/> ：移除源   
$ gem sources -a <https://mirrors.tuna.tsinghua.edu.cn/rubygems/> ： 添加下载源   

## 更新ruby版本
which ruby ：查看ruby可执行文件位置  
brew install ruby ：通过homebrew下载新版本ruby  
会默认下载到默认地址，查看bundle env发现ruby path和下载默认地址不同，所以可执行的ruby还是老版本  
![brew install ruby后输出的更换环境变量指引](/assets/image/ruby.png)    
按照说明，添加环境变量LDFLAGS、CPPFLAGS   
（vim ~/.bash_profile 加入   
export LDFLAGS="-L/opt/homebrew/opt/ruby/lib"    
export CPPFLAGS="-I/opt/homebrew/opt/ruby/include"）   
（不要直接export，只对当前终端会话生效）（参考<https://zhuanlan.zhihu.com/p/647191643>）   
添加PATH到~/.zshrc   
重启终端后，重试 $which ruby，发现修改了执行路径  


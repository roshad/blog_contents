---
title: 想让某文件夹，同步到两个git repo中，应如何做？
date: 2024-03-28
tags:
  - git
---
- 将被容纳的文件夹，创建为git 独立的repo。然后分别将其添加为两repo的 submodule
- 语法为 git submodule add <url_of_blog_content_repo> <repo_path> <想要的路径>

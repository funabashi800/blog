+++
author = "Takahiro Suzuki"
categories = ["GitHub Pages"]
date = "2019-08-27"
description = "Let's start to deploy your static site with GitHub pages"
featured = "pic05.gif"
featuredalt = "Pic 5"
featuredpath = "date"
linktitle = ""
title = "How to deploy a static web site to GitHub pages"
type = "post"

+++

Hello everyone🤩! This post will show you how to deploy your static site to GitHub pages. In the last post, I introduced you to how to deploy HUGO's static website to Amazon S3, but one of the consciousness must be the price. As far as a free tier, S3 will provide **5G in standard S3 storage**, **20,000 GET/mon**, and **2,000 PUT/mon**. It would be charitable, and generous service, but you might still worry about if you should check out, specifically student.  On the other hand, "GitHub pages" is **free**.

Let's cut to the chase quickly! I think many of you have been using GitHub as a git version control. Have you ever doubted how to deploy static built file from ```/public``` or ```/dist```, directory to GitHub pages?? GitHub pages will allow you to build static pages in your master branch, master brach (docs file), or gh_pg branch.

### 1. Create a repository for hosting (GitHub pages)
You might as well have 2 repositories to deploy, one is for normal developing (**Project repository**), and the other is for only hosting (**Hosting repository**).

**NOTE**. you have to identify your ***repository name*** like ```[GitHub Username].github.io```, otherwise, some paths to local file wouldn't work.

### 2. Add your hosting repository to project repository as a submodule

```zsh
$ cd [Project repository]

# NOTE: before exceting blow command, you might as well delete a folder where static site is located
# atatch hosting repository to a file where static site is located
$ git submodule add -b master git@github.com:[USERNAME]/[USERNAME].github.io.git public
```

### 3. Build again
Finally, build your application into a static site, and you can just commit and push as you do normally. Done!!

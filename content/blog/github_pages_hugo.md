+++
title = "使用Github Pages和Hugo搭建个人博客"
date = "2025-07-12T20:23:26+08:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = [
    "Hugo",
    "Github"
]
+++

## 安装Hugo
以Arch为例，运行 `pacman -S hugo` 即可安装Hugo。

## 创建Hugo项目
### 新建Hugo项目
使用 `hugo new site <项目名称>` 创建一个新的博客项目，在当前目录下生成一个自定义名称的Hugo项目。

### 导入主题
在 [themes.gohugo.io](https://themes.gohugo.io/) 中挑选自己喜欢的主题，点击**download**跳转到github页面，在已经创建的Hugo项目根目录下运行 `git submodule add <仓库链接> themes/<主题名称>` 即可下载，例如：
```shell
git submodule add https://github.com/janraasch/hugo-bearblog.git themes/hugo-bearblog
```
下载的主题在Hugo项目的theme目录下，修改 `hugo.toml` 配置文件，增加 `theme = '<主题名称>'` 可以使用指定主题，或者将 `theme/exampleSite/hugo.toml` 拷贝到Hugo项目根路径下（有些主题没有exampleSite）。

### 创建文章
使用 `hugo new <Markdown文件路径>` 可以新建Markdown文件，创建的Markdown文件在 `content` 目录下。
下面创建两个 `_index.md` 文件和一个普通的Markdown文件，`_index.md` 文件作为所在目录的首页：
```shell
hugo new _index.md
hugo new blog/_index.md
hugo new blog/my-new-page.md
```
`_index.md` 文件头部内容可能为（内容根据实际修改）：
```markdown
+++
title = "Home"  # 页面标题
menu = "main"   # 所在菜单
weight = 1      # 排序
+++
```
使用 `hugo server -D` 以构建和部署项目，在打印的信息中可以找到URL并访问查看效果。

## 上传到Github Pages
在Github上创建自己的Github Pages项目，回到本地，修改Hugo跟目录 `hugo.toml` 中的baseURL为刚刚创建的Github Pages地址，一般 `https://<github名称>.github.io`，在项目根目录运行 `hugo` 译该项目，在 `public` 录下会生成项目文件。进入 `public` 目录，将public项目推送到Github Pages仓库：
```shell
git init
git remote add origin <Github Pages仓库地址>
git branch -M main
git add -A .
git commit -m "<自定义提交信息>"
git push -u origin main
```
访问 `https://<github名称>.github.io` 查看效果。

## Hugo主题推荐
- [xmin](https://themes.gohugo.io/themes/hugo-xmin/)
- [bearblog](https://themes.gohugo.io/themes/hugo-bearblog/)
- [Anubis2](https://themes.gohugo.io/themes/hugo-theme-anubis2/)
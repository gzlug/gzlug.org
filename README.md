gzlug.org
------------

这是 [广州 GNU/Linux 用户组][l] 网站的源代码，原来采用 WordPress，现迁移到 Pelican，其中包括：

- content：所有文章，为 Markdown 格式
- pelican-themes：Pelican 主题
- pelicanconf.py：Pelican 配置文件
- develop_server.sh：开发脚本
- Makefile：Make 构建脚本
- requirements.txt: 依赖的Python包

Master 分支为Source，gp-pages 分支为生成的静态文件。

### 如何使用

请参照 [Pelican 快速入门][p] 安装 Pelican。

### 新建文章
所有新建文章请以年份开头，图片请按照年份放置在 images/ 文件夹中。  
为了保持一致性，推荐使用 Markdown 格式，主要包括文章元数据和正文两个部分，例如：  

    Title: (标题)
    Date: 2010-12-03 10:20 (创建日期)
    Modified: 2010-12-05 19:30 (修改日期)
    Category: Python (分类，只能使用单一分类)
    Tags: pelican, publishing (标签，多个以 , 分隔)
    Slug: my-super-post (slug，将用于 url，请与文件名保持一致)
    Authors: (作者，多个以 , 分隔)
    Summary: (摘要)

    这是正文。

### 关于摘要

我们一般把文章第一段作为摘要，但 Pelican 的摘要功能只会将其显示在首页，而文章本身所在页面却并不显示。因此推荐使用以下方式来产生摘要，只需将其添加到第一段之后即可：

    <!-- PELICAN_END_SUMMARY -->

### 添加代码

在撰文时，可对引用代码添加语法高亮显示，记法如下：

    A block of text. (正常文本)

        :::identifier (标识符，如 python)
        <code goes here> (具体的代码)

### Vim 支持

若你使用 Vim 文本编辑器，那么可以在 .vimrc 中定义如下函数并绑定快捷键 `_ + m`，这样能够快速生成文章元数据：

```viml
"-- Markdown header --"
function! MarkdownHeader()
let date = strftime("%Y-%m-%d %T")
exe "normal iTitle: "
exe "normal oDate: " . date
exe "normal oAuthors: "
exe "normal oCategory: "
exe "normal oTags: "
exe "normal oSlug: "
exe "normal o"
endfunction

nmap _m :call MarkdownHeader()<cr>
```

### 欢迎贡献

广州 GNU/Linux 用户组是非商业、非盈利的地方互助组织，gzlug.org 主要用于发布线下活动通知以及知识分享，欢迎大家提PR，分享文章或发起聚会，谢谢。

### 版权许可

这份 ReadMe fork 自 [xuxiaodong/linuxtoy.org](https://github.com/xuxiaodong/linuxtoy.org/blob/master/README.md)

本网站文字及图片内容遵循“[署名-非商业性使用-相同方式共享 2.5 中国大陆][c]”的创作共用协议。

[l]: http://gzlug.org
[p]: http://docs.getpelican.com/en/3.5.0/quickstart.html
[c]: http://creativecommons.org/licenses/by-nc-sa/2.5/cn/

* 这份ReadMe fork from [xuxiaodong/linuxtoy.org](https://github.com/xuxiaodong/linuxtoy.org/blob/master/README.md) *

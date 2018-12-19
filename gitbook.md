## 是什么?
实际上，GitBook 是一个基于 Node.js 的命令行工具，支持 Markdown 和 AsciiDoc 两种语法格式，可以输出
HTML、PDF、eBook 等格式的电子书。所以我更喜欢把 GitBook 定义为文档格式转换工具。

## 怎么使用
　　想象一下，现在你准备构建一本书籍，你在硬盘上新建了一个叫 mybook 的文件夹，按照以前的做法，你会新建一个 Word 文档，写上标题，然后开始巴滋巴滋地笔耕。但是现在有了 GitBook，你首先要做的是在 mybook 文件夹下执行以下命令：

> gitbook init

执行完后，你会看到多了两个文件 —— README.md 和 SUMMARY.md，它们的作用如下：

> * README.md —— 书籍的介绍写在这个文件里
* SUMMARY.md —— 书籍的目录结构在这里配置

接着我们执行 gitbook serve 来预览这本书籍，执行命令后会对 Markdown 格式的文档进行转换，默认转换为 html 格式，最后提示 “Serving book on http://localhost:4000 ”。嗯，打开浏览器看一下吧：

当你写得差不多，你可以执行 gitbook build 命令构建书籍，默认将生成的静态网站输出到 _book 目录。实际上，这一步也包含在 gitbook serve 里面，因为它们是 HTML，所以 GitBook 通过 Node.js 给你提供服务了。
　　当然，build 命令可以指定路径：

> gitbook build [书籍路径] [输出路径]

serve 命令也可以指定端口：

> gitbook serve --port 2333

你还可以生成 PDF 格式的电子书：

> gitbook pdf ./ ./mybook.pdf

生成 epub 格式的电子书：
> gitbook epub ./ ./mybook.epub

生成 mobi 格式的电子书：

> gitbook mobi ./ ./mybook.mobi

除此之外，别忘了还可以用 Git 做版本管理呀！在 mybook 目录下执行 git init 初始化仓库，执行 git remote add 添加远程仓库（你得先在远端建好）。接着就可以愉快地 commit，push，pull … 啦！

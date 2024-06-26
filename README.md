composer-doc-cn
===============

Composer 中文文档

---

- 希望更多的朋友能够参与此文档的翻译、勘误（您可以 Fork 本项目，并提交 Pull Request）。
- 新版本文档翻译缓慢进行中，详见 [1.6分支](https://github.com/5-say/composer-doc-cn/blob/1.6/README.md)
- 当前文档基本不影响新版 Composer 的使用，新文档在结构以及章节内容上做了比较大的调整，针对性的翻译会逐步完善。
- [中文翻译贡献者名单](/contributors.md)

---

## Book
- [简介](/00-intro.md)
- [基本用法](/01-basic-usage.md)
- [库（资源包）](/02-libraries.md)
- [命令行](/03-cli.md)
- [架构](/04-schema.md)
- [资源库](/05-repositories.md)
- [社区](/06-config)

## Articles
- [别名](/articles/aliases.md)  
版本分支名称的别名。
- [自定义安装程序](/articles/custom-installers.md)  
修改某些特殊类型包的安装方式。
- [Handling Private Packages With Satis](/articles/handling-private-packages-with-satis.md)  
Host your own composer repository
- [插件](/articles/plugins.md)  
修改和扩展 Composer 的功能。
- [脚本](/articles/scripts.md)  
脚本是指一些 Composer 事件的回调，它们在安装资源包的过程中被触发执行。
- [Troubleshooting](/articles/troubleshooting.md)  
Solving problems
- [二进制供应库](/articles/vendor-binaries.md)  
从资源包中暴露命令行脚本。

## FAQs

- [如何为我的框架自定义一个资源包安装目录？](/faq/how-do-i-install-a-package-to-a-custom-path-for-my-framework.md)
- [我应该提交 vendor 目录中的依赖包吗？](/faq/should-i-commit-the-dependencies-in-my-vendor-directory.md)
- [为什么说“比较符”和“通配符”相结合的版本约束是坏主意？](/faq/why-are-version-constraints-combining-comparisons-and-wildcards-a-bad-idea.md)
- [为什么 Composer 不递归加载储存库？](/faq/why-can%27t-composer-load-repositories-recursively.md)

## 相关文章推荐

- [PHP 开发者该知道的5个 Composer 小技巧](http://segmentfault.com/a/1190000000355928)

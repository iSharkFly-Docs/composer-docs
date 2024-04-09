# 我应该提交 vendor 目录中的依赖包吗

一般情况下 **不建议**。vendor 目录（或者你安装依赖的其它目录）都应该被添加进 `.gitignore`/`svn:ignore`/等等。

最好这么做，然后让所有开发人员使用 Composer 来安装依赖包。同样的，对构建服务器，CI，部署工具等，应在编译构建的时候对项目进行修改修改，使运行
Composer 成为其项目引导的一部分。

虽然在某些环境下我们也是可以提交 vendor 目录的，但它将导致一些问题：

- 当你更新代码时，将极大的增加 VCS 仓库的体积和差异。
- 在你自己的 VCS（代码管理工具） 中将产生与你依赖的资源包重复的历史记录。
- 通过 git 的一个 git 仓库安装添加依赖，将把它们视作子模块。这是有问题的，因为它们并不是真正的子模块，你的项目在运行的时候可能会出现问题。

如果你真的觉得你必须这样做，你有几个选择：

1. 限制自己安装标记为发布（releases ）的版本（无 dev 版本），这样你只会得到 zip 压缩的安装，并避免 git“子模块”出现的问题。
2. 使用 --prefer-dist 或在 [config](../06-config.md) 选项中设置 `preferred-install` 为 `dist`。
3. 在每一个依赖安装后删除其下的 `.git` 文件夹，然后你就可以添加它们到你的 git repo 中。你可以在 ZSH
   中运行 `rm -rf vendor/**/.git` 或者在 Bash 中运行`find vendor/ -type d -name ".git" -exec rm -rf {} \;`。但这意味着你在运行
   composer update 命令前需要先删除磁盘中的依赖文件。
4. 新增一个 .gitignore 规则（`/vendor/**/.git`）来忽略 vendor 下所有 `.git` 目录。这种方法不需要你在运行 composer update
   命令前删除你磁盘中的依赖文件。

通过上面的文字内容，我们知道在使用 Composer 项目的时候，我们不要把 vendor 中的内容也提交到代码管理库中，而应该使用 Composer
自己在运行的时候下载。

如果我们通过标准的 git ignore 文件生成器来生成 composer 的ignore 文件的话，我们也看到上面提示忽略的内容。

```text
# Created by https://www.toptal.com/developers/gitignore/api/composer
# Edit at https://www.toptal.com/developers/gitignore?templates=composer

### Composer ###
composer.phar
/vendor/

# Commit your application's lock file https://getcomposer.org/doc/01-basic-usage.md#commit-your-composer-lock-file-to-version-control
# You may choose to ignore a library lock file http://getcomposer.org/doc/02-libraries.md#lock-file
# composer.lock

# End of https://www.toptal.com/developers/gitignore/api/composer
```

# Hey everyone, this is Lydocan's new Blog

> updated at 2018/01/06.

## 项目目录结构

- backup
- node_modules 
项目依赖的模块，一般由npm命令生成并管理该文件夹
- public 
生成的一些网页资源文件
- scaffolds 
模版文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。

Hexo的模板是指在新建的markdown文件中默认填充的内容。例如，如果您修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改。
- source 
资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。
- themes 
主题文件夹。Hexo 会根据主题来生成静态页面。
- _config.yml
网站的配置信息，可以在此配置大部分参数。

## hexo使用指南

1. 发表文章，然后编辑文本
2. 启动本地服务器查看效果（可选）
3. 生成网页
4. 部署到github服务器

### 发表文章
```(shell)
hexo new [layout] title
```

### 发表草稿
```(shell)
hexo publish [layout] <filename>
```

### 服务器
```(shell)
静态模式(只处理public)
hexo server -s

自定义IP
hexo server -i 192.168.1.1

hexo server [-p xxxx]
```

### 清空public目录

`hexo clean`

### 生成器

`hexo generate --watch`


### 部署
`hexo deploy`

### 完成后部署
`hexo deploy --generate`

### 绑定域名

每次部署后，在github上设置好的域名会被清空，怎么办？

在source目录下添加名为CNAME的文件，然后写入自己博客的域名即可。

部署时会把source目录下的文件推动到github上，CNAME会记录github博客域名的别名，可以设置为你自己的域名。

### 发表图片

绝对路径方式：在source目录下添加，例如source/images/1.jpg，此时图片路径填`/images/1.jpg`。

相对路径方式：

图片除了可以放在统一的`images`文件夹中，还可以放在文章自己的目录中。文章的目录可以通过配置`_config.yml`来生成。

```
_config.ymlpost_asset_folder: true
```

将`_config.yml`文件中的配置项`post_asset_folder`设为`true`后，执行命令`$ hexo new post_name`，在`source/_posts`中会生成文章`post_name.md`和同名文件夹`post_name`。将图片资源放在`post_name`中，文章就可以使用相对路径引用图片资源了。

```
_posts/post_name/image.jpg![](image.jpg)
```

### 存在的问题
1. 每次提交更新，不管是push master的分支，还是hexo deploy提交gh-pages的分支，都要重新设置项目的custom domain。
2. 每次hexo deploy部署的时间都比较久。


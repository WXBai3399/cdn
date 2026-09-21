# jsDeliver+github使用教程，免费的cdn

前言：CDN的全称是Content Delivery Network，即内容分发网络。CDN是构建在网络之上的内容分发网络，依靠部署在各地的边缘服务器，通过中心平台的负载均衡、内容分发、调度等功能模块，使用户就近获取所需内容，降低网络拥塞，提高用户访问响应速度和命中率。CDN的关键技术主要有内容存储和分发技术。

国内加载github的资源比较慢，需要使用CDN加速来优化网站打开速度，于是使用jsDeliver+github搭建免费的CDN，非常适合博客网站使用。

jsDelivr 是一个免费开源的 CDN 解决方案，用于帮助开发者和站长。包含 JavaScript 库、jQuery 插件、CSS 框架、字体等等 Web 上常用的静态资源。

下图我们可以看到他似乎和npm,github,wordpress有某种py关系。[点击访问jsDelivr主页](https://www.jsdelivr.com/)

![img](https://cdn.jsdelivr.net/gh/honjun/ImageHosting/sina/006bYVyvly1fzarmsp5msj30ts0jojsb.jpg)

NPM是JavaScript的包管理器，也是世界上最大的软件注册中心。发现可重用代码的包——并以强大的新方式组装它们。每星期大约有 30 亿次的下载量，包含超过 600000 个 包（package） （即，代码模块）。来自各大洲的开源软件开发者使用 npm 互相分享和借鉴。包的结构使您能够轻松跟踪依赖项和版本。

所以jsDeliver+npm就是把npm上的包当做cdn的存储。
使用教程：（jsDeliver不支持加载超过20M的资源，所以一些视频最好压缩到20M以下）

```
// load any project hosted on npm
// 加载以NPM为存储的任何项目
https://cdn.jsdelivr.net/npm/package@version/file
// load jQuery v3.2.1
// 比如加载Jquery3.2.1
https://cdn.jsdelivr.net/npm/jquery@3.2.1/dist/jquery.min.js
// use a version range instead of a specific version
//使用版本范围而不是特定版本
https://cdn.jsdelivr.net/npm/jquery@3.2/dist/jquery.min.js
https://cdn.jsdelivr.net/npm/jquery@3/dist/jquery.min.js
// omit the version completely to get the latest one
//完全忽略版本以获取最新版本，不建议使用
https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js
略......
```

### Github

![img](https://cdn.jsdelivr.net/gh/honjun/ImageHosting/sina/006bYVyvly1fzatzue2tkj31340jewey.jpg)

gitHub是一个面向开源及私有软件项目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名gitHub。
jsDeliver+Github使用教程：

```
// load any GitHub release, commit, or branch
// 加载任何Github发布、提交或分支
https://cdn.jsdelivr.net/gh/user/repo@version/file
略......
```

### WordPress

![img](https://cdn.jsdelivr.net/gh/honjun/ImageHosting/sina/006bYVyvly1fzau28wpj5j30x70jp3yq.jpg)
WordPress是一款个人博客系统，并逐步演化成一款内容管理系统软件，它是使用PHP语言和MySQL数据库开发的。用户可以在支持 PHP 和 MySQL数据库的服务器上使用自己的博客。
jsDeliver+WordPress使用教程：

```
// load any plugin from the WordPress.org plugins SVN repo
// 从WordPress.org等SVN仓库加载任何插件
https://cdn.jsdelivr.net/wp/plugins/project/tags/version/file
略......
```

这里我们介绍使用的是jsDeliver+github，所以接下来只介绍这部分使用。

## 第一步：新建github仓库

![img](https://cdn.jsdelivr.net/gh/Zevs6/CDN/img/repository.png)

## 第二步：克隆Github仓库到本地

![img](https://cdn.jsdelivr.net/gh/Zevs6/CDN/img/download.png)

$ git clone 你的仓库链接 # 本地克隆github仓库

## 第三步：上传需要的资源

在本地目录右键 Git Bash Here

复制需要的静态资源到本地git仓库中，提交到github仓库上。
命令如下：

```
// 查看状态
git status
// 添加到库中
git add .
// 提交更新（引号内 为自定义信息说明）
git commit -m '第一次提交'
// 推送至远程仓库 
git push
```

## 第四步：发布仓库

点击release发布

![img](https://cdn.jsdelivr.net/gh/Zevs6/CDN/img/release.png)

发布版本号为1.0（自定义）

![img](https://cdn.jsdelivr.net/gh/Zevs6/CDN/img/release1.png)

## 第五步：通过jsDeliver引用资源

使用方法：
https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名@发布的版本号/文件路径
比如：
//加载图片
https://cdn.jsdelivr.net/gh/Zevs6/CDN/img/avatar.jpg

注意：版本号不是必需的，是为了区分新旧资源，如果不使用版本号，将会直接引用最新资源，除此之外还可以使用某个范围内的版本，查看所有资源等，具体使用方法如下：

- // 加载任何Github发布、提交或分支
  https://cdn.jsdelivr.net/gh/user/repo@version/file
- // 加载 jQuery v3.2.1
  https://cdn.jsdelivr.net/gh/jquery/jquery@3.2.1/dist/jquery.min.js
- // 使用版本范围而不是特定版本
  https://cdn.jsdelivr.net/gh/jquery/jquery@3.2/dist/jquery.min.js
  https://cdn.jsdelivr.net/gh/jquery/jquery@3/dist/jquery.min.js
- // 完全省略该版本以获取最新版本
  https://cdn.jsdelivr.net/gh/jquery/jquery/dist/jquery.min.js
- // 将“.min”添加到任何JS/CSS文件中以获取缩小版本，如果不存在，将为会自动生成
  https://cdn.jsdelivr.net/gh/jquery/jquery@3.2.1/src/core.min.js
- // 在末尾添加 / 以获取资源目录列表
  https://cdn.jsdelivr.net/gh/jquery/jquery/


使用 jsDelivr

jsDelivr 是一个免费的公共 CDN 服务，可以将 GitHub 仓库中的文件直接转换为 CDN 链接。其基本格式为：


基本 URL 是https://cdn.jsdelivr.net/gh/{username}/{repo}/，
其中替换{username}为 GitHub 用户名和{repo}项目的存储库名称。
将该 URL 附加到您要在项目中访问的文件的路径

转换为 jsDelivr 的 CDN 地址：
https://cdn.jsdelivr.net/gh/WXBai3399/cdn@main/img/YourName.jpg

在 HTML 文件中引用：
```html
<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/1506085843/fillDiff@master/src/main/resources/css/diff2html.min.css" />
  </head>
  <body>
    <div>hello</div>
  </body>
</html>
```

@{version-number}您还可以通过添加到存储库名称来利用语义版本控制。您可以根据需要定位主要、次要和补丁版本。
```html
<!-- Always get the latest version -->
<!-- Not recommended for production sites! -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/atomic/dist/atomic.js"></script>

<!-- Get minor updates and patch fixes within a major version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/atomic@4/dist/atomic.js"></script>

<!-- Get patch fixes within a minor version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/atomic@4.0/dist/atomic.js"></script>

<!-- Get a specific version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/atomic@4.0.0/dist/atomic.js"></script>
```

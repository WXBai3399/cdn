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

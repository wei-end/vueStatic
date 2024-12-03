"scripts": {
"predeploy": "npm run build",
"deploy": "gh-pages -d dist -r git@github.com:wei-end/vueStatic.git -b gh-pages"
},

## npm run build 文件进行打包 

## npm run deploy 使用了 node的包 gh-pages 后面都是具体的命令
  
    这段 package.json 中的 scripts 配置是用于部署静态网站到GitHub Pages的命令。让我们逐个部分解释这个命令：

    "deploy": 这是npm脚本的键，表示这个脚本的名称是deploy。你可以通过运行 npm run deploy 来执行这个脚本。

    "gh-pages" 是一个npm包，它是一个命令行工具，用于将静态网站部署到GitHub Pages。

    -d dist 是gh-pages命令的一个选项，-d 表示--dest，即部署的目标分支。这里指定dist目录作为部署的内容，dist目录通常包含构建后的静态文件。

    -r git@github.com:wei-end/vueStatic.git 是gh-pages命令的一个选项，-r 表示--repo，即指定仓库的URL。这里指定了GitHub仓库的地址，用于推送gh-pages分支的内容。

    -b gh-pages 是gh-pages命令的一个选项，-b 表示--branch，即指定部署到的分支。这里指定为gh-pages分支，这是GitHub Pages服务用于托管静态网站的默认分支。

    综上所述，这个命令的作用是：使用gh-pages工具，将dist目录下的内容部署到GitHub仓库git@github.com:wei-end/vueStatic.git的gh-pages分支上，从而实现静态网站的托管和发布。

由于 项目在 github 上进行静态部署时 https:// <username(用户名)>.github.io/<repository-name(项目名称)>/ 是这样的格式
如果不设置 publicPath:'/vueStatic/' 那么访问的时候 publicPath默认是 '/' 是相对于根目录的 具体访问的时候就会 是空白页 访问不到页面 根目录就是 https:// <username(用户名)>.github.io/ 
github 把对应静态资源都放托管在了 /vueStatic/ 下
所以需要设置 publicPath:'/vueStatic/' 或者 publicPath: '.' 才能正确访问

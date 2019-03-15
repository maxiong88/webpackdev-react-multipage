# webpackdev-react-multipage

webpack-dev-server react react-hot-loader 多页面热更新 简易版

::: tip
在package.json里的script里使用了--hot
在webpack.config.js里调用了HotModuleReplacementPlugin,
会造成 `Maximum call stack size exceeded`
所以把webpack.config.js里的HotModuleReplacementPlugin去掉就好
:::

在配置文件中webpack.config.js中的entry写入

``` js
entry: {
	app:['react-hot-loader/patch','path路径']
}
```

在.babelrc文件中添加

``` js

{
    "plugins": ["react-hot-loader/babel"]
}

```

在每个入口文件中添加

``` js

if (module.hot) {
  module.hot.accept()
}

```

github:案例[https://github.com/maxiong88/webpackdev-react-multipage](https://github.com/maxiong88/webpackdev-react-multipage)

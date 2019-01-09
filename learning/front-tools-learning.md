# 前端学习 - 工具

参考：[入门 Webpack，看这篇就够了](https://mp.weixin.qq.com/s?__biz=MjM5NTEwMTAwNg==&mid=2650211216&idx=1&sn=d2a765e886016afcfebf4090b37cd2bf)

### npm（可类比composer）
- 配置文件
    - package.json
- 单一入口（啥？这是后端？...）
- 模块化

### Webpack
- 用途
    - 打包ES6 js文件、CSS、fonts、图片等
- 使用
    - 通过webpack命令 -> 通过配置文件webpack.config.js -> 通过设置npm "scripts"并执行npm start
- 配置选项
    - devtool：不同级别的source-map对应不同的打包速度和调试方便程度。
    - -dev-server。实时监测代码修改，终端显示。
    - loaders。指定文件类型进行转换。这样程序源文件（如配置文件）可以是json，最后变成可执行js文件。
    - css-loader，style-loader
- 插件
    - HtmlWebpackPlugin。根据模板生成HTML5文件（`不得了，模板都有了`）
    - 热更新。
        - 在插件中添加new webpack.HotModuleReplacementPlugin()，
        - 在devServer中添加hot参数。
        - 或者，添加Babel的react-transform-hrm插件。

### Babel
- 用途
    - 支持ES6、JSX。
- 为方便扩展，babel配置一般单独写在`.babelrc`文件（webpack将自动调用）

### CSS 模块化
- 用途
    - 不同模块之间类名不会冲突
- 使用
    - 在webpack配置的module oaders的loader名中指定`?modules`
    ```
    //webpack.config.js
    module > loaders > loader: 'style!css?modules'
    ```
    - postcss。处理Less、Sass...

### 产品阶段的构建
- 目的
    - 优化、压缩、分离CSS和JS
- 实现
    - 新建一个webpack.production.config.js存放针对生产环境的配置。
- 细节
    - OccurenceOrderPlugin
    - 压缩JS代码：UglifyJsPlugin
    - 分离CSS和JS文件：ExtractTextPlugin
    - 缓存
        ```
        //webpack.config.js
        output > filename: '[name]-[hash].js'
        ```
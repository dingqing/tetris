# tetris
使用React、Redux实现俄罗斯方块小游戏。

## 1.准备
### 目标
- 实现俄罗斯方块
- 顺便学习前端技能
### 知识准备
> 一看别人的资料的时候：那么多，难以理解的样子。自己开始写的话也是一步步不知不觉出来了一堆。

学习资源：[React 技术栈系列教程](http://www.ruanyifeng.com/blog/2016/09/react-technology-stack.html)
- 前端工具
    - [学习笔记](https://github.com/dingqing/tetris/blob/master/learning/front-tools-learning.md)
- ES6
    - [学习笔记](https://github.com/dingqing/tetris/blob/master/learning/es6-learning.md)
- React
    - [学习笔记](https://github.com/dingqing/tetris/blob/master/learning/react-learning.md)
- Redux
    - [学习笔记](https://github.com/dingqing/tetris/blob/master/learning/redux-learning.md)

## 2.系统介绍
### /src目录一览
```
src
    ├─ actions          [被/control/todo里面的文件调用]
    ├─ componets        [组件]
        ├─ ...          [图案和标题、屏幕、得分、“下一个”、音效、暂停...]
    ├─ containers       [容器]
    ├─ controls         []
    ├─ reducers         [计算新的state]
    ├─ resource         []
    ├─ store            []
    ├─ unit             []
index.js                [入口文件]
webpack.config.js       [webpack配置文件]
w.config.js
```

## 3.开发
### 安装
    ```
    npm install
    ```
### 运行
    ```
    npm start
    ```
浏览自动打开 [http://127.0.0.1:8080/](http://127.0.0.1:8080/)
### 多语言
在 [i18n.json](https://github.com/dignqing/tetris/blob/master/i18n.json) 配置多语言环境，使用"lan"参数匹配语言如：`https://dignqing.github.io/tetris/?lan=en`
### 打包编译
```
npm run build
```

在build文件夹下生成结果。

## 总结
- ……
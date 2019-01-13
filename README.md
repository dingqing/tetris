# tetris-react
使用React、Redux实现俄罗斯方块小游戏练习

## 1.准备
### 目标
- 实现俄罗斯方块
- 顺便学习前端技能
### 知识准备
> 看别人的资料的时候：那么多，难以理解的样子。自己开始写的话也是一步步不知不觉出来了一堆。

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
### /src目录结构
```
src
    ├─ actions          [被/control/todo里面的文件调用]
    ├─ componets        [组件]（以下按开发顺序罗列）
        ├─ decorate         [屏幕两边的图案、上方标题]
        ├─ matrix           [游戏屏幕]
        ├─ logo             [游戏开始时的屏幕上的恐龙图案]
        ├─ point            [得分、最高分、上轮得分]
        ├─ number           [起始行/消除行，级别，时间]
        ├─ next             [下一个]
        ├─ music            [音效]
        ├─ pause            [暂停]
        ├─ keyboard         [掉落、上下左右等共8个按钮]
        ├─ guide            [二维码、github按钮、键盘提示]
    ├─ containers       [容器]
    ├─ control          []
    ├─ reducers         [计算新的state]
    ├─ resource         []
    ├─ store            []
    ├─ unit             []
    └─index.js          [入口文件]
.babelrc                [babel配置文件]
.package.json           [包配置文件]
webpack.config.js       [webpack配置文件]
w.config.js             [被引入的webpack配置]
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
打开 [http://127.0.0.1:8080/](http://127.0.0.1:8080/)

## 4.总结
- 打通前端（部分）技能
- 顺便回顾后端框架设计，项目执行流程
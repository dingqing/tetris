# Redux学习笔记

参考：[Redux 入门教程](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)

## 1.基本用法
`看不懂的新概念或者其他东西可以先放脑海里，到后面理解了的时候再回来消化掉。`
- 何时需要Redux
    - 简单应用不需要
- 设计思想
    - web应用是一个状态机，视图与状态对应
    - 所有状态，保存在一个对象里面
- 基本概念（`基本上都顾名思义就好了`）
    - Store：保存数据的地方，整个应用只能有一个Store
    - State：
    - Action *object*：View --Action--> State
    - Action Creator
    - Store.dispatch()：View发出Action的唯一方法
    - Reducer *function*：Store --State--> View
    - Store.subscribe()
- 工作流程
- 总结：用户发出Action，Reducer函数计算新的State，View重新渲染。

## 2.中间件和异步操作

## 3.React-Redux用法
- UI组件
- 容器组件
- connect()
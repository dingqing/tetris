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
    ```
    import {createStore} from 'redux';
    
    // Store：保存数据的地方，整个应用只能有一个Store
    // 创建的时候传入Reducer，第二个参数是状态初始值
    const store = createStore(reducer, window.STATE_FROM_SERVER);
    
    // 监听State变化
    store.subscribe(listener);
    // 解除监听
    let unsubscribe = store.subscribe(() =>
        console.log(store.getState())
    );
    unsubscribe();
        
    // 一个State对应一个View
    const state = store.getState();
    
    const ADD_TODO = '添加 TODO';
    // Action Creator：生成Action
    function addTodo(text){
        return {
            type: ADD_TODO,
            text
        }
    }
    // store.dispatch：View发出Action的唯一方法
    store.dispatch(addTodo('Learn Redux'));
    
    // reducer：计算新的State
    // 数组进行reduce计算将reducer作为参数，所以叫做reducer
    // reducer拆分
    import {combineReducers} from 'redux'
    import * as reducers from './reducers'
    const reducer = combineReducers(reducers)
    ```
- 工作流程
    - 用户发出Action
    - Store调用Reducer，并传入当前State和收到的Action，Reducer会返回新的State。
    - State一旦有变化，Store会调用监听函数。
    - listener可以通过store.getState()得到当前状态。如果是React，这时可以触发重新渲染View。

## 2.中间件和异步操作
- 目的：异步操作结束后执行Reducer

## 3.React-Redux用法
- UI组件
- 容器组件
- connect()
    - 将两种组件连起来
    ```
    import {connect} from 'react-redux'
    const VisibleTodoList = connect(
        mapStateToProps,
        mapDispatchToProps
    )(TodoList)
    ```
- mapStateToProps()
- mapDispatchToProps()
- <Provider>组件
    - 将所有组件包起来，这样就方便拿到state对象
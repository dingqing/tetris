# React学习笔记

参考：[React 入门实例教程](http://www.ruanyifeng.com/blog/2015/03/react.html)

- 安装
    - 引入三个库
    - 或者
        ```
        npm install -g create-react-app
        ```
- HTML模板
    - `type="text/babel"`支持JSX语法
    - babel将js文件进行语法转换
- ReactDOM.render()
    - 将模板转换为HTML，并插入指定DOM节点
- JSX语法
    - HTML与JavaScript混写。遇到<开头则解析HTML，遇到{开头则解析JavaScript
- 组件（component）
    ```
    var SomeComponent = React.createClass({
        // 验证属性
        PropTypes:{
        },
        // 状态
        getInitialState: function(){
            return {liked: false};
        },
        // ajax
        componentDidMount: function(){
            $.get(this.props.source, function(result){
                var lastGist = result[0];
                if (this.isMounted()){
                    this.setState({
                        username: lastGist.owner.login,
                        lastGistUrl: lastGist.html_url
                    });
                }
            }.bind(this));
        },
        // ajax with promise
        componentDidMount: function(){
            this.props.promise.then(
                value => this.setState({loading: false, data: value}),
                error => this.setState({loading: false, error: error})
            );
        },
        handleClick: function(){
            this.setState({liked: !this.state.liked});
            this.refs.myTextInput.focus(); //获取真实DOM节点
        },
        render: function(){
            // ajax with promise
            if (this.state.loading) {
                return <span>Loading...</span>;
            }else{
                var text = this.state.liked ? 'like' : 'haven\'t liked;
                return
                    <div onclick={this.handleClick}>
                    <input type="text" ref="myTextInput"/>
                    // 子节点
                    {
                        React.Children.map(this.props.children, function(child){
                            return <li>{child}</li>;
                        })
                    }
                    </div>
                ;
            }
        }
    });
    
    ReactDOM.render(
        <SomeComponent source="http://xxx.com"/>,
        document.getElementById('example')
    );
    // ajax with promise
    ReactDOM.render(
        <SomeComponent promise={$.getJSON('http://xxx.com')}/>,
        document.getElementById('example')
    );
    ```
    - this.state
        - state表示随用户交互会变化的属性，props不会变
    - 状态：
        - mounting：已插入真实DOM，
        - updating：正在被重新渲染，
        - unmounting：已移出真实DOM
    - 处理函数：
        - 针对三种状态，每个状态都有will和did函数，共计五种。如componentWillMount()
        - componentWillReceiveProps(object nextProps)：已加载组件收到新的参数时调用，
        - shouldComponentUpdate(object nextProps, object nextState)：组件判断是否重新渲染时调用
- 表单
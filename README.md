# Kickoffredux redux及webapck入门
### redux部分代码参考自 redux官方例子 [todomvc](https://github.com/reactjs/redux/tree/master/examples/todomvc)
### webapck部分运用了各种loader和plugin来了解webpack的配置

### 总结
1. 学习了基于npm的包管理和开发环境搭建及npm scripts的使用
2. 学习了webpack的使用及插件配置
3. 通过阅读部分redux的源码及官方例子,了解了单向数据流的最佳实践
4. ES6的语法及.babelrc的配置

    ```javascript
    {
      "presets": ["react", "es2015"],
      "env": {
        "development": {
          "presets": ["react-hmre"]
        }
      }
    }
    ```

### 环境搭建
1. 切换到cnpm镜像: 
   在~/.zshrc或~/.bashrc加入如下配置

    ```javascript
    #alias for cnpm
    alias cnpm="npm --registry=https://registry.npm.taobao.org \
    --cache=$HOME/.npm/.cache/cnpm \
    --disturl=https://npm.taobao.org/dist \
    --userconfig=$HOME/.cnpmrc"
    ```

2. cnpm install -g webpack
  
   cnpm install

### 命令
* npm start 本地调试
* npm run build 编译静态文件(打md5 hash值)

### sass说明
* index.scss index页面css文件
* common.scss 通用css模块
* mixin 公用mixin
* varibles 全局变量

### js说明
运用redux官方推荐的react分层结构
* `actions` action类型的定义
* `components` 展现层组件,不关心外部数据,纯展现层
* `constants` 常量定义,如action名称等
* `containers` 外层组件,和redux进行绑定(state及action的绑定),对数据敏感
* `reducers` action触发后对state分别处理,返回新的state,最后把所有reducer进行组合
* `store` redux中唯一的store,把reducer与store进行绑定
* `index.js` 将store与外层组件进行绑定

### mock说明[TODO]

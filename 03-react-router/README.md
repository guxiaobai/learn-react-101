## 03 - React Router

### 01 - 安装

```bash
npm install react-router-dom --save
```

### 02 - API

* `<BrowserRouter>`
* `<HashRouter>`
* `<Route>`: 路由配置的核心标记, 路径匹配时显示对应组件
* `<Switch>`: 只显示第一个匹配的路由
* `<Link>`: 普通链接，不会触发浏览器刷新
* `<NavLink>`: 类似Link但是会添加当前选中状态
* `<Prompt>`: 满足条件时提示用户是否离开当前页面
* `<Redirect>`: 重定向当前页面

**01 - `Route` 参数**

* `exact`: 精确匹配
* `strict`: 严格模式



### 参考资料

* [React Router](https://reacttraining.com/react-router/)
* [history](https://github.com/ReactTraining/history)
* [轻松学 React-Router 4](https://github.com/guxiaobai/learn-course-100/tree/main/com.qiuzhi99/019-react-router-4)
* [React Router 使用教程](http://www.ruanyifeng.com/blog/2016/05/react_router.html)


**Web API**

* [Location](https://developer.mozilla.org/zh-CN/docs/Web/API/Location)
* [History API](https://developer.mozilla.org/zh-CN/docs/Web/API/History_API)

**源码分析**

* [router.js](https://github.com/ant-design/ant-design-pro/blob/1.4.4/src/router.js)
* [UserLayout.js](https://github.com/ant-design/ant-design-pro/blob/1.4.4/src/layouts/UserLayout.js) / [BasicLayout.js](https://github.com/ant-design/ant-design-pro/blob/1.4.4/src/layouts/BasicLayout.js)
* [AuthorizedRoute.js](https://github.com/ant-design/ant-design-pro/blob/1.4.4/src/components/Authorized/AuthorizedRoute.js)


全局JavaScript逻辑和应用生命周期管理。
```javascript
// app.js
export default {
  onCreate() {
    console.info('Application onCreate');
  },
  onDestroy() {
    console.info('Application onDestroy');
  },
}
```

每一个应用都有一个`app.js`文件，其中有两个`onCreate`和`onDestroy`钩子函数，用于在系统加载应用时赋予用户执行一些自定义操作的能力。

> 后面在*容器组件*和*通用组件*章节中，每一个组件的案例都默认有一个`app.js`文件，为了文档描述的简介性，后面单独介绍每个组件时，将不再说明`app.js`文件。
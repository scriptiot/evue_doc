应用退出除使用物理按键退出应用外，还可以通过组件的事件触发。本章节以右滑退出为例，讲述应用退出的操作。

应用退出，必须调用app模块的terminate方法。当页面右滑的时候会触发onswipe事件，在事件中执行app.terminate即可实现应用退出。由于swipe是有方向属性的，在事件函数处理中要注意判断方向，否则任意方向的滑动都会触发退出应用操作，代码示例如下：

```html
<!-- index.hml：绑定div的swipe事件 -->
<div class="container" onswipe="touchMove">
    <text id="title">
        Hello {{title}}
    </text>
    <input type="button" value="View Detail"
           style="width: 300px; height: 80px;" onclick="clickAction">
    </input>
</div>
```

```javascript
// index.js:
import router from '@system.router'
// 导入app模块
import app from '@system.app'
 
export default {
    data: {
        title: 'World'
    },
    clickAction(){
          router.replace({
              uri: 'pages/detail/detail'
          });
    },
    touchMove(e){  // swipe处理事件
        if(e.direction == "right")  // 右滑退出
        {
             this.appExit();
        }
    },
    appExit(){  // 退出app
        app.terminate();
    }
}
```


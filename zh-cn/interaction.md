每个组件都有一些通用事件和特有事件，开发者可在这些事件中实现应用的功能和逻辑。组件中添加事件的格式如下：

```html
<element onevent="eventAction">
```

常见的组件事件如下表所示：

| 事件      | 描述                                                         |
| --------- | ------------------------------------------------------------ |
| click     | 组件被点击时触发，使用方法参见下面示例。                     |
| longpress | 组件被长按时触发，使用方法与click相同。                      |
| swipe     | 组件上快速滑动时触发，使用方法参见[应用退出](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-exiting-0000001056363133#ZH-CN_TOPIC_0000001056363133)章节。 |

以\<input\>组件的onclick事件为例，介绍事件的使用方法。首先，在index.hml文件中添加一个\<input\>组件，添加后的代码示例如下：

```html
<div class="container">
    <text  id="title">
        Hello {{title}}
    </text>
    <input type="button" value="View Detail" style="width: 300px; height: 50px;" onclick="clickAction"></input>
</div>
```

在如上代码中，页面里添加了一个\<input\>组件，onclick事件及其处理函数也添加到组件中。clickAction是一个Javascript函数，它的实现在pages/index/index.js文件中，代码示例如下：

```javascript
import router from '@system.router'
 
export default {
    data: {
        title: 'World'
    },
    clickAction(){
        router.replace({
            uri: 'pages/detail/detail'
        });
    }
}
```

clickAction实现的功能是点击按钮即可跳转到另外一个页面，详见[页面路由](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-routes-0000001056203160#ZH-CN_TOPIC_0000001056203160)。
很多应用都不仅仅由一个页面组成，如何将这些页面串联起来，让他们根据开发者的需要来实现跳转，这就需要页面路由来实现。在分布式应用中，页面路由router根据uri的地址来找到目标页面，实现跳转。下面以两个简单页面之间的跳转为例说明页面跳转的操作，具体实现步骤如下：

1. 在“pages”目录右键，选择“New Page”，创建一个detail页面。如果使用其他方式添加页面，则在添加页面后需要修改配置文件config.json中的pages标签。
2. 在index页面通过点击button按钮调用router.replace()函数跳转到详情页。
3. 在detail页面通过点击button按钮调用router.replace()回到首页。

创建detail页面，页面中包含一个\<text\>组件和\<button\>组件，\<text\>组件用来指明当前页面，\<button\>组件用来实现两个页面之间的相互跳转。pages/detail/detail.hml文件代码示例如下，detail.css文件内容和绘制样式章节中的[index.css](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-style-0000001055883166#ZH-CN_TOPIC_0000001055883166__zh-cn_topic_0000001050020757_section192248504211)一致：



```html
<!-- detail.hml -->
<div class="container">
    <text id="title">
        Detail Page
    </text>
    <input type="button" value="Back" style="width: 300px; height: 80px;" onclick="clickAction"></input>
</div>
```



在页面的js文件中实现跳转逻辑，调用router.replace()方法跳转到uri指定的页面，代码示例如下：

```javascript
// index.js:
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

```javascript
// detail.js:
import router from '@system.router'
 
export default {
    clickAction(){
        router.replace({
            uri: 'pages/index/index'
        });
    }
}
```

界面开发完成后，请参考[使用预览器查看应用效果](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/previewer-0000001054328973)：

![](https://communityfile-drcn.op.hicloud.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20200922162411.35858181549913493406071108190330:50510922084432:2800:46481456CB4091ECE503D5CBF12A9631EB928C3DD2D5575D6750C8B4C51C3374.png?needInitFileName=true?needInitFileName=true)
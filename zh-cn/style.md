> 行内样式  
> 选择器样式  
> 动态绑定样式

在[构建布局](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-layout-0000001056483134#ZH-CN_TOPIC_0000001056483134)中，已经可以运行应用并显示结果。组件标签中类似`style="width:454px;height:454px;"`的语句即为样式设置语句，通过样式可以设置组件的显示大小、背景颜色、对齐方式等属性。本章节以<div>和<text>组件为例来介绍如何设置样式，样式主要有三种设置方式：行内样式、选择器样式和动态绑定样式。三种方式设置的样式效果一致，只是写法不同。

# 行内样式

行内样式是将样式内容直接放到组件的style属性中，多个样式值则是通过分号间隔。在示例中，我们可以看到通过行内样式对div和text组件设置了高度和宽度属性。

```html
<div style="width: 454px; height: 454px;">
<text style="width: 200px; height: 100px;">
```

我们可以通过设置组件的部分样式，使得text组件中的内容显示在屏幕的最中间。

```html
<!-- 设置div中的子组件为弹性布局，并且居中显示；保证text组件显示在屏幕中间。-->
<div style="width: 454px; height: 454px; display: flex; justify-content: center; align-items: center;"> 
<!-- 设置text组件中文字居中显示；保证Hello World显示在屏幕最中间。-->
<text style="width: 200px; height: 100px; font-size: 30px; text-align: center;"> 
```

# 选择器样式

使用行内样式存在以下缺点：

- 针对每个组件都要设置样式。
- 如果多个组件需要设置相同的样式，则每个组件都写同样的样式，导致代码冗余；而且修改样式时，需要修改所有代码，工作量大。

针对以上问题，我们可以采用选择器样式，将所有的样式代码写到`pages/index/index.css`文件中，然后通过class、id等方式和组件关联起来。以上节中的代码为例，修改后的代码如下：

```css
/* index.css */
/* --类选择器，所有组件中class="container" 的组件都会使用该样式。*/
.container { 
    flex-direction: column;
    display: flex;
    justify-content: center;
    align-items: center;
    left: 0px;
    top: 0px;
    width: 454px;
    height: 454px;
}
/* ID选择器，id为title的组件使用的样式 */
#title { 
    font-size: 30px;
    text-align: center;
    width: 400px;
    height: 100px;
    /* 设置文字颜色为红色 */
    color: #ff0000; 
}
```

```html
<!-- index.hml -->
<!-- 关联index.css中的.container样式代码块 -->
<div class="container"> 
    <!-- 关联index.css中的#title样式代码块 -->
    <text id="title"> 
        Hello World
    </text>
</div>
```

# 动态绑定样式

在[行内样式](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-style-0000001055883166#ZH-CN_TOPIC_0000001055883166__zh-cn_topic_0000001050020757_section8498147174113)和[选择器样式](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-style-0000001055883166#ZH-CN_TOPIC_0000001055883166__zh-cn_topic_0000001050020757_section192248504211)中，样式设置方式是静态的，即代码开发中设置的样式在程序运行的时候不能更改，这种方式限制了程序的显示效果。如果要在程序运行过程中动态地改变样式，就需要用到动态绑定样式。所谓动态绑定就是值和变量动态关联，随着值的变更而显示不同的效果。动态绑定的使用方式为{{变量名}}，其中变量名是js文件中data对象的属性值。目前动态绑定样式只支持绑定行内样式。

在下面代码中，text的字体大小和data中的font-size属性绑定，显示的文字和data中的title属性绑定：

```html
<!-- index.hml -->
<div class="container">
    <text id="title" style="font-size: {{fontSize}};">
        Hello {{title}}
    </text>
    <input type="button" value="View Detail" style="width: 300px; height: 80px;" onclick="clickAction"></input>
</div>
```

```javascript
// index.js:
import router from '@system.router'
 
export default  {
    data: {
        title: 'World',
        fontSize: '30px'
    },
    clickAction(){
        router.replace({
            uri: 'pages/detail/detail'
        });
    }
}
```

界面开发完成后，请参考[使用预览器查看应用效果](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/previewer-0000001054328973)：

![](https://communityfile-drcn.op.hicloud.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20200922162411.12635253061720679126918538211765:50510922084431:2800:9BEAD3649B026B998F658E990B4E338DE8B4BE8239E3316AD74BFA1D802B455A.png?needInitFileName=true?needInitFileName=true)
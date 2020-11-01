> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO 

\<list\>的子组件，用来展示列表具体item。

# 子组件
支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

# 样式
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*弹性布局<br/>*none*：不渲染此元素 |
| width | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | \<length\> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

> 请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-list-item`

**index.hml**

```html
<list class="todo-wraper">
    <list-item class="todo-item">
        <text class="todo-title">000</text>
        <text class="todo-title">111</text>
    </list-item>
    <list-item class="todo-item">
        <text class="todo-title">222</text>
        <text class="todo-title">333</text>
    </list-item>
    <list-item class="todo-item">
        <text class="todo-title">444</text>
        <text class="todo-title">555</text>
    </list-item>
</list>
```

**index.css**

```css
/* index.css */
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    left: 0px;
    top: 0px;
    width: 454px;
    height: 454px;
}
.todo-wraper {
    width: 454px;
    height: 300px;
    top: 50px;
}
.todo-item {
    width: 454px;
    height: 80px;
    flex-direction: column;
    border-width: 1px;
    border-style: solid;
    border-color: red;
    background-color: black;
}
.todo-title {
    width: 454px;
    height: 40px;
    color: white;
    padding: 4px;
    text-align: center;
    border-radius: 10px;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'HelloWorld'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-list-item/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evue.exe ../../test/list-item/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031205804.png)
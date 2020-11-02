> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

跑马灯组件，用于展示一段单行滚动的文字。

# 子组件
不支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| scrollamount  | number | 6  | 否 | 跑马灯每次滚动时移动的最大长度。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

# 样式
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| color | \<color\> | #ffffff | 否 | 设置跑马灯中文字的文本颜色。 |
| font-size | \<length\> | 30          | 否 | 设置跑马灯中文字的文本尺寸。目前仅支持30px和38px 两个字体大小。 |
| font-family | string | HYQiHei-65S | 否 | 字体。目前仅支持HYQiHei-65S 字体。 |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*弹性布局<br/>*none*：不渲染此元素 |
| width | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | \<length\> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |
| [left\|top] | \<length\> | - | 否 | left|

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-marquee`

**index.hml**

```html
<div class="container">
    <list class="list-container">
        <list-item class="listitem">
            <marquee scrollamount="3" style="width: 120px;
                                             height: 50px;
                                             margin-top: 10px;
                                             color: red;
                                             border-width: 1px;
                                             border-color: red;
                                             border-radius: 5px;
                                             font-size: 38px;
                                             font-family: HYQiHei-65S;">
                show-abcedfghijklmn
            </marquee>
        </list-item>
        <list-item class="listitem">
            <marquee scrollamount="30" style="border-width: 1px;
                                              border-color: red;
                                              padding: 5px;
                                              margin-top: 10px;
                                              color: red;
                                              font-size: 38px;
                                              font-family: HYQiHei-65S;">
                show-abcedfghijklmn
            </marquee>
        </list-item>
        <list-item class="listitem">
            <marquee scrollamount="300" style="border-width: 1px;
                                               border-color: red;
                                               padding: 5px;
                                               width: 100px;
                                               height: 50px;
                                               margin-top: 10px;
                                               color: red;
                                               font-size: 38px;
                                               font-family: HYQiHei-65S;">
                show-abcedfghijklmn
            </marquee>
        </list-item>
    </list>
</div>
```

**index.css**

```css
.container {
    display: flex;
    width: 454px;
    height: 454px;
    border-width: 2px;
    border-radius: 2px;
    margin: 0px;
    padding: 0px;
    background-color: green;
}

.list-container {
    width: 300px;
    height: 350px;
    left: 75px;
    top: 55px;
    background-color: yellow;
}

.listitem {
    flex-direction: column;
    align-items: center;
    width: 330px;
    height: 100px;
    margin: 0px;
    padding: 5px;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'show-marquee'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
cd evuesimulator-linux-v2.0
./evuesimulator test/test-marquee/
```

**Windows**

```powershell
cd evuesimulator-windows-v2.0
<<<<<<< Updated upstream
evuesimulator.exe test/test-marquee/
=======
evuesimulator.exe ../../test/test-marquee/
>>>>>>> Stashed changes
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/Peek-2020-10-31-22-23.gif)
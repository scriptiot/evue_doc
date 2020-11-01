> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

交互式组件，包括单选框，多选框，按钮。

# 子组件
不支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| type | string | button | 否 | input组件类型，可选值为button，checkbox，radio。<br/>button，checkbox，radio不支持动态修改。可选值定义如下：<br/>**button：**定义可点击的按钮；<br/>**checkbox：**定义多选框；<br/>**radio：**定义单选按钮，允许在多个拥有相同name值的选项中选中其中一个； |
| checked | boolean | false | 否 | 当前组件是否选中。 |
| name | string | - | 否 | input组件的名称。 |
| value | string | - | 否 | input组件的value值，当类型为radio时必填且相同name值的选项该值唯一。 |

# 事件

* 当input类型为checkbox、radio时，支持如下事件：

|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |
| change | { checked:true\|false} | checkbox多选框或radio单选框的checked状态发生变化时触发该事件。 |

* 当input类型为button时，支持如下事件：

| 名称      | 参数       | 描述                   |
| --------- | ---------- | ---------------------- |
| click     | -          | 点击动作触发该事件。   |
| longpress | -          | 长按动作触发该事件。   |
| swipe     | SwipeEvent | 组件上快速滑动后触发。 |

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

**注意事项：**

* input组件目前不支持radio

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-input`

**index.hml**

```html
<div class="container">
    <list id="list-container">
        <list-item id="listitem">
            <input type="button" style="left: 85px;
                                        width: 130px;
                                        height: 40px;
                                        border-width: 1px;
                                        border-color: red;"
             value="button 1" onclick="onclick" onlongpress="onlongpress">
            </input>
        </list-item>
        <list-item id="listitem">
            <input type="radio" style="left: 85px;
                                       width: 300px;
                                       height: 60px;
                                       border-width: 1px;
                                       border-color: red;
                                       border-radius: 10px;"
                   checked="true" value="radio 2" onclick="backMain">
            </input>
        </list-item>
        <list-item id="listitem">
            <input type="checkbox" style="left: 85px;
                                          width: 130px;
                                          height: 40px;
                                          border-width: 1px;
                                          border-color: red;"
                   checked="true" value="checkbox 3" onclick="backMain">
            </input>
        </list-item>
        <list-item id="listitem">
            <input type="checkbox" style="left: 85px;
                                          width: 130px;
                                          height: 40px;
                                          border-width: 1px;
                                          border-color: red;
                                          display: none;"
                   checked="true" value="checkbox 3" onclick="backMain">
            </input>
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

#list-container {
    width: 300px;
    height: 300px;
    left: 70px;
    top: 70px;
    background-color: yellow;
}

#listitem {
    flex-direction: column;
    align-items: center;
    width: 300px;
    height: 60px;
    margin: 0px;
    padding: 10px;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'World'
    },
    onclick: function() {
        print("=====onclick=====");
    },
    onlongpress: function() {
        print("=====longpress=====");
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-input/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evue.exe ../../test/test-input/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031224002.jpg)
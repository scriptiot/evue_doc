> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO  

滑动容器，提供切换子组件显示的能力。

# 子组件
支持除\<list\>之外的子组件。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| index  | number | 0 | 否 | 当前在容器中显示的子组件的索引值。 |
| loop  | boolean | true | 否 | 是否开启循环轮播。<br/>不支持动态修改。<br/> **说明：**loop参数生效需要满足以下两个条件：<br/>1. 除第一个子组件之外，剩余子组件的总长度大于等于swiper的长度；<br/>2. 除最后一个子组件之外，剩余子组件的总长度大于等于swiper的长度。 |
| duration | number | - | 否 | 子组件切换的动画时长。 |
| vertical | boolean | false | 否 | 是否为纵向滑动，纵向滑动时采用纵向的指示器。不支持动态修改。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| change  | { index: currentIndex } | 当前显示的组件索引变化时触发该事件。 |
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
| margin | \<length\> | 0 | 否 | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。是<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | \<length\> | 0 | 否 | 设置左、上、右、下外边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |
| [left\|top] | \<length\> | - | 否 | left|

> 说明：由于绝对定位不支持设置百分比，所以也不支持stack组件的子组件上设置margin。

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

> 请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/swiper`

**index.hml**

```html
<swiper class="container" index=0 vertical=false uration="500" onchange="swiperChange">
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width: 0px;">
        <text style="left: 140px;
                     top: 70px;
                     width: 180px;
                     height: 60px;
                     text-align: center;
                     font-size: 20px;
                     font-family: simsun;"> {{title}} </text>
        <image id="logo-animation" src="./common/images/logo.bin"
               style="left: 80px;top: 120px;text-align: center;"></image>
    </div>
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width: 0px;">
        <text style="left: 180px;
                     top: 70px;
                     width: 180px;
                     height: 100px;
                     text-align: center;
                     font-size: 30px;
                     font-family: simsun;"> 图标 </text>
        <div style="flex-direction: row;
                    align-items: center;
                    border-width: 0px;
                    left: 90px;
                    top: 120px;
                    width: 300px;
                    height: 60px;
                    fade-in-time: 100;
                    fade-in-delay: 100">
            <image src="./common/images/light/appbar.add.bin"
                   style="fade-in-time: 200;fade-in-delay: 200"></image>
            <image src="./common/images/light/appbar.clear.bin"
                   style="fade-in-time: 200; fade-in-delay: 400"></image>
            <image src="./common/images/light/appbar.cd.bin" 
                   style="fade-in-time: 200; fade-in-delay: 600"></image>
        </div>
        <div style="flex-direction: row;
                    left: 90px;
                    top: 180px;
                    border-width: 0px;
                    width: 300px;
                    height: 60px;">
            <image src="./common/images/light/appbar.disk.bin"
                   style="fade-in-time: 200;fade-in-delay: 800;"></image>
            <image src="./common/images/light/appbar.app.bin"
                   style="fade-in-time: 200;fade-in-delay: 1000;"></image>
            <image src="./common/images/light/appbar.alert.bin"
                   style="fade-in-time: 200;fade-in-delay: 1200;"></image>
        </div>
        <div style="flex-direction: row;
                    left: 90px;
                    top: 240px;
                    border-width: 0px;
                    width: 300px;
                    height: 60px;">
            <image src="./common/images/light/appbar.cart.bin"
                   style="fade-in-time: 200;fade-in-delay: 1400;"></image>
            <image src="./common/images/light/appbar.clock.bin"
                   style="fade-in-time: 200;fade-in-delay: 1600;"></image>
            <image src="./common/images/light/appbar.adobe.bridge.bin"
                   style="fade-in-time: 200;fade-in-delay: 1800;"></image>
        </div>
        <div style="flex-direction: row;
                    left: 90px;
                    top: 300px;
                    border-width: 0px;
                    width: 300px;
                    height: 60px;">
            <image src="./common/images/light/appbar.arrow.expand.bin"
                   style="fade-in-time: 200;fade-in-delay: 2000;"></image>
            <image src="./common/images/light/appbar.delete.bin"
                   style="fade-in-time: 200;fade-in-delay: 2200;"></image>
            <image src="./common/images/light/appbar.browser.chrome.bin"
                   style="fade-in-time: 200;fade-in-delay: 2400;"></image>
        </div>
    </div>
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width:0px;">
        <text style="left: 110px;
                     top: 70px;
                     width: 200px;
                     height: 60px;
                     text-align: center;
                     font-size: 30px;
                     font-family: simsun;"> 列表和跑马灯 </text>
        <list id="list_container">
            <list-item id="listitem2">
                <marquee scrollamount="3" style="width: 100px;
                                                 height: 100px;
                                                 text-align: center;
                                                 margin-top: 10px;
                                                 color: red;
                                                 font-size: 30px;
                                                 font-family: simsun; ">
                    1234567890
                </marquee>
            </list-item>
            <list-item id="listitem2">
                <marquee scrollamount="30" style="width: 100px;
                                                  height: 100px;
                                                  text-align: center;
                                                  margin-top: 10px;
                                                  color: red;
                                                  font-size: 30px;
                                                  font-family: simsun;">
                    abcedfghijklmnopqrstuvwxys
                </marquee>
            </list-item>
            <list-item id="listitem2">
                <marquee scrollamount="300" style="width: 100px;
                                                   height: 100px;
                                                   text-align: center;
                                                   margin-top: 10px;
                                                   color: red;
                                                   font-size: 30px;
                                                   font-family: simsun;">
                    八佰和金刚川
                </marquee>
            </list-item>
        </list>
    </div>
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width: 0px;">
        <text style="left: 110px;
                     top: 70px;
                     width: 200px;
                     height: 60px;
                     text-align: center;
                     font-size: 30px;
                     font-family: simsun;"> 按钮 </text>
        <list id="list_container">
            <list-item id="listitem1">
                <input type="button" value="slider" onclick="onPage1" onlongpress="onlongpress"
                       style="left: 85px;width: 130px;height: 40px;"></input>
            </list-item>
            <list-item id="listitem1">
                <input type="button" value="switch" onclick="onPage2" onlongpress="onlongpress"
                       style="left: 85px;width: 130px;height: 40px;"></input>
            </list-item>
            <list-item id="listitem1">
                <input type="button" value="progress" onclick="onPage3" onlongpress="onlongpress"
                       style="left: 85px;width: 130px;height: 40px;"></input>
            </list-item>
        </list>
    </div>
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width: 0px;">
        <text style="left: 110px;
                     top: 70px;
                     width: 200px;
                     height: 60px;
                     text-align: center;
                     font-size: 30px;
                     font-family: simsun;"> 图表 </text>
        <chart style="left:72px; top:130px; width:300px; height: 250px"></chart>
    </div>
    <div style="background-color: white;
                text-align: center;
                width: 454px;
                height: 454px;
                border-width: 0px;">
        <text style="left: 100px;
                     top: 70px;
                     width: 200px;
                     height: 60px;
                     text-align: center;
                     font-size: 30px;
                     font-family:simsun;"> 滑动选择器 </text>
        <picker-view type="text" selected="0" range="['a','b','c','d']"
                     style="left: 190px;
                            top: 120px;
                            width: 280px;
                            height: 50px;
                            margin-top: 10px;
                            margin-left: 85px;"></picker-view>
        <picker-view type="text" selected="1" range="['a','b','c','d']"
                     style="left: 190px;
                            top: 180px;
                            width: 280px;
                            height: 50px;
                            margin-top: 10px;
                            margin-left: 85px;"></picker-view>
        <picker-view type="text" selected="2" range="['a','b','c','d']"
                     style="left: 190px;
                            top: 240px;
                            width: 280px;
                            height: 50px;
                            margin-top: 10px;
                            margin-left: 85px;"></picker-view>
        <picker-view type="text" selected="3" range="['a','b','c','d']"
                     style="left: 190px;
                            top: 300px;
                            width: 280px;
                            height: 50px;
                            margin-top: 10px;
                            margin-left: 85px;"></picker-view>
        <picker-view type="text" selected="4" range="['a','b','c','d']"
                     style="left: 190px;
                            top: 360px;
                            width: 280px;
                            height: 50px;
                            margin-top: 10px;
                            margin-left: 85px;"></picker-view>
    </div>
</swiper>
```

**index.css**

```css
#logo-animation {
    animation-name: image-animation;
    animation-delay: 0;
    animation-duration: 200;
    animation-timing-function: linear;
    animation-fill-mode: none;
    animation-iteration-count: 1;
}

text {
    animation-name: text;
    animation-delay: 200;
    animation-duration: 200;
    animation-timing-function: linear;
    animation-fill-mode: none;
    animation-iteration-count: 1;
    animation-property: x;
    animation-property-from: 0;
    animation-property-to: 140;
}

#id_container {
    display: flex;
    width: 454px;
    height: 454px;
    border-width: 2px;
    border-radius: 2px;
    margin: 0px;
    padding: 0px;
}

#list_container {
    width: 300px;
    height: 250px;
    left: 70px;
    top: 140px;
}

#separator {
    width: 454px;
    height: 4px;
    background-color: white;
}

.title {
    display: flex;
    font-size: 30px;
    text-align: center;
    width: 100px;
    height: 60px;
    left: 50px;
    top: 10px;
}

#id_title {
    font-size: 30px;
    text-align: center;
    width: 200px;
    height: 100px;
}

#listitem1 {
    flex-direction: column;
    align-items: center;
    width: 300px;
    height: 60px;
    margin: 0px;
    padding: 10px;
}

#listitem2 {
    flex-direction: column;
    align-items: center;
    width: 330px;
    height: 50px;
    margin: 0px;
    padding: 5px;
}

#div_animation {
    background-color:white;
    text-align:center;
    width:454px; 
    height:454px; 
    border-width:0px;
}

#animation1 {
    left: 80px;
    top: 145px;
    width: 300px; 
    height: 200px;
    border-width: 0px;
    background-color: #123456;
    animation-name: color-animation;
    animation-delay: 0;
    animation-duration: 1000;
    animation-timing-function: ease-in;
    animation-fill-mode: none;
    animation-iteration-count: 1;
}

#image_angle_animation{
    left: 100px;
    top: 150px;
    background-color: #123456;
    animation-name: angle-animation;
    animation-delay: 0;
    animation-duration: 1000;
    animation-timing-function: linear;
    animation-fill-mode: none;
    animation-iteration-count: 200;
}

@keyframes image-animation
{
    from {
        x: 0;
    }
    to {
        x: 80;
    }
}

@keyframes color-animation
{
    from {
        background-color: red;
    }
    to {
        background-color: #123456;
    }
}

@keyframes angle-animation
{
    from {
        angle: 0;
    }
    to {
        angle: 3600;
    }
}
```

**index.js**

```javascript
router = require("@system.router")

export default {
    data: {
        title: 'show-abcedfghijklmn',
        pageIndex: 0,
        address: {
            city: 'beijing'
        }
    },

    onInit: function() {
        print("==========onInit==========")
    },

    onReady: function() {
        // this.data.pageIndex = 20;
        // this.data.title = '30000000';
        print("==========onReady==========")
        print(this.data)
        print(this.data.pageIndex)
    },

    onShow: function() {
        print("==========onShow==========")
    },

    onHide: function() {
        print("==========onHide==========")
    },

    onDestroy: function() {
        print("==========onDestroy==========")
    },

    onPage1: function(obj, x, y) {
        print("==========onclick==========")
        print(x);
        print(x);
        router.replace({
            uri: "pages/slider/index"
        })
    },

    onPage2: function(obj, x, y) {
        print("==========onclick==========")
        print(x);
        print(x);
        router.replace({
            uri: "pages/switch/index"
        })
    },

    onPage3: function(obj, x, y) {
        print("==========onclick==========")
        print(x);
        print(x);
        router.replace({
            uri: "pages/progress/index"
        })
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/swiper/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evuesimulator.exe ../../test/swiper/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/Peek-2020-10-31-22-01.gif)
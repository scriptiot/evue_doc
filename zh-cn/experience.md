> 搭建环境和创建项目  
> JS主体介绍  
> 运行应用

# 搭建环境和创建项目

1. 先从仓库克隆项目

   ```shell
   git clone https://github.com/scriptiot/evue
   ```

2. 进入仓库所在目录

   ```shell
   cd ~/evue
   ```

# JS主体介绍

LiteWearable工程目录如下图所示：

**目录结构：**

```shell
.
├── app.js
├── common
│   └── images
│       ├── appbar.camera.flash.auto.selected.bin
│       ├── appbar.chevron.right.bin
│       ├── appbar.control.fastforward.bin
│       ├── appbar.control.pause.bin
│       ├── appbar.control.rewind.bin
│       ├── appbar.fingerprint.bin
│       ├── appbar.foot.bin
│       ├── appbar.forest.bin
│       ├── appbar.new.window.bin
│       ├── appbar.repeat.bin
│       ├── appbar.return.bin
│       ├── appbar.smiley.angry.bin
│       ├── appbar.smiley.cry.bin
│       ├── appbar.smiley.frown.bin
│       ├── appbar.smiley.glasses.bin
│       ├── appbar.smiley.grin.bin
│       ├── appbar.smiley.kiki.bin
│       ├── appbar.smiley.squint.bin
│       ├── appbar.smiley.tounge.bin
│       ├── appbar.smiley.what.bin
│       ├── appbar.sound.3.bin
│       ├── distance.bin
│       ├── dribbble.bin
│       ├── evernote.bin
│       ├── flipboard.bin
│       ├── girl-128×128.bin
│       ├── girl-150×150.bin
│       ├── hotpower.bin
│       ├── instagram.bin
│       ├── microphone-64×64.bin
│       ├── microphone.bin
│       ├── phone-64×64.bin
│       ├── pingfanzhilu.bin
│       ├── pocket.bin
│       ├── rss.bin
│       ├── speed.bin
│       ├── sun.bin
│       ├── time.bin
│       ├── twitter.bin
│       ├── voice-64×64.bin
│       ├── voice.bin
│       ├── whatsapp.bin
│       ├── youtube.bin
│       └── yuyin.bin
├── pages
│   ├── call
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── chart
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── index
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── list
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── music
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── progress
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   ├── ring
│   │   ├── index.css
│   │   ├── index.hml
│   │   └── index.js
│   └── weather
│       ├── index.css
│       ├── index.hml
│       └── index.js
└── viewmodel
    ├── framework.js
    └── viewmodel.js
```

**pages/index/index.hml：**此文件定义了index页面的布局，在index页面中用到的组件，以及这些组件的层级关系。该页面是智能手表应用的菜单首页。

```html
<div class="container">
    <text style="top: 30px;
                 color: white;
                 width: 454px;
                 height: 35px;
                 text-align: center;
                 font-family: simsun;
                 font-size: 30px;">菜单</text>
    <list class="list-container">
        <list-item class="list-item" url="pages/index/index"
                   onclick="onPageRedirect">
            <image src="./common/images/dribbble.bin"
                   class="app-icon"></image>
            <text class="maintitle">首页</text>
            <!-- <text class="subtitle">100.42</text>
            <text class="maintitle-note">公里</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/call/index"
                   onclick="onPageRedirect">
            <image src="./common/images/evernote.bin"
                   class="app-icon"></image>
            <text class="maintitle">电话</text>
            <!-- <text class="subtitle">07:23:39</text> -->
            <!-- <text class="maintitle-note">公里</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/chart/index"
                   onclick="onPageRedirect">
            <image src="./common/images/flipboard.bin"
                   class="app-icon"></image>
            <text class="maintitle">健身曲线</text>
            <!-- <text class="subtitle">2755</text>
            <text class="maintitle-note">千卡</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/music/index"
                   onclick="onPageRedirect">
            <image src="./common/images/pocket.bin"
                   class="app-icon"></image>
            <text class="maintitle">音乐</text>
            <!-- <text class="subtitle">100.42</text>
            <text class="maintitle-note">公里</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/weather/index"
                   onclick="onPageRedirect">
            <image src="./common/images/rss.bin"
                   class="app-icon"></image>
            <text class="maintitle">天气</text>
            <!-- <text class="subtitle">07:23:39</text> -->
            <!-- <text class="maintitle-note">公里</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/list/index"
                   onclick="onPageRedirect">
            <image src="./common/images/twitter.bin"
                   class="app-icon"></image>
            <text class="maintitle">跑步记录</text>
            <!-- <text class="subtitle">2755</text>
            <text class="maintitle-note">千卡</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon"></image>
        </list-item>
        <list-item class="list-item" url="pages/ring/index"
                   onclick="onPageRedirect">
            <image src="./common/images/whatsapp.bin"
                   class="app-icon"></image>
            <text class="maintitle">更新升级</text>
            <!-- <text class="subtitle">2755</text>
            <text class="maintitle-note">千卡</text> -->
            <image src="./common/images/appbar.chevron.right.bin"
                   class="arrow-icon">d</image>
        </list-item>
    </list>
</div>
```

**pages/index/index.css：**此文件定义了index布局和页面的样式。

```css
.container {
    display: flex;
    /* align-items: center;
    justify-content: center; */
    width: 454px;
    height: 454px;
    margin: 0px;
    padding: 0px;
    background-color: black;
}

.list-container {
    width: 300px;
    height: 300px;
    left: 75px;
    top: 90px;
    border-width: 0px;
    background-color: black;
}

.list-item {
    width: 454px;
    height: 100px;
    left: 0px;
    background-color: black;
    border-width: 0px;
    border-color: red;
}

.app-icon {
    top: 20px;
    left: 100px;
}

.arrow-icon {
    top: 18px;
    left: 300px;
}

.maintitle {
    top: 40px;
    left: 180px;
    color: white;
    width: 130px;
    height: 35px;
    font-family: simsun;
    font-size: 30px;
}

.maintitle-note {
    top: 58px;
    left: 260px;
    color: white;
    width: 100px;
    height: 35px;
    font-family: simsun;
    font-size: 20px;
}

.subtitle {
    top: 20px;
    left: 180px;
    color: white;
    width: 100px;
    height: 35px;
    font-family: simsun;
    font-size: 20px;
}
```

**pages/index/index.js：**此文件定义了index页面的业务逻辑，比如数据绑定，事件处理等。此处，变量"title"采用数据绑定的形式定义为字符串"World"，用户可以在需要的业务逻辑中修改"title"的值。

```javascript
router  = require("@system.router")

export default {
    data: {
        title: 'Hello ',
        pageIndex: 0,
    },
    
    onInit: function () {
        print("==========onInit==========")
    },

    onReady: function () {
        this.data.pageIndex = 20;
        // this.data.user.age = 30;
        print("==========onReady==========")
        print(this.data)
        print(this.data.pageIndex)
    },

    onShow: function () {
        print("==========onShow==========")
    },

    onHide: function () {
        print("==========onHide==========")
    },
    
    onDestroy: function () {
        print("==========onDestroy==========")
    },

    onPageRedirect: function (obj, x, y) {
        print("==========onclick==========")
        print(obj.attributes.url);
        print(x);
        print(y);
        router.replace({
            uri: obj.attributes.url
        })
    }
}
```

**注意事项：**

* JS中的`console.log`在这里只支持`print`

# 运行应用

**Linux**

```shell
cd evuesimulator-linux-v2.0
./evuesimulator test/LiteWearable/
```

**Windows**

```shell
cd evuesimulator-windows-v2.0
evuesimulator.exe test/LiteWearable/
```
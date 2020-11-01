应用生命周期主要有两个：应用创建时调用的onCreate和应用销毁时触发的onDestroy。

一个应用中可能会有多个页面，一个页面一般包括onInit、onReady、onShow和onDestroy等在页面创建、显示和销毁时会触发调用的事件：

- onInit() ：表示页面的数据已经准备好，可以使用js文件中的data数据。
- onReady() ：表示页面已经编译完成，可以将界面显示给用户。
- onShow() ：JS UI只支持应用同时运行并展示一个页面，当打开一个页面时，上一个页面就销毁了。当一个页面显示的时候，会调用onShow。
- onDestroy() ：页面销毁时被调用。

![点击放大](http://statics.evmiot.com/95196391995494320938434679404238.png)

当应用从页面A跳转到页面B时，首先调用页面A的onDestroy函数。页面A销毁后，依次调用页面B的onInit、onReady、onShow函数来初始化和显示页面B。
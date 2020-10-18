> 搭建环境和创建项目
>
> JS主体介绍
>
> 运行应用

# 搭建环境和创建项目

- 搭建环境：请参考[下载和安装软件](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/software_install-0000001053582415)和[配置开发环境](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/environment_config-0000001052902427)。
- 创建项目：请参考[创建一个新的工程](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/create_new_project-0000001053342414)，设备类型选择“Lite Wearable”。

# JS主体介绍

HelloWorld工程目录如下图所示：

**图1** 目录结构

![](https://communityfile-drcn.op.hicloud.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20200922162411.10498504611100906543002201012100:50510922084431:2800:20D9F58418B9FDEFE7AB836C72266AFB1E3EC2342CC00AA9B6759A1A4984BCBC.png?needInitFileName=true?needInitFileName=true)

**pages/index/index.hml：**此文件定义了index页面的布局，在index页面中用到的组件，以及这些组件的层级关系。index.hml文件包含了一个text组件，内容为“Hello World”。

```html
<div class="container">
    <text class="title">
      Hello {{title}}
    </text>
</div>
```

**pages/index/index.css：**此文件定义了index页面的样式。index.css文件定义了“container”和“title”的样式。

```css
.container {
  display: flex;  
  justify-content: center;  
  align-items: center;  
  left: 0px;  
  top: 0px; 
  width: 454px;  
  height: 454px;
}
.title {
  font-size: 30px;  
  text-align: center;  
  width: 200px;  
  height: 100px;
}
```

**pages/index/index.js：**此文件定义了index页面的业务逻辑，比如数据绑定，事件处理等。此处，变量“title”采用数据绑定的形式定义为字符串“World”，用户可以在需要的业务逻辑中修改“title”的值。

```javascript
export default {
    data: {
        title: 'World'
    }
}
```

**resources：**此目录用于存放系统级资源配置文件，如应用图标等。

**config.json：**此文件是配置文件，主要定义了页面路由和应用信息，可根据IDE工程和页面创建向导自动完成填充。

```json
{
    "app": {
        "bundleName": "com.huawei.helloworld",
        "vendor": "huawei",
        "version": {
            "code": 1,
            "name": "1"
        },
        "apiVersion": {
            "compatible": 3,
            "target": 4
        }
    },
    "deviceConfig": {
        "default": {}
    },
    "module": {
        "deviceType": ["liteWearable"],
        "distro": {
            "deliveryWithInstall": true,
            "moduleName": "entry",
            "moduleType": "entry"
        },
        "abilities": [{
            "name": "default",
            "icon": "$media:icon",
            "label": "helloworld",
            "visible": true,
            "type": "page"
        }],
        "js": [{
            "pages": ["pages/index/index"],
            "name": "default"
        }]
    }
}
```

# 运行应用

请参考[使用预览器查看应用效果](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/previewer-0000001054328973)。
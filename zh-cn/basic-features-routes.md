> 导入模块
>
> router.replace(OBJECT)

# 导入模块

```javascript
import router from '@system.router';
```

# router.replace(OBJECT)

用应用内的某个页面替换当前页面，并销毁被替换的页面。

## 参数

| 参数名 | 类型   | 必填 | 说明                                                         |
| ------ | ------ | ---- | ------------------------------------------------------------ |
| uri    | string | 是   | 目标页面的uri，可以是一下的两种格式：<br/>页面绝对路径，由配置文件中pages列表提供，例如：`pages/index/index`,`pages/detail/detail`<br/>特殊值，如果uri的值是"/"，则跳转到首页。 |
| params | Object | 否   | 跳转时要同时传递到目标页面的数据，跳转到目标页面后，参数可以在页面中直接使用，如this.data1(data1为跳转时params参数中的key值)。 |

## 示例

```javascript
// 在当前页面中
router.replace({
  uri: 'pages/detail/detail',
  params: {
      data1: 'message',
  },
});
// 在detail页面中
console.info('showData1:' + this.data1);
```


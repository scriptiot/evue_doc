> 导入模块
>
> brightness.getValue(OBJECT)
>
> brightness.setValue(OBJECT)
>
> brightness.getMode(OBJECT)
>
> brightness.setMode(OBJECT)
>
> brightness.setKeepScreenOn(OBJECT)

# 导入模块

```javascript
import brightness from '@system.brightness';
```

# brightness.getValue(OBJECT)

获得设备当前的屏幕亮度值。

## 参数

| 参数名   | 类型     | 必填 | 说明                     |
| -------- | -------- | ---- | ------------------------ |
| success  | Function | 否   | 接口调用成功的回调函数。 |
| fail     | Function | 否   | 接口调用失败的回调函数。 |
| complete | Function | 否   | 接口调用结束的回调函数。 |

success返回值：

| **参数名** | 类型   | **说明**                          |
| ---------- | ------ | --------------------------------- |
| value      | number | 屏幕亮度，取值为1-255之间的整数。 |

## 示例

```javascript
brightness.getValue({
  success: function(data){
    console.log('success get brightness value:' + data.value);
  },
  fail: function(data, code) {
    console.log('get brightness fail, code: ' 
                + code + ', data: ' + data);
  },
});
```

# brightness.setValue(OBJECT)

设置设备当前的屏幕亮度值。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| value    | number   | 是   | 屏幕亮度，值为1-255之间的整数。<br/>如果值小于等于0，系统按1处理。<br/>如果值大于255，系统按255处理。<br/>如果值为小数，系统将处理为整数。例如设置为8.1，系统按8处理。 |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

## 示例

```javascript
brightness.setValue({
  value: 100,
  success: function(){
    console.log('handling set brightness success.'); 
  },
  fail: function(data, code){
    console.log('handling set brightness value fail, code:' 
                + code + ', data: ' + data);
  },
});
```

# brightness.getMode(OBJECT)

获得当前屏幕亮度模式。

## 参数

| 参数名   | 类型     | 必填 | 说明                     |
| -------- | -------- | ---- | ------------------------ |
| success  | Function | 否   | 接口调用成功的回调函数。 |
| fail     | Function | 否   | 接口调用失败的回调函数。 |
| complete | Function | 否   | 接口调用结束的回调函数。 |

success返回值：

| **参数名** | **类型** | **说明**                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| mode       | number   | 值为0或1：<br/>0为手动调节屏幕亮度模式<br/>1为自动调节屏幕亮度模式 |

## 示例

```javascript
brightness.getMode({
  success: function(data){
    console.log('success get mode:' + data.mode);
  },
  fail: function(data, code){
    console.log('handling get mode fail, code:' 
                + code + ', data: ' + data);
  },
});
```

# brightness.setMode(OBJECT)

设置设备当前的屏幕亮度模式。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                     |
| -------- | -------- | ---- | -------------------------------------------------------- |
| mode     | number   | 是   | 值为0或1<br/>0为手动调节屏幕亮度<br/>1为自动调节屏幕亮度 |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                 |
| fail     | Function | 否   | 接口调用失败的回调函数。                                 |
| complete | Function | 否   | 接口调用结束的回调函数。                                 |

## 示例

```javascript
brightness.setMode({
  mode: 1,
  success: function(){
    console.log('handling set mode success.'); 
  },
  fail: function(data, code){
    console.log('handling set mode fail, code:' 
                + code + ', data: ' + data);
  },
});
```

# brightness.setKeepScreenOn(OBJECT)

设置屏幕是否保持常亮状态，开启常亮模式推荐在onShow()阶段调用。

## 参数

| **参数名**   | **类型** | 必填 | **说明**                 |
| ------------ | -------- | ---- | ------------------------ |
| keepScreenOn | boolean  | 是   | 是否保持屏幕常亮。       |
| success      | Function | 否   | 接口调用成功的回调函数。 |
| fail         | Function | 否   | 接口调用失败的回调函数。 |
| complete     | Function | 否   | 接口调用结束的回调函数。 |



## 示例

```javascript
brightness.setKeepScreenOn({
  keepScreenOn: true,
  success: function () {
    console.log('handling set keep screen on success.')
  },
  fail: function (data, code) {
    console.log('handling set keep screen on fail, code:' 
                + code + ', data: ' + data);
  },
});
```


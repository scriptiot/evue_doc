> 导入模块
>
> vibrator.vibrate(OBJECT)
>

# 导入模块

```javascript
import vibrator from '@system.vibrator';
```

# vibrator.vibrate(OBJECT)

触发设备振动。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| mode     | string   | 否   | 振动的模式，其中long表示长振动，short表示短振动，默认值为long。 |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

## 示例

```javascript
vibrator.vibrate({
  mode: 'short',
  success() {
    console.log('success to vibrate');
  },
  fail(data, code) {
    console.log('handle fail, data = ${data}, code = ${code}');
  },
});
```

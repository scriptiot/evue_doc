> 导入模块
>
> battery.getStatus(OBJECT)
>

# 导入模块

```javascript
import battery from '@system.battery';
```

# battery.getStatus(OBJECT)

获取设备当前的充电状态及剩余电量。

## 参数

| 参数名   | 类型     | 必填 | 说明                     |
| -------- | -------- | ---- | ------------------------ |
| success  | Function | 否   | 接口调用成功的回调函数。 |
| fail     | Function | 否   | 接口调用失败的回调函数。 |
| complete | Function | 否   | 接口调用结束的回调函数。 |

success返回值：

| **参数名** | 类型    | 说明                                     |
| ---------- | ------- | ---------------------------------------- |
| charging   | boolean | 当前电池是否在充电中。                   |
| level      | number  | 当前电池的电量，取值范围：0.00 - 1.00 。 |

## 示例

```javascript
battery.getStatus({
  success: function(data) {
    console.log('success get battery level:' + data.level);
  },
  fail: function(data, code) {
    console.log('fail to get battery level code:' + code + ', data: ' + data);
  },
});
```

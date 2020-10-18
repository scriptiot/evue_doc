> 导入模块
>
> 传感器错误码列表
>
> sensor.subscribeStepCounter(OBJECT)
>
> sensor.unsubscribeStepCounter()
>
> sensor.subscribeBarometer(OBJECT)
>
> sensor.unsubscribeBarometer()
>
> sensor.subscribeHeartRate(OBJECT)
>
> sensor.unsubscribeHeartRate()
>
> sensor.subscribeOnBodyState(OBJECT)
>
> sensor.unsubscribeBodyState()
>
> sensor.getOnBodyState()

# 导入模块

```javascript
import sensor from '@system.sensor';
```

# 传感器错误码列表

| 错误码 | 说明                         |
| ------ | ---------------------------- |
| 900    | 当前设备不支持相应的传感器。 |

# sensor.subscribeStepCounter(OBJECT)

订阅计步传感器数据变化。再次调用时，会覆盖前一次调用效果，即仅最后一次调用生效。

## 参数

| 参数名  | 类型     | 必填 | 说明                             |
| ------- | -------- | ---- | -------------------------------- |
| success | Function | 是   | 计步传感器数据改变后的回调函数。 |
| fail    | Function | 否   | 接口调用失败的回调函数。         |

success返回值：

| **参数名** | **类型** | **说明**                         |
| ---------- | -------- | -------------------------------- |
| steps      | number   | 计步传感器重启后累计记录的步数。 |

## 示例

```javascript
sensor.subscribeStepCounter({
  success: function(ret) {
    console.log('get step value:' + ret.steps);
  },
  fail: function(data, code) {
    console.log('subscribe step count fail, code:' + code + ', data:' + data);
  },
});
```

> 说明：建议在页面销毁时，即onDestory回调中，取消数据订阅，避免不必要的性能开销。

# sensor.unsubscribeStepCounter()

取消订阅计步传感器。

## 参数

无

## 示例

```javascript
sensor.unsubscribeStepCounter();
```

# sensor.subscribeBarometer(OBJECT)

订阅气压传感器数据变化。再次调用时，会覆盖前一次调用效果，即仅最后一次调用生效。

## 参数

| 参数名  | 类型     | 必填 | 说明                             |
| ------- | -------- | ---- | -------------------------------- |
| success | Function | 是   | 气压传感器数据改变后的回调函数。 |
| fail    | Function | 否   | 接口调用失败的回调函数。         |

success返回值：

| **参数名** | 类型   | **说明**               |
| ---------- | ------ | ---------------------- |
| pressure   | number | 气压值，单位：帕斯卡。 |

## 示例

```javascript
sensor.subscribeBarometer({
  success: function(ret) {
    console.log('get data value:' + ret.pressure);
  },
  fail: function(data, code) {
    console.log('subscribe barometer fail, code: ' + code + ', data: ' + data);
  },
});
```

> **说明** ：建议在页面销毁时，即onDestory回调中，取消数据订阅，避免不必要的性能开销。

# sensor.unsubscribeBarometer()

取消订阅气压传感器。

## 参数

无

## 示例

```javascript
sensor.unsubscribeBarometer();
```

# sensor.subscribeHeartRate(OBJECT)

订阅心率传感器数据变化。再次调用时，会覆盖前一次调用效果，即仅最后一次调用生效。

## 参数

| 参数名  | 类型     | 必填 | 说明                                            |
| ------- | -------- | ---- | ----------------------------------------------- |
| success | Function | 是   | 心率传感器数据改变后的回调函数，默认频率5s/次。 |
| fail    | Function | 否   | 接口调用失败的回调函数。                        |

success返回值：

| **参数名** | 类型   | **说明**                |
| ---------- | ------ | ----------------------- |
| heartRate  | number | 心率值。255表示非法值。 |

## 示例

```javascript
sensor.subscribeHeartRate({
  success: function(ret) {
    console.log('get heartrate value:' + ret.heartRate);
  },
  fail: function(data, code) {
    console.log('subscribe heart rate fail, code: ' + code + ', data: ' + data);
  },
});
```

> **说明** ：建议在页面销毁时，即onDestory回调中，取消数据订阅，避免不必要的性能开销。

# sensor.unsubscribeHeartRate()

取消订阅心率。

## 参数

无

## 示例

```javascript
sensor.unsubscribeHeartRate();
```

# sensor.subscribeOnBodyState(OBJECT)

订阅设备佩戴状态。再次调用时，会覆盖前一次调用效果，即仅最后一次调用生效。

## 参数

| 参数名  | 类型     | 必填 | 说明                       |
| ------- | -------- | ---- | -------------------------- |
| success | Function | 是   | 穿戴状态改变后的回调函数。 |
| fail    | Function | 否   | 接口调用失败的回调函数。   |

success返回值：

| **参数名** | 类型    | **说明**     |
| ---------- | ------- | ------------ |
| value      | boolean | 是否已佩戴。 |

## 示例

```javascript
sensor.subscribeOnBodyState({
  success: function(ret) {
    console.log('get on-body state value:' + ret.value);
  },
  fail: function(data, code) {
    console.log('fail to get on body state, code:' + code + ', data: ' + data);
  },
});
```

> **说明** ：建议在页面销毁时，即onDestory回调中，取消数据订阅，避免不必要的性能开销。

# sensor.unsubscribeOnBodyState()

取消订阅设备佩戴状态。

## 参数

无

## 示例

```javascript
sensor.unsubscribeOnBodyState();
```

# sensor.getOnBodyState()

获取设备佩戴状态。

 ## 参数

| **参数名** | 类型     | 必填 | **说明**                 |
| ---------- | -------- | ---- | ------------------------ |
| success    | Function | 否   | 接口调用成功的回调函数。 |
| fail       | Function | 否   | 接口调用失败的回调函数。 |
| complete   | Function | 否   | 接口调用结束的回调函数。 |

success返回值：

| 参数名 | **类型** | **说明**     |
| ------ | -------- | ------------ |
| value  | boolean  | 是否已佩戴。 |

## 示例

```javascript
sensor.getOnBodyState({
  success: function(ret) {
    console.log('on body state: ' + ret.value);
  },
  fail: function(data, code) {
    console.log('handing fail, message: ' + data + ', code: ' + code);
  },
});
```
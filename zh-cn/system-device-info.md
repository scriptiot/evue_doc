> 导入模块
>
> device.getInfo(OBJECT)
>

# 导入模块

```javascript
import device from '@system.device';
```

# device.getInfo(OBJECT)

获取当前设备的信息。

## 参数

| 参数名   | 类型     | 必填 | 说明                     |
| -------- | -------- | ---- | ------------------------ |
| success  | Function | 否   | 接口调用成功的回调函数。 |
| fail     | Function | 否   | 接口调用失败的回调函数。 |
| complete | Function | 否   | 接口调用结束的回调函数。 |

success返回值：

| **参数名**    | **类型** | **说明**                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| brand         | string   | 品牌。                                                       |
| manufacturer  | string   | 生产商。                                                     |
| model         | string   | 型号。                                                       |
| product       | string   | 代号。                                                       |
| language      | string   | 系统语言。                                                   |
| region        | string   | 系统地区。                                                   |
| windowWidth   | number   | 可使用的窗口宽度。                                           |
| windowHeight  | number   | 可使用的窗口高度。                                           |
| screenDensity | number   | 屏幕密度。                                                   |
| screenShape   | string   | 屏幕形状。可取值：<br/>**rect：**方形屏；<br/>**circle：**圆形屏。 |

fail返回错误代码：

| **错误码** | **说明**                       |
| ---------- | ------------------------------ |
| 200        | 返回结果中存在无法获得的信息。 |

## 示例

```javascript
device.getInfo({
  success: function(data) {
    console.log('success get device info brand:' + data.brand);
  },
  fail: function(data, code) {
    console.log('fail get device info code:'+ code + ', data: ' + data);
  },
});
```

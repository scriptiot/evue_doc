> 同步
>
> 异步
>
> 订阅

# 同步

同步方法调用后必须等到方法结果返回后才能继续后续的行为，返回值可以是任意类型。

## 示例

```javascript
var info = app.getInfo();
console.log(JSON.stringify(info));
```

# 异步

异步方法调用整个过程不会阻碍调用者的工作。业务执行完成后会调用开发者提供的回调函数。

* 异步接口支持的回调函数

<table>
    <tr>
        <th>回调函数</th>
        <th>参数名</th>
        <th>类型</th>
        <th>返回值</th>
        <th>说明</th>
    </tr>
    <tr>
        <td>success</td>
        <td rowspan="2">data</td>
        <td rowspan="2">any</td>
        <td>可选，返回值可以是任意类型，详见接口使用文档。</td>
        <td rowspan="3">在执行完成时触发。</td>
    </tr>
    <tr>
        <td rowspan="2">fail</td>
        <td>错误信息内容，一般是字符串，也可能是其他类型，详见接口使用文档。</td>
    </tr>
    <tr>
        <td>code</td>
        <td>number</td>
        <td>错误代码，详见通用错误码。</td>
    </tr>
    <tr>
        <td>cancel</td>
        <td>data</td>
        <td>any</td>
        <td>一般无内容，详见接口使用文档。</td>
        <td>在用户取消时触发。部分用户交互场景可能有对该回调接口的支持。</td>
    </tr>
    <tr>
        <td>complete</td>
        <td>-</td>
        <td>-</td>
        <td>-</td>
        <td>在执行完成时触发。</td>
    </tr>
</table>
> **说明：**
>
> * success、fail、cancel和complete四个回调函数是否支持参考具体接口描述
> * success、fail和cancel三个回调函数的触发是互斥的，即会且只会在一个回调函数中触发，触发任意一个都会再次调用complete回调。

## 示例

```javascript
battery.getStatus({
  success: function(data) {
    console.log('success get battery level:' + data.level);
  },
  fail: function(data, code) {
    console.log('fail to get battery level code:' + code);
  },
});
```

# 订阅

订阅接口不会立即返回结果，开发者要在参数中设置相应的回调函数；该回调函数会在完成时或者事件变化时进行回调；可以执行多次。

* 订阅接口支持以下回调函数

<table>
  <tr>
    <th>回调哈安徽</th>
    <th>参数名</th>
    <th>类型</th>
    <th>返回值</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>success</td>
    <td>data</td>
    <td>any</td>
    <td>返回值可以是任意类型，详见接口使用文档。</td>
    <td>接口调用成功或事件变更时触发，可能会触发多次。</td>
  </tr>
  <tr>
    <td rowspan="2">fail</td>
    <td>data</td>
    <td>any</td>
    <td>错误信息内容，一般是字符串，也可能是其他类型，详见接口使用文档。</td>
    <td rowspan="2">在执行失败时触发。一旦触发该回调函数，success不会再次被调用，接口调用结束。</td>
  </tr>
  <tr>
    <td>code</td>
    <td>number</td>
    <td>错误代码，详见通用错误码。</td>
  </tr>
</table>


 ## 示例

以地理位置接口为例

```javascript
geolocation.subscribe({
  success: function(data) {
    console.log('get location. latitude:' + data.latitude);
  },
  fail: function(data, code) {
    console.log('fail to get location. code:' + code);
  },
});
```


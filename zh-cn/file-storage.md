> 导入模块
>
> storage.get(OBJECT)
>
> storage.set(OBJECT)
>
> storage.clear(OBJECT)
>
> storage.delete(OBJECT)

# 导入模块

```javascript
import storage from '@system.storage';
```

# storage.get(OBJECT)

读取存储的内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| key      | string   | 是   | 内容索引。<br/>字符串最大长度为32，且不能包含“\/"*+,:;<=>?[] |
| default  | string   | 否   | key不存在则返回的默认值。如果未指定，则返回空字符串，长度为0。 |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

## 示例

```javascript
storage.get({
  key: 'storage_key',
  success: function(data) {
    console.log('call storage.get success: ' + data);
  },
  fail: function(data, code) {
    console.log('call storage.get fail, code: ' + code + ', data: ' + data);
  },
  complete: function() {
    console.log('call complete');
  },
});
```

# storage.set(OBJECT)

修改存储的内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| key      | string   | 是   | 内容索引。<br/>字符串最大长度为32，且不能包含“\/"*+,:;<=>?[] |
| default  | string   | 否   | key不存在则返回的默认值。如果未指定，则返回空字符串，长度为0。 |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

## 示例

```javascript
storage.set({
  key: 'storage_key',
  value: 'storage value',
  success: function() {
    console.log('call storage.set success.');
  },
  fail: function(data, code) {
    console.log('call storage.set fail, code: ' + code + ', data: ' + data);
  },
});
```

# storage.clear(OBJECT)

清空存储的内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                     |
| -------- | -------- | ---- | ---------------------------------------- |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。 |
| fail     | Function | 否   | 接口调用失败的回调函数。                 |
| complete | Function | 否   | 接口调用结束的回调函数。                 |

## 示例

```javascript
storage.clear({
  success: function() {
    console.log('call storage.clear success.');
  },
  fail: function(data, code) {
    console.log('call storage.clear fail, code: ' + code + ', data: ' + data);
  },
});
```

# storage.delete(OBJECT)

删除存储的内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                    |
| -------- | -------- | ---- | ------------------------------------------------------- |
| key      | string   | 是   | 内容索引。字符串最大长度为32，且不能包含“\/"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                |
| fail     | Function | 否   | 接口调用失败的回调函数。                                |
| complete | Function | 否   | 接口调用结束的回调函数。                                |

## 示例

```javascript
storage.delete({
  key: 'Storage1',
  success: function() {
    console.log('call storage.delete success.');
  },
  fail: function(data, code) {
    console.log('call storage.delete fail, code: ' + code + ', data: ' + data);
  },
});
```
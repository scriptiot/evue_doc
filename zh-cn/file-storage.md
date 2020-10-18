> 导入模块
>
> file.move(OBJECT)
>
> file.copy(OBJECT)
>
> file.list(OBJECT)
>
> file.get(OBJECT)
>
> file.delete(OBJECT)
>
> file.writeText(OBJECT)
>
> file.wtireArrayBuffer(OBJECT)
>
> file.readText(OBJECT)
>
> file.readArrayBuffer(OBJECT)
>
> file.access(OBJECT)
>
> file.mkdir(OBJECT)
>
> file.rmdir(OBJECT)

涉及到文件目录的请参考[存储目录定义](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-file-0000001056483114#ZH-CN_TOPIC_0000001056483114__zh-cn_topic_0000000000616658_section1856519365229)。

# 导入模块

```javascript
import file from '@system.file';
```

# file.move(OBJECT)

将指定文件移动到其他指定位置。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| srcUri   | string   | 是   | 要移动的文件的uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| dstUri   | string   | 是   | 文件要移动到的位置的uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.move({
  srcUri: 'internal://app/myfiles1',
  dstUri: 'internal://app/myfiles2',
  success: function(uri) {
    console.log('call success callback success');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.copy(OBJECT)

将指定文件拷贝并存储到指定位置，接口所使用的URI描述详见[文件组织](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-file-0000001056483114#ZH-CN_TOPIC_0000001056483114)。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| srcUri   | string   | 是   | 要拷贝的文件的uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| dstUri   | string   | 是   | 文件要拷贝到的位置的uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.copy({
  srcUri: 'internal://app/file.txt',
  dstUri: 'internal://app/file_copy.txt',
  success: function(uri) {
    console.log('call success callback success');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.list(OBJECT)

获取指定路径下全部文件的列表，接口所使用的 URI 描述详见[文件组织](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-file-0000001056483114#ZH-CN_TOPIC_0000001056483114)。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 目录uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

success返回值：

| 参数名   | 类型  | 说明                                                         |
| -------- | ----- | ------------------------------------------------------------ |
| fileList | Array | 获取的文件列表，其中每个文件的信息的格式为：<br/>**{**<br/>**uri:'file1',**<br/>**lastModifiedTime:1589965924479,**<br/>**length:10240,**<br/>**type: 'file'**<br/>**}** |

每个文件的元信息：

| 参数名           | 类型   | 说明                                                         |
| ---------------- | ------ | ------------------------------------------------------------ |
| uri              | string | 文件的 uri。                                                 |
| lastModifiedTime | number | 文件上一次保存时的时间戳，显示从1970/01/01 00:00:00 GMT到当前时间的毫秒数。<br/>轻量级智能穿戴上受限于底层文件系统约束，固定返回0。 |
| length           | number | 文件的大小，单位为字节。<br/>当type等于dir时，length 固定为0。 |
| type             | string | 文件的类型，可选值为：<br/>**dir：**目录；<br/>**file：**文件。 |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.list({
  uri: 'internal://app/pic',
  success: function(data) {
    console.log(data.fileList);
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.get(OBJECT)

获取指定本地文件的信息，URI请参考[文件组织](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-file-0000001056483114#ZH-CN_TOPIC_0000001056483114)。

## 参数

| 参数名    | 类型     | 必填 | 说明                                                         |
| --------- | -------- | ---- | ------------------------------------------------------------ |
| uri       | string   | 是   | 文件的uri。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| recursive | boolean  | 否   | 是否进行递归获取子目录文件列表，缺省为false。                |
| success   | Function | 否   | 接口调用成功的回调函数，返回存储的内容。                     |
| fail      | Function | 否   | 接口调用失败的回调函数。                                     |
| complete  | Function | 否   | 接口调用结束的回调函数。                                     |

success返回值：

| 参数名           | 类型   | 说明                                                         |
| ---------------- | ------ | ------------------------------------------------------------ |
| uri              | string | 文件的uri。                                                  |
| length           | number | 文件字节长。当type等于dir时，length 固定为0。                |
| lastModifiedTime | number | 文件保存时的时间戳，从1970/01/01 00:00:00到当前时间的毫秒数。<br/>轻量级智能穿戴上受限于底层文件系统约束，固定返回0。 |
| type             | string | 文件类型，可选值为：<br/>**dir：**目录；<br/>**file：**文件。 |
| subFiles         | Array  | 文件列表。                                                   |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.get({
  uri: 'internal://app/file',
  success: function(data) {
    console.log(data.uri);
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.delete(OBJECT)

删除本地文件，使用的URI参考[文件组织](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-file-0000001056483114#ZH-CN_TOPIC_0000001056483114)。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.delete({
  uri: 'internal://app/my_file',
  success: function() {
    console.log('call delete success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.writeText(OBJECT)

写文本内容到指定文件。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| text     | string   | 是   | 写入的字符串。                                               |
| encoding | string   | 否   | 编码格式，默认为UTF-8。目前仅支持UTF-8。                     |
| append   | boolean  | 否   | 是否追加模式，默认为false。                                  |
| success  | Function | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.writeText({
  uri: 'internal://app/workspace/test.txt',
  text: 'Text that just for test.',
  success: function() {
    console.log('call writeText success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.writeArrayBuffer(OBJECT)

写Buffer内容到指定文件。

## 参数

| 参数名   | 类型       | 必填 | 说明                                                         |
| -------- | ---------- | ---- | ------------------------------------------------------------ |
| uri      | string     | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| buffer   | Uint8Array | 是   | 写入的Buffer。                                               |
| encoding | string     | 否   | 编码格式，默认为UTF-8。目前仅支持UTF-8。                     |
| append   | boolean    | 否   | 是否追加模式，默认为false。                                  |
| success  | Function   | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function   | 否   | 接口调用失败的回调函数。                                     |
| complete | Function   | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.writeArrayBuffer({
  uri: 'internal://cache/workspace/test',
  buffer: buffer, //buffer为Uint8Array类型
  success: function() {
    console.log('call writeArrayBuffer success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.readText(OBJECT)

从指定文件中读取文本内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| encoding | string   | 否   | 编码格式，默认为UTF-8。目前仅支持UTF-8。                     |
| position | number   | 否   | 读取的起始位置，默认值为文件的起始位置。                     |
| length   | number   | 否   | 读取的长度，默认值为4096。                                   |
| success  | Function | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

success返回值：

| **参数名** | **类型** | **说明**           |
| ---------- | -------- | ------------------ |
| text       | string   | 读取到的文本内容。 |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.readText({
  uri: 'internal://cache/workspace/text.txt',
  success: function(data) {
    console.log('call readText success: ' + data.text);
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.readArrayBuffer(OBJECT)

从指定文件中读取Buffer内容。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| position | number   | 否   | 读取的起始位置，默认值为文件的起始位置。                     |
| length   | number   | 否   | 读取的长度，默认值为4096。                                   |
| success  | Function | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

success返回值：

| **参数名** | **类型**   | **说明**           |
| ---------- | ---------- | ------------------ |
| buffer     | Uint8Array | 读取到的文件内容。 |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.readArrayBuffer({
  uri: 'internal://app/workspace/test',
  position: 10,
  length: 200,
  success: function(data) {
    console.log('call readArrayBuffer success: ' + data.buffer);
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.access(OBJECT)

判断指定文件或目录是否存在。

## 参数

| 参数名   | 类型     | 必填 | 说明                                                         |
| -------- | -------- | ---- | ------------------------------------------------------------ |
| uri      | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| success  | Function | 否   | 接口调用成功的回调函数。                                     |
| fail     | Function | 否   | 接口调用失败的回调函数。                                     |
| complete | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.access({
  uri: 'internal://app/test',
  success: function() {
    console.log('call access success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.mkdir(OBJECT)

创建指定目录。

## 参数

| 参数名    | 类型     | 必填 | 说明                                                         |
| --------- | -------- | ---- | ------------------------------------------------------------ |
| uri       | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| recursive | boolean  | 否   | 是否递归创建该目录的上级目录，缺省为false。                  |
| success   | Function | 否   | 接口调用成功的回调函数。                                     |
| fail      | Function | 否   | 接口调用失败的回调函数。                                     |
| complete  | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明           |
| ------ | -------------- |
| 202    | 出现参数错误。 |
| 300    | 出现I/O错误。  |

## 示例

```javascript
file.mkdir({
  uri: 'internal://share/test_directory',
  success: function() {
    console.log('call mkdir success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```

# file.rmdir(OBJECT)

删除指定目录。

## 参数

| 参数名    | 类型     | 必填 | 说明                                                         |
| --------- | -------- | ---- | ------------------------------------------------------------ |
| uri       | string   | 是   | 删除文件的uri，不能是应用资源路径。轻量级智能穿戴上字符串最大长度为128，且不能包含“"*+,:;<=>?[] |
| recursive | boolean  | 否   | 是否递归创建该目录的上级目录，缺省为false。                  |
| success   | Function | 否   | 接口调用成功的回调函数。                                     |
| fail      | Function | 否   | 接口调用失败的回调函数。                                     |
| complete  | Function | 否   | 接口调用结束的回调函数。                                     |

fail返回错误代码：

| 错误码 | 说明               |
| ------ | ------------------ |
| 202    | 出现参数错误。     |
| 300    | 出现I/O错误。      |
| 301    | 文件或目录不存在。 |

## 示例

```javascript
file.rmdir({
  uri: 'internal://app/test_directory',
  success: function() {
    console.log('call rmdir success.');
  },
  fail: function(data, code) {
    console.error('call fail callback fail, code: ' + code + ', data: ' + data);
  },
});
```


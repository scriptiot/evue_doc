>  导入模块
>
> app.getInfo()
>
> app.terminate()

# 导入模块

```javascript
import app from '@system.app';
```

# app.getInfo()

获取当前应用配置文件中声明的信息。 

## 参数

无

## 返回值

| 参数名      | 类型   | 说明                 |
| ----------- | ------ | -------------------- |
| appName     | string | 表示应用的名称。     |
| versionName | string | 表示应用的版本名称。 |
| versionCode | number | 表示应用的版本号。   |

## 示例

```javascript
var info = app.getInfo();
console.log(JSON.stringify(info));
```

# app.terminate()

退出当前Ability

## 参数

无

## 示例

```javascript
app.terminate();
```


> 导入模块
>
> configuration.getLocale()

# 导入模块

```javascript
import configuration from '@system.configuration';
```

# configuration.getLocale()

获取应用当前的语言和地区。默认与系统的语言和地区同步。

## 参数

| 参数名          | 类型   | 说明                                                         |
| --------------- | ------ | ------------------------------------------------------------ |
| language        | string | 语言。例如：zh。                                             |
| countryOrRegion | string | 国家或地区。例如：CN。                                       |
| dir             | string | 文字布局方向。取值范围：<br/>**ltr：**从左到右；<br/>**rtl：**从右到左。 |

## 示例

```javascript
const localeInfo = configuration.getLocale();
console.info(localeInfo.language);
```
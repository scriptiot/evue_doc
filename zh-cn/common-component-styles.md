组件普遍支持的可以在style或css中设置组件外观样式。

| 名称                              | 类型     | 默认值      | 必填 | 描述                                                         |
| --------------------------------- | -------- | ----------- | ---- | ------------------------------------------------------------ |
| color                             | <color>  | #808080     | 否   | 候选项字体颜色。                                             |
| font-size                         | <length> | 30px        | 否   | 候选项字体尺寸，类型length，单位px。                         |
| selected-color                    | <color>  | \#ffffff    | 否   | 选中项字体颜色。                                             |
| selected-font-size                | <length> | 38px        | 否   | 选中项字体尺寸，类型length，单位px。                         |
| font-family                       | string   | HYQiHei-65S | 否   | 选项字体类型。                                               |
| width                             | <length> | 0           | 否   | 设置组件自身的宽度。未。设置时组件宽度默认为0。              |
| height                            | <length> | 0           | 否   | 设置组件自身的高度。未设置时组件高度默认为0。                |
| padding                           | <length> | 0           | 否   | 使用简写属性设置所有的内边距属性。                           |
| margin                            | <length> | 0           | 否   | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | <length> | 0           | 否   | 设置左、上、右、下外边距属性。                               |
| border-width                      | <length> | 0           | 否   | 使用简写属性设置元素的所有边框宽度。                         |
| border-color                      | <color>  | black       | 否   | 使用简写属性设置元素的所有边框颜色。                         |
| border-radius                     | <length> | -           | 否   | border-radius属性是设置元素的外边框圆角半径。                |
| background-color                  | <color>  | -           | 否   | 设置背景颜色。                                               |
| display                           | string   | flex        | 否   | 确定一个元素所产生的框的类型，可选值为：<br/>**flex：**弹性布局。<br/>**none：**不渲染此元素。 |
| [left\|top]                       | <length> | 否          | 否   | left\|top需要配合position样式使用，来确定元素的偏移位置。<br/>left属性规定元素的左边缘。该属性定义了定位元素左外边距边界与其包含块左边界之间的偏移。<br/>top属性规定元素的顶部边缘。该属性定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |

> **说明**
>
> 通用样式都不是必填项。
>
> 目前，样式支持的颜色格式如下：
>
> * rgb(255, 255, 255)
> * rgba(255, 255, 255, 1.0)
> * HEX格式：#rrggbb，#aarrggbb
> * 枚举格式：black，white等，详见[表1](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-common-component-styles-0000001055614307#ZH-CN_TOPIC_0000001055614307__zh-cn_topic_0000001050791158_table16879155017425)。Script脚本中不支持枚举格式。

表1 当前支持的颜色枚举

<table>
	<tr>
		<th>枚举名称</th>
		<th>对应颜色</th>
		<th>颜色</th>
	</tr>
	<tr>
		<td>aliceblue</td>
		<td>#f0f8ff</td>
		<td bgcolor="#f0f8ff">&nbsp;</td>
	</tr>
    <tr>
		<td>antiquewhite</td>
		<td>#faebd7</td>
		<td bgcolor="#faebd7">&nbsp;</td>
	</tr>
    <tr>
		<td>aqua</td>
		<td>#00ffff</td>
		<td bgcolor="#00ffff">&nbsp;</td>
	</tr>
    <tr>
		<td>aquamarine</td>
		<td>#7fffd4</td>
		<td bgcolor="#7fffd4">&nbsp;</td>
	</tr>
    <tr>
		<td>azure</td>
		<td>#f0ffff</td>
		<td bgcolor="#f0ffff">&nbsp;</td>
	</tr>
    <tr>
		<td>beige</td>
		<td>#f5f5dc</td>
		<td bgcolor="#f5f5dc">&nbsp;</td>
	</tr>
    <tr>
		<td>bisque</td>
		<td>#ffe4c4</td>
		<td bgcolor="#ffe4c4">&nbsp;</td>
	</tr>
    <tr>
		<td>black</td>
		<td>#000000</td>
		<td bgcolor="#000000">&nbsp;</td>
	</tr>
    <tr>
		<td>blanchedalmond</td>
		<td>#ffebcd</td>
		<td bgcolor="#ffebcd">&nbsp;</td>
	</tr>
    <tr>
		<td>blue</td>
		<td>#0000ff</td>
		<td bgcolor="#0000ff">&nbsp;</td>
	</tr>
    <tr>
		<td>blueviolet</td>
		<td>#8a2be2</td>
		<td bgcolor="#8a2be2">&nbsp;</td>
	</tr>
    <tr>
		<td>brown</td>
		<td>#a52a2a</td>
		<td bgcolor="#a52a2a">&nbsp;</td>
	</tr>
    <tr>
		<td>burlywood</td>
		<td>#deB887</td>
		<td bgcolor="#deB887">&nbsp;</td>
	</tr>
    <tr>
		<td>cadetblue</td>
		<td>#5f9ea0</td>
		<td bgcolor="#5f9ea0">&nbsp;</td>
	</tr>
    <tr>
		<td>chartreuse</td>
		<td>#7fff00</td>
		<td bgcolor="#7fff00">&nbsp;</td>
	</tr>
    <tr>
		<td>chocolate</td>
		<td>#d2691e</td>
		<td bgcolor="#d2691e">&nbsp;</td>
	</tr>
    <tr>
		<td>coral</td>
		<td>#ff7f50</td>
		<td bgcolor="#ff7f50">&nbsp;</td>
	</tr>
    <tr>
		<td>cornflowerblue</td>
		<td>#6495ed</td>
		<td bgcolor="#6495ed">&nbsp;</td>
	</tr>
    <tr>
		<td>cornsilk</td>
		<td>#fff8dc</td>
		<td bgcolor="#fff8dc">&nbsp;</td>
	</tr>
    <tr>
		<td>crimson</td>
		<td>#dc143c</td>
		<td bgcolor="#dc143c">&nbsp;</td>
	</tr>
    <tr>
		<td>cyan</td>
		<td>#00ffff</td>
		<td bgcolor="#00ffff">&nbsp;</td>
	</tr>
    <tr>
		<td>darkblue</td>
		<td>#00008b</td>
		<td bgcolor="#00008b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkcyan</td>
		<td>#008b8b</td>
		<td bgcolor="#008b8b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkgoldenrod</td>
		<td>#b8860b</td>
		<td bgcolor="#b8860b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkgray</td>
		<td>#a9a9a9</td>
		<td bgcolor="#a9a9a9">&nbsp;</td>
	</tr>
    <tr>
		<td>darkgreen</td>
		<td>#006400</td>
		<td bgcolor="#006400">&nbsp;</td>
	</tr>
    <tr>
		<td>darkgrey</td>
		<td>#a9a9a9</td>
		<td bgcolor="#a9a9a9">&nbsp;</td>
	</tr>
    <tr>
		<td>darkkhaki</td>
		<td>#bdb76b</td>
		<td bgcolor="#bdb76b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkmagenta</td>
		<td>#8b008b</td>
		<td bgcolor="#8b008b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkolivegreen</td>
		<td>#556b2f</td>
		<td bgcolor="#556b2f">&nbsp;</td>
	</tr>
    <tr>
		<td>darkorange</td>
		<td>#ff8c00</td>
		<td bgcolor="#ff8c00">&nbsp;</td>
	</tr>
    <tr>
		<td>darkorchid</td>
		<td>#9932cc</td>
		<td bgcolor="#9932cc">&nbsp;</td>
	</tr>
    <tr>
		<td>darkred</td>
		<td>#8b0000</td>
		<td bgcolor="#8b0000">&nbsp;</td>
	</tr>
    <tr>
		<td>darksalmon</td>
		<td>#e9967a</td>
		<td bgcolor="#e9967a">&nbsp;</td>
	</tr>
    <tr>
		<td>darkseagreen</td>
		<td>#8fbc8f</td>
		<td bgcolor="#8fbc8f">&nbsp;</td>
	</tr>
    <tr>
		<td>darkslateblue</td>
		<td>#483d8b</td>
		<td bgcolor="#483d8b">&nbsp;</td>
	</tr>
    <tr>
		<td>darkslategray</td>
		<td>#2f4f4f</td>
		<td bgcolor="#2f4f4f">&nbsp;</td>
	</tr>
    <tr>
		<td>darkturquoise</td>
		<td>#00ced1</td>
		<td bgcolor="#00ced1">&nbsp;</td>
	</tr>
    <tr>
		<td>darkviolet</td>
		<td>#9400d3</td>
		<td bgcolor="#9400d3">&nbsp;</td>
	</tr>
    <tr>
		<td>deeppink</td>
		<td>#ff1493</td>
		<td bgcolor="#ff1493">&nbsp;</td>
	</tr>
    <tr>
		<td>deepskyblue</td>
		<td>#00bfff</td>
		<td bgcolor="#00bfff">&nbsp;</td>
	</tr>
</table>
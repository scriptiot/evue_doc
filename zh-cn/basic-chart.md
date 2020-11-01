> 子组件  
> 属性  
> 方法  
> 事件  
> 样式  
> DEMO

图表组件，用于呈现线性图、柱状图界面。

# 子组件
不支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| type | string | line | 是 | 设置图表类型（不支持动态修改），可选项有：<br/>**bar：**柱状图。<br/>**line：**线型图。 |
| options | Object | - | 是 | 图表参数设置，柱状图和线性图必须设置参数设置。可以设置x轴、y轴的最小值、最大值、刻度数、是否显示，线条宽度、是否平滑等，详见[表1](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table12775365017)。（不支持动态修改） |
| datasets | Array\<Object\> | - | 是 | 数据集合，柱状图和线性图必须设置数据集合。可以设置多条数据集及其背景色，详见[表2](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table13810518157)。 |

**表1** options定义

| **名称** | **类型** | **默认值** | **必填** | **描述**                                                     |
| -------- | -------- | ---------- | -------- | ------------------------------------------------------------ |
| xAxis    | Object   | -          | 是       | x轴参数设置。可以设置x轴最小值、最大值、刻度数以及是否显示。详见[表3](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table11312112919528)。 |
| yAxis    | Object   | -          | 是       | y轴参数设置。可以设置y轴最小值、最大值、刻度数以及是否显示。详见[表4](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table893622720553)。 |
| series   | Object   | -          | 否       | 数据序列参数设置。可以设置1）线的样式，如线宽、是否平滑；2）设置线最前端位置白点的样式和大小。详见[表6](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table7790183513918)和[表7](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table1435760101317)。<br/>**说明**：仅线型图支持。 |

**表2** datasets定义

| 名称                        | 类型            | 默认值   | 必填 | 描述                                    |
| --------------------------- | --------------- | -------- | ---- | --------------------------------------- |
| backgroundColor(deprecated) | \<color\>       | \#ff6384 | 否   | 设置线或柱的颜色（不推荐使用）。        |
| strokeColor                 | \<color\>       | \#ff6384 | 否   | 线条颜色。<br/>**说明：**仅线型图支持。 |
| fillColor                   | \<color\>       | #ff6384  | 否   | 填充颜色。                              |
| data                        | Array\<number\> | -        | 是   | 设置绘制线或柱中的点集。                |
| gradient                    | boolean         | false    | 否   | 设置是否显示填充颜色。                  |

**表3** xAxis定义

| 名称     | 类型      | 默认值   | 必填 | 描述                                                         |
| -------- | --------- | -------- | ---- | ------------------------------------------------------------ |
| min      | number    | 0        | 否   | x轴的最小值。<br/>**说明：**不支持负数。仅线型图支持。       |
| max      | number    | 100      | 否   | x轴的最大值。<br/>**说明：**不支持负数。仅线型图支持。       |
| axisTick | number    | 10       | 否   | x轴显示的刻度数量。<br/>**说明：**仅支持1~20，且具体显示的效果与如下计算值有关（图的宽度所占的像素/（max-min））。<br/>因轻量级智能穿戴为整型运行，在除不尽的情况下会有误差产生，具体的表现形式是x轴末尾可能会空出一段。<br/>在柱状图中，每组数据显示的柱子数量与刻度数量一致，且柱子显示在刻度处。 |
| display  | boolean   | false    | 否   | 是否显示x轴。                                                |
| color    | \<color\> | \#c0c0c0 | 否   | x轴颜色。                                                    |

**表4** yAxis定义

| 名称     | 类型      | 默认值   | 必填 | 描述                                                         |
| -------- | --------- | -------- | ---- | ------------------------------------------------------------ |
| min      | number    | 0        | 否   | y轴的最小值。<br/>**说明：**不支持负数。仅线型图支持。       |
| max      | number    | 100      | 否   | y轴的最大值。<br/>**说明：**不支持负数。仅线型图支持。       |
| axisTick | number    | 10       | 否   | y轴显示的刻度数量。<br/>**说明：**仅支持1~20，且具体显示的效果与如下计算值有关（图的宽度所占的像素/（max-min））。<br/>因轻量级智能穿戴为整型运行，在除不尽的情况下会有误差产生，具体的表现形式是y轴末尾可能会空出一段。<br/>在柱状图中，每组数据显示的柱子数量与刻度数量一致，且柱子显示在刻度处。 |
| display  | boolean   | false    | 否   | 是否显示y轴。                                                |
| color    | \<color\> | \#c0c0c0 | 否   | y轴颜色。                                                    |

**表5** series定义

| 名称        | 类型   | 默认值 | 必填 | 描述                                                         |
| ----------- | ------ | ------ | ---- | ------------------------------------------------------------ |
| lineStyle   | Object | -      | 否   | 线样式设置，如线宽、是否平滑。                               |
| headPoint   | Point  | -      | 否   | 线最前端位置白点的样式和大小。                               |
| topPoint    | Point  | -      | 否   | 最高点的样式和大小。                                         |
| bottomPoint | Point  | -      | 否   | 最低点的样式和大小。                                         |
| loop        | Object | -      | 否   | 设置屏幕显示满时，是否需要重头开始绘制。详见[表8](https://developer.harmonyos.com/cn/docs/documentation/doc-references/lite-wearable-basic-chart-0000001055173380#ZH-CN_TOPIC_0000001055173380__zh-cn_topic_0000001050030933_table13982347173714)。 |

**表6** lineStyle定义

| 名称   | 类型       | 默认值 | 必填 | 描述       |
| ------ | ---------- | ------ | ---- | ---------- |
| width  | \<length\> | 1px    | 否   | 线宽设置。 |
| smooth | boolean    | false  | 否   | 是否平滑。 |

**表7** HeadPoint/TopPoint/BottomPoint定义

| 名称        | 类型       | 默认值   | 必填 | 描述                                                         |
| ----------- | ---------- | -------- | ---- | ------------------------------------------------------------ |
| shape       | string     | circle   | 否   | 线最前端/最高点/最低点位置高亮点的形状。可选值为：<br/>**circle：**圆形。 |
| size        | \<length\> | 5px      | 否   | 线最前端/最高点/最低点位置高亮点的大小。                     |
| strokeWidth | \<length\> | 1px      | 否   | 边框宽度                                                     |
| strokeColor | \<color\>  | \#ff0000 | 否   | 边框颜色。                                                   |
| fillColor   | \<color\>  | \#ff0000 | 否   | 填充颜色。                                                   |
| display     | boolean    | true     | 否   | 是否高亮显示。                                               |

**表8** loop定义

| 名称   | 类型       | 默认值 | 必填 | 描述                                                         |
| ------ | ---------- | ------ | ---- | ------------------------------------------------------------ |
| margin | \<length\> | 1      | 否   | 擦除点的个数（最新绘制的点与最老的点之间的横向距离）。注意：轻量设备margin和topPoint/bottomPoint/headPoint同时使用时，有概率出现point正好位于擦除区域的情况，导致point不可见，因此不建议同时使用。 |

#  方法

| 方法   | 参数                                                         | 描述                                                         |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| append | {<br/>serial: number, // 设置要更新的线型图数据下标<br/>data: Array<number>, // 设置新增的数据<br/>} | 往已有的数据序列中动态添加数据，根据serial指定目标序列，serial为datasets数组的下标，从0开始。注意：不会更新datasets[index].data。仅线型图支持，按横坐标加1递增（与xAxis min/max设置相关）。 |



# 事件

|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

# 样式
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*弹性布局<br/>*none*：不渲染此元素 |
| width | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | \<length\> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |
| [left\|top] | \<length\> | - | 否 | left|

**注意事项：**

* EVUE 1.0版本的chart组件，是一个参数写死的demo，更多扩展支持已在2.0版本提上日程，另一方面，我们也在期待社区给我们更多需求和反馈

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-chart`

**index.hml**

```html
<div style="background-color: white;
            text-align: center;
            width: 454px;
            height: 454px;
            border-width: 0px;">
    <text style="left: 110px;
                 top:70px;
                 width: 200px;
                 height: 60px;
                 text-align: center;
                 font-size: 30px;
                 font-family:simsun;"> 图表 </text>
    <chart style="left: 72px;
                  top:130px;
                  width:300px;
                  height: 250px"></chart>
</div>
```

**index.css**

```css
.container {
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    /*flex-wrap: wrap;*/
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'show-test-chart'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-chart/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evuesimulator.exe ../../test/test-chart/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031223417.jpg)
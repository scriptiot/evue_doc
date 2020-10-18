组件普遍支持的可以在style或css中设置的动态的旋转、平移、缩放效果。
|  名称   | 类型  |  默认值   | 描述  |
|  ----  | ----  |  ----  | ----  |
| transform  | string | - | 详见表1。 |
| animation-name  | string | - | 指定@keyframes，详见表2。 |
| animation-delay  | <time> | 0 | 定义动画播放的延迟时间。支持的单位为[s(秒)|ms(毫秒) ]，默认单位为ms，格式为：1000ms或1s。 |
| animation-duration  | <time> | 0 | 定义一个动画周期。支持的单位为[s(秒)|ms(毫秒) ]，默认单位为ms，格式为：1000ms或1s。<br/> **说明：**轻量级智能穿戴上，动画周期最大值为60s。<br/>animation-duration 样式必须设置，否则时长为 0，则不会播放动画。 |
| animation-iteration-count  | number | infinite | 1 | 定义动画播放的次数，默认播放一次，可通过设置为infinite无限次播放。 |
| animation-timing-function  | string | linear | 描述动画执行的速度曲线，用于使动画更为平滑。可选项有：<br/>**linear：**表示动画从头到尾的速度都是相同的。<br/>**ease-in：**表示动画以低速开始，cubic-bezier(0.42, 0.0, 1.0, 1.0)。<br/>**ease-out：**表示动画以低速结束，cubic-bezier(0.0, 0.0, 0.58, 1.0)。<br/>**ease-in-out：**表示动画以低速开始和结束，cubic-bezier(0.42, 0.0, 0.58, 1.0)。 |
| animation-fill-mode  | string | none | 指定动画执行结束后的状态。可选项有：<br/>**none：**恢复初始状态。<br/>**forwards：**保持动画结束时的状态（在最后一个关键帧中定义）。 |

表1 transform操作说明
|  名称   | 类型  | 描述  |
|  ----  | ----  | ----  |
| translateX  | <length> | X轴方向平移动画属性 |
| translateY  | <length> | Y轴方向平移动画属性 |
| rotate  | \<deg\> \| \<rad\> | 旋转动画属性 |

> 说明：轻量级智能穿戴仅支持原始大小的图片进行旋转。

表2 @keyframes属性说明
|  名称   | 类型  |  默认值   | 描述  |
|  ----  | ----  |  ----  | ----  |
| background-color  | <color> | -  | 动画执行后应用到组件上的背景颜色。 |
| width  | <length> | -  | 动画执行后应用到组件上的宽度值。 |
| height  | <length> | -  | 动画执行后应用到组件上的高度值。 |
| transform  | string | -  | 定义应用在组件上的变换类型，见表1。 |

对于不支持起始值或终止值缺省的情况，可以通过from和to显示指定起始和结束。示例：
```css
@keyframes Go
{
    from {
        background-color: #f76160;
    }
    to {
        background-color: #09ba07;
    }
}
```

![picture](https://communityfile-drcn.op.hicloud.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20200930144419.12562769090068034679161790658283:50510930071315:2800:24C94BA6793BA636D81432870BAA8AA9E5E9732400593733190F2A6DAF7907D2.gif?needInitFileName=true?needInitFileName=true)

> 说明：@keyframes的from/to不支持动态绑定。
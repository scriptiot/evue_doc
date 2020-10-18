> 子组件  
> 属性  
> 事件  
> 样式  
> 方法  
> 示例  

图片帧动画播放器。

# 子组件
不支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id | string | - | 否 | 组件的唯一标识。 |
| style | string | - | 否 | 组件的样式声明。 |
| class | string | - | 否 | 组件的样式类，用于引用样式表。 |
| ref | string | - | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| images | Array<ImageFrame> | - | 是 | 设置图片帧信息集合。每一帧的帧信息包含图片路径、图片大小和图片位置信息。目前支持以下图片格式：png、jpg。ImageFrame的详细说明请见表1。<br/>**说明：**使用时需要使用数据绑定的方式，如images = {{images}}，js中声明相应变量：images: [{src: '/common/heart-rate01.png'}, {src: '/common/heart-rate02.png'}]。 |
| iteration | number | string | infinite | 否 | 设置帧动画播放次数。number表示固定次数，infinite枚举表示无限次数播放。 |
| reverse | boolean | false | 否 | 设置播放顺序。false表示从第1张图片播放到最后1张图片； true表示从最后1张图片播放到第1张图片。 |
| fixedsize | boolean | true | 否 | 设置图片大小是否固定为组件大小。 true表示图片大小与组件大小一致，此时设置图片的width 、height 、top 和left属性是无效的。false表示每一张图片的 width 、height 、top和left属性都要单独设置。 |
| duration | string | - | 是 | 设置单次播放时长。单位支持[s(秒)|ms(毫秒)]，默认单位为ms。 duration为0时，不播放图片。 值改变只会在下一次循环开始时生效。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| stop | - | 帧动画结束时触发。 |
| click | - | 点击动作触发该事件。 |
| longpress | - | 长按动作触发该事件。 |
| swipe | SwipeEvent | 组件上快速滑动后触发。 |

# 样式
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| flex-direction | string | row  | 否 | flex容器主轴方向。可选项有：<br/>*column*：垂直方向从上到下<br/>*row*：水平方向从左到右 |
| flex-wrap  | string | nowrap  | 否 | flex容器是单行还是多行显示，该值暂不支持动态修改。可选项有：<br/>*nowrap*：不换行，单行显示。<br/>*wrap*：换行，多行显示。 |
| justify-content  | string | flex-start  | 否 | flex容器当前行的主轴对齐格式。可选项有：<br/*>flex-start*：项目位于容器的开头。<br/>*flex-end*：项目位于容器的结尾。<br/>*center*：项目位于容器的中心。<br/>*space-between*：项目位于各行之间留有空白的容器内。<br/>*space-around*：项目位于各行之前、之间、之后都留有空白的容器内。 |
| align-items  | string | flex-start | 否 | flex容器当前行的交叉轴对齐格式，可选值为：<br/>*flex-start*：元素向交叉轴起点对齐。<br/>*flex-end*：元素向交叉轴终点对齐。<br/>*center*：元素在交叉轴居中。 |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*弹性布局<br/>*none*：不渲染此元素 |
| width | <length> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | <length> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | <length> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| margin | <length> | 0 | 否 | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。是<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | <length> | 0 | 否 | 设置左、上、右、下外边距属性。 |
| border-width | <length> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | <color> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | <length> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | <color> | - | 否 | 设置背景颜色。 |
| [left\|top] | <length> | - | 否 | left|top需要配合position样式使用，来确定元素的偏移位置。<br/>left属性规定元素的左边缘。该属性定义了定位元素左外边距边界与其包含块左边界之间的偏移。<br/>top属性规定元素的顶部边缘。该属性定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |

# 方法
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| start | - | 开始播放图片帧动画。再次调用，重新从第1帧开始播放。 |
| pause | - | 暂停播放图片帧动画。 |
| stop | - | 停止播放图片帧动画。 |
| resume | - | 继续播放图片帧。 |
| getState | - | 获取播放状态。可能值有：<br/>playing：播放中<br/>paused：已暂停<br/>stopped：已停止。 |

# 示例
```
<!-- xxx.hml -->
<image-animator ref="animator" images="{{images}}" iteration="3" reverse="false" fixedsize="false" duration="2s" style="width: 454px; height: 454px"  onstop="handleStop"  onclick="handleClick">
</image-animator>
```
```javascript
// xxx.js
export default {
  data: {
    images: [{
      src: '/common/heart-rate01.png',
      width: '200px',
      height: '200px',
      top: '127px',
      left: '127px',
    }, {
      src: '/common/heart-rate02.png',
      width: '240px',
      height: '240px',
      top: '107px',
      left: '107px',
    }, {
      src: '/common/heart-rate03.png',
      width: '280px',
      height: '280px',
      top: '87px',
      left: '87px',
    }, {
      src: '/common/heart-rate04.png',
      width: '320px',
      height: '320px',
      top: '67px',
      left: '67px',
    }],
  },
  handleClick() {
    const animator = this.$refs.animator;
    const state = animator.getState();
    if (state === 'paused') {
      animator.resume();
    } else if (state === 'stopped') {
      animator.start();
    } else {
      animator.pause();
    }
  },
  handleStart() {
    console.log('start');
  },
  handlePause() {
    console.log('paused');
  },
  handleStop() {
    console.log('stoped');
  },
  handleResume() {
    console.log('resumed');
  },
}
```
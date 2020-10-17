> 子组件  
> 属性  
> 事件  
> 样式  

基础容器，用作页面结构的根节点或将内容进行分组。

# 子组件
支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

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
| margin-[left|top|right|bottom] | <length> | 0 | 否 | 设置左、上、右、下外边距属性。 |
| border-width | <length> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | <color> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | <length> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | <color> | - | 否 | 设置背景颜色。 |
| [left|top] | <length> | - | 否 | left|top需要配合position样式使用，来确定元素的偏移位置。<br/>left属性规定元素的左边缘。该属性定义了定位元素左外边距边界与其包含块左边界之间的偏移。<br/>top属性规定元素的顶部边缘。该属性定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |
> 页面结构  
> 数据绑定  
> 事件绑定  
> 列表渲染  
> 条件渲染  

HML（HarmonyOS Markup Language）是一套类HTML的标记语言，通过组件，事件构建出页面的内容。页面具备数据绑定、事件绑定、列表渲染、条件渲染等高级能力。

# 页面结构
```
<!-- xxx.hml -->
<div class="item-container">
  <text class="item-title">Image Show</text>
  <div class="item-content">
    <image src="/common/xxx.png" class="image"></image>
  </div>
</div>
```
# 数据绑定
```
<!-- xxx.hml -->
<text> {{content}} </text>
```
```javascript
// xxx.js
export default {
  data: {
    content: 'Hello World!',
  },
}
```
# 事件绑定
```
<!-- xxx.hml -->
<div>
  <!-- 正常格式 -->
  <div onclick="clickfunc"></div>
  <!-- 缩写 -->
  <div @click="clickfunc"></div>
</div>
```
```javascript
<!-- xxx.hml -->
// xxx.js
export default {
  data: {
    obj: '',
  },
  clickfunc: function() {
    this.obj = 'Hello World';
  },
}
```
# 列表渲染
```
<!-- xxx.hml -->
<div class="array-container">
  <!-- div列表渲染 -->
  <!-- 默认$item代表数组中的元素, $idx代表数组中的元素索引 -->
  <div for="{{array}}" tid="id">
    <text>{{$idx}}.{{$item.name}}</text>
  </div>
  <!-- 自定义元素变量名称 -->
  <div for="{{value in array}}" tid="id">    
    <text>{{$idx}}.{{value.name}}</text>
  </div>
  <!-- 自定义元素变量、索引名称 -->
  <div for="{{(index, value) in array}}" tid="id">    
    <text>{{index}}.{{value.name}}</text>
  </div>
</div>
```
```javascript
// xxx.js
export default {
  data: {
    array: [
      {id: 1, name: 'jack', age: 18}, 
      {id: 2, name: 'tony', age: 18},
    ],
  },
}
```
tid属性主要用来加速for循环的重渲染，旨在列表中的数据有变更时，提高重新渲染的效率。tid属性是用来指定数组中每个元素的唯一标识，如果未指定，数组中每个元素的索引为该元素的唯一id。例如上述tid="id"表示数组中的每个元素的id属性为该元素的唯一标识。for循环支持的写法如下：
+ for="array"：其中array为数组对象，array的元素变量默认为$item。
+ for="v in array"：其中v为自定义的元素变量，元素索引默认为$idx。
+ for="(i, v) in array"：其中元素索引为i，元素变量为v，遍历数组对象array。

> 说明：  
> + 数组中的每个元素必须存在tid指定的数据属性，否则运行时可能会导致异常。
> + 数组中被tid指定的属性要保证唯一性，如果不是则会造成性能损耗。比如，示例中只有id和name可以作为tid字段，因为它们属于唯一字段。
> + tid不支持表达式。

# 条件渲染
条件渲染分为2种：if/elif/else和show。两种写法的区别在于：第一种写法里if为false时，组件不会在vdom中构建，也不会渲染，而第二种写法里show为false时虽然也不渲染，但会在vdom中构建；  

另外，当使用if/elif/else写法时，节点必须是兄弟节点，否则编译无法通过。实例如下：
```
<!-- xxx.hml -->
<div>
  <text if="{{show}}"> Hello-TV </text>
  <text elif="{{display}}"> Hello-Wearable </text>
  <text else> Hello-World </text>
</div>
```
```javascript
// xxx.js
export default {
  data: {
    show: false,
    display: true,
  },
}
```
优化渲染优化：show方法。当show为真时，节点正常渲染；当为假时，仅仅设置display样式为none。
```
<!-- xxx.hml -->
<text show="{{visible}}"> Hello World </text>
```
```javascript
// xxx.js
export default {
  data: {
    visible: false,
  },
}
```
> 说明：禁止在同一个元素上同时设置for和if属性。
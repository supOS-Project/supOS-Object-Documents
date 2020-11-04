# BaseSelector使用说明

### 一、概述

本文档讲述新下拉框的用法，如你在此基础上定制新属性栏颜色选择组件，欢迎补充该文档。

### 二、BaseSelector

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--  
config|是|下拉框配置|object| --
value|是|传入值为object,{value:'xxx',disabledKey:['xxx'],value为当前选中值对应config options中的key值,disabledKey表示当前被禁用的选项}|object|--
preSubmit|是|设置值方法|function(value)|--
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
options|否|下拉选项配置| array[]，[{value: object{}&#124;ReactNode,key:String&#124;Number, disabled: boolean，style: Object }]| --
className|否|自定义样式名，最外层容器类名|string| ''
prefix|否|前缀文字|string| ''
showArrow|否|是否显示下拉箭头|boolean|true
placeholder|否|提示文字|string|''
styleless|否|弱化样式，不会显示边框,减弱交互效果|boolean|false

#### 3、Demo

##### 在其他组件中引用

```javascript
<BaseSelector
  value={(string|object)}
  preSubmit={function}
  formatMessage={formatMessage}
  config={
    options: Array,
    className: String,
    prefix: Boolean,
    showArrow: Boolean,
    placeholder: Object,
    styleless: Boolean
  }
/>
```

##### 通过config配置使用, 组件内需要实现get set方法

```javascript
{
  configs: [
    {
      id: 'CustomID',
      component: 'BaseSelector',
      options: Array,
      className: String,
      prefix: Boolean,
      showArrow: Boolean,
      placeholder: Object,
      styleless: Boolean
      }
  ]
}
```

```javascript
class Component {
  getCustomID() {
    <!-- other code -->
    <!-- 根据判断条件禁用下拉选项 -->
    if(isDisabelBySomething) {
      return {
        value:'xxx',
        disabledKey:['xxx','xxx']
      }
    }else {
      return 'xxx'
    }
  }
  setCustomID(value) {
    <!-- other code -->
    this.setConfig()
  }
}
```

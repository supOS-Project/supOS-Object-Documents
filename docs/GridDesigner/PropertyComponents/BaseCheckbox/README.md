# BaseCheckbox使用说明

### 一、概述

本文档讲述新基础选择框的用法，如你在此基础上定制新属性栏颜色选择组件，欢迎补充该文档。

### 二、BaseCheckbox

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--  
config|是|下拉框配置|object| --
value|是|传入值为object,{value:Boolean&#124;Array[String],disabledKey:Array[String],config中的options如果为Object, 当作switch开关使用, checked值为Bollean,表示当前开关状态，disabledKey无效。如果options为Array,value为Array包含选中的value值，对应options配置中的value,disabled可用表示当前被禁用的选项}|null|--
preSubmit|是|设置值方法|function(value)|--
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
options|否|下拉选项配置,value多选框标识（等同于key或id 与antd风格保持一致）label标签名|object{}&#124;array[]，[{ value:String&#124;Number, label: Object{}, disabled: boolean }]| --
orderReverse|否|反转排列顺序，默认label在前，选择框在后，**在options[Object]配置中使用**|Boolean| flase
justifyOrder|否|对其方式 left&#124;right&#124;center&#124;around&#124;between,效果与flex布局相同，**在options[Object]配置中使用**|string| left
span|否|options为数组时每项所占份数, **在options[Array]配置中使用**|Number|6

#### 3、Demo

##### 在其他组件中引用

```javascript
<BaseCheckbox
  value={object}
  preSubmit={function}
  formatMessage={formatMessage}
  config={
    options: Object|Array
  }
/>
```

##### 通过config配置使用, 组件内需要实现get set方法

```javascript
{
  configs: [
    {
      id: 'CustomID',
      component: 'BaseCheckbox',
      options: Object|Array
    }
  ]
}
```

```javascript
class Component {
  getCustomID() {
    <!-- other code -->
    <!-- 根据判断条件禁用选中状态 -->
      return {
        value:String|Number,
        disabledKey:[String|Number]
      }
  }
  setCustomID(value) {
    <!-- other code -->
    this.setConfig()
  }
}
```

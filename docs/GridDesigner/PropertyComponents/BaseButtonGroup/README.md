# BaseButtonGroup使用说明

### 一、概述

本文档讲述新按钮组用法，如你在此基础上定制新属性栏颜色选择组件，欢迎补充该文档。

### 二、BaseButtonGroup

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--  
config|是|参数配置|object| --
value|是|传入值为object,value表示当前key值 {value:String}|null|--
preSubmit|是|设置值方法|function(value)|--
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
options|否|颜色配置，value正常状态显示，activeValue active状态显示,activeStyle 文字类的active样式| [{ key:String&#124;Number, value: Object{}&#124;ReactNode{},activevalue:Object{}&#124;ReactNode{},activeStyle:Object }]| --

#### 3、Demo

##### 在其他组件中引用

```javascript
<BaseButtonGroup
  value={object}
  preSubmit={function}
  formatMessage={formatMessage}
  config={
    <!-- ColorPicker config -->
    options: Array
  }
/>
```

##### 通过config配置使用, 组件内需要实现get set方法

```javascript
{
  configs: [
    {
      id: 'CustomID',
      component: 'BaseButtonGroup',
      <!-- ColorPicker config -->
      options: Array
    }
  ]
}
```

```javascript
class Component {
  getCustomID() {
    <!-- other code -->
      return {
        value: String
      }
  }
  setCustomID(value) {
    <!-- other code -->
    this.setConfig()
  }
}
```

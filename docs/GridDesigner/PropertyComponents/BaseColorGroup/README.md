# BaseColorGroup使用说明

### 一、概述

本文档讲述新颜色选择器组的用法，如你在此基础上定制新属性栏颜色选择组件，欢迎补充该文档。

### 二、BaseColorGroup

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--  
config|是|参数配置|object| --
value|是|传入值为object,{key:String,label:Object}|null|--
preSubmit|是|设置值方法|function(value)|--
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
options|否|颜色配置|[{ key:String&#124;Number, label: Object{},colorType:String}]| --
colorType&#124;showLatestColor&#124;showDeg|否|与颜色选择器配置相同，**可以在options中配置，会覆盖外层配置**|String&#124;Boolean| flase

#### 3、Demo

##### 在其他组件中引用

```javascript
<BaseColorGroup
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
      component: 'BaseColorGroup',
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
        [key1]: {
          color: String
        },
        [key2]: {
          color: String
        }
      }
  }
  setCustomID(value) {
    <!-- other code -->
    this.setConfig()
  }
}
```

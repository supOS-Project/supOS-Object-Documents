# BaseInputNumberNew使用说明

### 一、概述

    本文档讲述新数字输入框的用法，如你在此基础上定制新数字输入框组件，欢迎补充该文档。

### 二、BaseInputNumberNew

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|组件配置|object|-
value|否|值|object|-
preSubmit|是|回调方法|function(value)|-

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
type|否|[数字类型](/docs/CommonIntro/formatter#number)|string|naturalInteger
min|否|最小值|number|-Infinity
max|否|最大值|number|Infinity
step|否|步进|number|1
prefix|否|前缀|object|-
suffix|否|后缀|object|-
showBorder|否|显示边框|boolean|true
allowEmpty|否|允许空值|boolean|false

#### 3、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

![BaseInputNumber_1](./images/1.png 'BaseInputNumber_1')
```javascript
{
  configs: [
    {
      id: 'LegendWidth',
      component: 'BaseInputNumberNew',
      type: 'naturalInteger',
      min: 0,
      prefix: Messages.size
    }
  ]
}
```

![BaseInputNumber_2](./images/2.png 'BaseInputNumber_2')
```javascript
{
  configs: [
    {
      id: 'LegendWidth',
      component: 'BaseInputNumberNew',
      type: 'naturalInteger',
      min: 0,
      suffix: Messages.size
    }
  ]
}
```

![BaseInputNumber_3](./images/3.png 'BaseInputNumber_3')
```javascript
{
  configs: [
    {
      id: 'LegendWidth',
      component: 'BaseInputNumberNew',
      type: 'naturalInteger',
      min: 0,
      prefix: Messages.size,
      suffix: Messages.pixel
    }
  ]
}
```
# BaseRange使用说明

### 一、概述

    本文档讲述新区间组件的用法，如你在此基础上定制新区间组件，欢迎补充该文档。

### 二、BaseRange

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
allowEmpty|否|允许空值|boolean|false
unit|否|单位|string|''

#### 3、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

![BaseRange_1](./images/1.png 'BaseRange_1')
```javascript
{
  configs: [
    {
      id: 'Angle',
      component: 'BaseRange',
      isCustom: 'multi-part',
      type: 'integer',
      prefix: commonMessage.angle,
      min: -90,
      max: 90,
      unit: '°'
    }
  ]
}
```
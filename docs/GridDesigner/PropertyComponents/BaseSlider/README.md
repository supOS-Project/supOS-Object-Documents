# BaseSlider 使用说明

### 一、概述

    本文档讲述新BaseSlider控件的用法，如你在此基础上定制BaseSlider控件，欢迎补充该文档。

### 二、config组件  无

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|滑动项配置|object|
value|否| 滑动进度 | number|-
preSubmit|是|设置滑动进度的值|function(value)|-

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
min|否| 最小值 |number| 1
max|否| 最大值 |number| 100
title|否| 进度条标题 |string| ''

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'slider',
      component: 'BaseSlider',
      config: {
        min: 1,
        max: 20,
        title: '透明度'
      }
    }
  ]
}
```
 
### 三、复用组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|滑动项配置|object|
value|否| 滑动进度 | number|-
preSubmit|是|设置滑动进度的值|function(value)|-


#### 2、Demo

```javascript
<BaseSlider
  config={{
    min: 1,
    max: 20,
    title: '透明度'
  }}
  preSubmit={preSubmit}
/>
```
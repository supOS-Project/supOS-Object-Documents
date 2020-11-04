# BaseLabel 使用说明

### 一、概述

    本文档讲述新BaseLabel控件的用法，如你在此基础上定制BaseLabel控件，欢迎补充该文档。

### 二、config组件  无

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|label配置|object|
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
title|否| 文案 | string | ''
color|否| 颜色 |string| '#1f292f'
fontSize|否| 字号 |number| 12
marginType|否| full: 左边无间距, margin: 左边有边距 |string| ''


##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'BaseLabel',
      component: 'BaseLabel',
      isUI: true,
      title: '背景'
    }
  ]
}
```
 
### 三、复用组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|label配置|object|
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
title|否| 文案 | string | ''
color|否| 颜色 |string| '#1f292f'
fontSize|否| 字号 |number| 12
marginType|否| full: 左边无间距, margin: 左边有边距 |string| ''

#### 2、Demo

```javascript
<BaseSlider
  config={{
    title: '背景'
  }}
  formatMessage={formatMessage}
/>
```
# BaseText使用说明

### 一、概述

    本文档讲述新BaseText控件的用法，如你在此基础上定制BaseText控件，欢迎补充该文档。

####  type_base
![type_base](./images/type_base.png 'type_base')
<br/>
####  type_align_color
![type_align_color](./images/type_align_color.png 'type_align_color')
<br/>
####  type_align_style
![type_align_style](./images/type_align_style.png 'type_align_style')
<br/>
####  type_align_style_color
![type_align_style_color](./images/type_align_style_color.png 'type_align_style_color')
<br/>
####  type_rotate_style
![type_rotate_style](./images/type_rotate_style.png 'type_rotate_style')
<br/>
####  type_rotate_style_color
![type_rotate_style_color](./images/type_rotate_style_color.png 'type_rotate_style_color')

### 二、config组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|字体配置|object|
value|否|字体参数|object|-
preSubmit|是|设置字体的方法|function(value)|-
formatMessage|是|国际化|function|--

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
type|否| 四种类型: 'type_base', 'type_align_color', 'type_align_style', 'type_align_style_color'， 'type_rotate_style', 'type_rotate_style_color' |string| 'type_base'

#### 3、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'BaseText',
      component: 'BaseText',
      type: 'type_base'
    }
  ]
}
```

### 三、复用组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|字体配置|object|
value|否|字体参数|object|-
preSubmit|是|设置字体的方法|function(value)|-
formatMessage|是|国际化|function|--


#### 2、Demo

```javascript
<BaseButton
  config={ {
      type: 'type_base'
    }}
  preSubmit={preSubmit}
  formatMessage={formatMessage}
/>
```
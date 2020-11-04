# BaseButton使用说明

### 一、概述

    本文档讲述新Button控件的用法，如你在此基础上定制Button控件，欢迎补充该文档。



### 二、config组件  无

 
### 三、复用组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
iconType|否| 新增: 'add' 自定义: 'custom' |string|-
iconDom|否|dom节点|dom节点|-
size|否|按钮大小: 'small', 'large'|string| large
value|否|值|按钮的文案|''| ''
width|否|按钮的宽度|string| 100%
preSubmit|否|按钮的点击事件|fn| () => {}

#### 2、Demo

```javascript
<BaseButton
  config={{
      size: 'large',
      text: '按钮'
    }}
  preSubmit={preSubmit}
/>
```
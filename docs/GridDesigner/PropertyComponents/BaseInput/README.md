# BaseInput使用说明

### 一、概述

    本文档讲述新Input控件的用法，如你在此基础上定制Input控件，欢迎补充该文档。

![BaseInput_1](./images/1.png 'BaseInput_1')
<br/>
![BaseInput_2](./images/2.png 'BaseInput_2')
<br/>
![BaseInput_3](./images/3.png 'BaseInput_3')

### 二、config组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
prefix|否|在输入框前添加标签,若传入字符串,直接显示字符串值|object/string|-
suffix|否|在输入框上添加后缀,若传入字符串,直接显示字符串值|object/string|-
placeholder|否|输入框提示|string|-
value|否|值|以对象格式传入:{value:xxx}|Object|-

#### 2、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'MainTitleText',
      component: 'BaseInputNew',
      isCustom: 'multi-part',
      prefix: commonMessage.mainTile,
      suffix: commonMessage.unit,
      placeholder: commonMessage.pleaseEnterTitle
    }
  ]
}
```

### 三、复用组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
preSubmit|是|设置输入框的值,以对象格式返回obj:{value:xxx}|function(obj)|-
formatMessage|是|翻译|function|-
prefix|否|在输入框前添加标签,若传入字符串,直接显示字符串值|object/string|-
suffix|否|在输入框上添加后缀,若传入字符串,直接显示字符串值|object/string|-
placeholder|否|输入框提示|string|-
value|否|值|以对象格式传入:{value:xxx}|Object|-

#### 2、Demo

```javascript
<BaseInput
  formatMessage={formatMessage}
  value={{ value: '主标题' }}
  config={{
    prefix: commonMessage.mainTile,
    suffix: commonMessage.unit,
    placeholder: commonMessage.pleaseEnterTitle
  }}
  preSubmit={preSubmit}
/>
```
# BaseTextArea使用说明

### 一、概述

    本文档讲述新文本输入框的用法，如你在此基础上定制新文本输入框组件，欢迎补充该文档。

### 二、BaseTextArea

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
value|否|值|object|-
rows|否|输入框所占行数|number|6

#### 2、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'CreditsText',
      isCustom: 'multi-part',
      component: 'BaseTextArea',
      placeholder: commonMessage.pleaseEnterCreditsInfo
    }
  ]
}
```
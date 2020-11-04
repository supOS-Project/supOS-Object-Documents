# BaseRadio使用说明

### 一、概述

    本文档讲述新Radio控件的用法，如你在此基础上定制Radio控件，欢迎补充该文档。

  ![BaseRadio](./images/1.png 'BaseRadio')

### 二、config组件

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
options|否|以配置形式设置子元素options:[{label: commonMessage.second, value: 'second', disabled: true }]|array|[]
value|否|值,以对象格式传入:{value:xxx}|Object|-

#### 2、Demo

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'MainTitleText',
      component: 'BaseRadio',
      isCustom: 'multi-part',
      options:{options}
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
options|否|以配置形式设置子元素options:[{label: commonMessage.second, value: 'second', disabled: true }]|array|[]
config|否|Input配置|object|
value|否|值|以对象格式传入:{value:xxx}|Object|-

#### 2、Demo

```javascript
<BaseRadio
  formatMessage={formatMessage}
  value={{ value: '1' }}
  preSubmit={preSubmit}
  options={options}
/>
```
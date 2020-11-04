# ColorPicker使用说明

### 一、概述

    本文档讲述新颜色选择器的用法，如你在此基础上定制新属性栏颜色选择组件，欢迎补充该文档。

### 二、ColorPickerNew

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|颜色选择器配置|object|
value|否|颜色|object|-
preSubmit|是|设置颜色方法|function(value)|-

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
colorType|否|颜色选择器类型，color、gradient分别对应单色和渐变|string|color
defaultValue|否|默认颜色，根据colorType不同，对应string或object|string\|Object|-
showLatestColor|否|显示最近颜色|boolean|false
popupContainerQuery|否|显示颜色选择器弹框的父容器选择器|string|#drawWrapContainer
showDeg|否|显示渐变角度，colorType为gradient时生效|boolean|false

#### 3、value(渐变)

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
from|否|渐变起始颜色|string|#FFFFFF
to|否|渐变结束颜色|string|#000000
deg|否|渐变角度|number|0

#### 4、Demo

##### 作为组件使用

```javascript
<ColorPickerNew
  config={{ colorType: 'color', showLatestColor: true }}
  value={{ color: '#FFFFFF' }}
  preSubmit={preSubmit}
/>
<ColorPickerNew
  config={{ colorType: 'gradient', showLatestColor: true, showDeg: true }}
  value={{
    from: '#FFFFFF',
    to: '#000000',
    deg: 0
  }}
  preSubmit={preSubmit}
/>
```

若默认的展示节点不符使用场景UI要求，可以定制内容，方法如下：

```javascript
<ColorPickerNew
  config={{ colorType: 'color', showLatestColor: true }}
  value={value}
  preSubmit={preSubmit}
>
  <span
    className={styles.colorSpan}
    style={{ background: value }}
  />
</ColorPickerNew>
```

##### 作为组件config使用单色模式，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'color',
      displayName: 'color',
      component: 'ColorPickerNew',
      colorType: 'color',
      showLatestColor: true,
      popupContainerQuery: '#drawWrapContainer'
    }
  ]
}
```

##### 作为组件config使用渐变模式，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'gradient',
      displayName: 'gradient',
      component: 'ColorPickerNew',
      colorType: 'gradient',
      showLatestColor: true,
      popupContainerQuery: '#drawWrapContainer'
    }
  ]
}
```

### 三、ColorPickerWithLabel

![ColorPickerWithLabel_0](./images/ColorPickerWithLabel_0.png 'ColorPickerWithLabel_0')
<br/>
![ColorPickerWithLabel_1](./images/ColorPickerWithLabel_1.png 'ColorPickerWithLabel_1')
<br/>
![ColorPickerWithLabel_2](./images/ColorPickerWithLabel_2.png 'ColorPickerWithLabel_2')

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|带label的单色颜色选择器配置|object|
value|否|颜色|string|#FFFFFF
preSubmit|是|设置颜色方法|function(value)|

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
label|否|显示的label文字|string|
labelMode|否|显示的label样式|string|
labelWidth|否|显示的label宽度|Number|
customStyles|否|定义最外层div样式|objectstring|color
colorType|否|颜色选择器类型，color、gradient分别对应单色和渐变|string|color
showLatestColor|否|显示最近颜色|boolean|false

#### 3、Demo

##### 作为组件使用

```javascript
<ColorPickerWithLabel
  config={{ label: '颜色' }}
  value={{ color: '#FFFFFF' }}
  preSubmit={preSubmit}
/>
<ColorPickerWithLabel
  config={{ label: '颜色', colorType='gradient' }}
  value={{
    from: '#CCCCCC',
    to: '#888888',
    deg: 90
  }}
  preSubmit={preSubmit}
/>
```

##### 作为组件config使用单色模式，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'color',
      displayName: 'color',
      component: 'ColorPickerWithLabel',
      label: '颜色',
      labelWidth: 40
    }
  ]
}
```

##### 作为组件config使用渐变模式，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'gradient',
      displayName: 'gradient',
      component: 'ColorPickerNew',
      colorType: 'gradient',
      config: {
        label: '数据颜色'
      }
    }
  ]
}
```

### 四、BackgroundNew

![BackgroundNew_0](./images/BackgroundNew_0.png 'BackgroundNew_0')
<br/>
![BackgroundNew_1](./images/BackgroundNew_1.png 'BackgroundNew_1')
<br/>
![BackgroundNew_2](./images/BackgroundNew_2.png 'BackgroundNew_2')

#### 1、API

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
config|否|带label的单色颜色选择器配置|object|
value|否|颜色|object|
preSubmit|是|设置颜色方法|function(value)|

#### 2、config

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
showLatestColor|否|显示最近颜色|boolean|false
showDeg|否|显示渐变颜色|boolean|true

#### 3、value

属性|是否必填|说明|类型|默认值
:--|:--:|:--|:--|:--
color|否|单色颜色|string|#FFFFFF
from|否|渐变起始颜色|string|#FFFFFF
to|否|渐变结束颜色|string|#000000
deg|否|渐变角度|number|0
colorType|否|颜色选择器类型，color、gradient分别对应单色和渐变|string|color

#### 4、Demo

##### 作为组件使用

```javascript
<BackgroundNew
  value={
    color: '#AACCAA',
    from: '#CCCCCC',
    to: '#888888',
    deg: 90,
    colorType: 'gradient'
  }
  preSubmit={preSubmit}
/>
```

##### 作为组件config使用，组件内需要有相应的get、set方法

```javascript
{
  configs: [
    {
      id: 'background',
      displayName: 'background',
      component: 'BackgroundNew',
      value: {
        color: '#AACCAA',
        from: '#CCCCCC',
        to: '#888888',
        deg: 90,
        colorType: 'gradient'
      }
    }
  ]
}
```

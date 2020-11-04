**1\. 图表库公共属性配置**

**1.1\. 数据源以及其他零散配置：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|
|-----|--------|----|--------|--------|----------|
| 数据源  || array   | \[\]  | setDataSource         | getDataSource         |
| 时间格式 | 时间格式不做转换 | boolean | false | setInitFormat         | getInitFormat         |
| 组件ID || string  ||      | getCtrlId|

**1.2\. 标题：**

**1.2.1\. 主标题：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法| 脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 显示   | 是否显示标题   | boolean  | true  | setTitleVisibility    | getTitleVisibility    | 允许|
| 主标题  || string  || setTitle | getTitle |允许|
| 文本样式 || object  | \{ fontSize = 16, fontFamily = '微软雅黑', color = '\#333333', fontWeight, fontStyle \} | setChartTitle         | getChartTitle         | 允许|
| 对齐方式 || string  | 'center'('center'\|'left'\|'right')| setTitleAlign         | getTitleAlign         | 允许|

**1.2.2\. 副标题：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|  脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 显示   | 是否显示副标题  | boolean  | false | setSubtitleVisibility | getSubtitleVisibility | 允许|
| 副标题  || string  || setSubtitle | getSubtitle | 允许|
| 文本样式 || object  | \{ fontSize = 12, fontFamily = '微软雅黑', color = '\#333333', fontWeight, fontStyle \} | setSubChartTitle      | getSubChartTitle      | 允许|
| 对齐方式 || string  | 'center'('center'\|'left'\|'right') | setSubTitleAlign      | getSubTitleAlign      | 允许|


**1.3\. 基础：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|  脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 边框       |      | object  | \{ borderWidth:0, borderColor:'\#ddd', borderRadius:0 \}  | setBaseBorderStyle     | getBaseBorderStyle     | 允许|
| 边距（上右下左） |      | object  | \{ spacingTop:10, spacingBottom:10, spacingLeft:10, spacingRight:10 \} | setBaseBoxSpacing      | getBaseBoxSpacing      | 允许|
| 背景颜色     |      | string  | 'rgba\(0, 0, 0, 0\)'  | setBackgroundColor     | getBackgroundColor     | 允许|
| 图表颜色     |      | string  | 'rgba\(0, 0, 0, 0\)'  | setPlotBackgroundColor | getPlotBackgroundColor | 允许|
| 定位层级     |      | number  | 100| setChartZIndex         | getChartZIndex         |
| 全屏       |      | boolean | false  | getFullscreenIcon      | setFullscreenIcon      |

**1.4\. 图例：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|  脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 显示   |      | boolean | false                                                                         | setLegendEnabled             | getLegendEnabled             | 允许|
| 边框   |      | object  | \{ borderWidth:0, borderColor:'\#ddd', borderRadius:0 \}                      | setLegendBorderStyle         | getLegendBorderStyle         | 允许|
| 对齐方式 |      | string  | 'bottom\-center'                                                               | setLegendAlign               | getLegendAlign               | 允许|
| 布局方式 |      | string  | 'horizontal'                                                                  | setLegendLayout              | getLegendLayout              | 允许|
| 文本样式 |      | object  | \{ fontSize:16, fontFamily:'微软雅黑', color:'\#333333', fontWeight, fontStyle \} | setLegendText                | getLegendText                | 允许|
| 背景颜色 |      | string  | '\#fff'                                                                       | setLegendItemBackgroundColor | getLegendItemBackgroundColor | 允许|

**1.5\. 标签（仪表盘、速度仪除外）：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|  脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 显示标签   |      | boolean | false | setDataLabelsEnabled | getDataLabelsEnabled | 允许|
| 边框 |      | object | { borderWidth:0, borderColor:'#ddd', borderRadius:0 }   | setDataLabelsBorderStyle | getDataLabelsBorderStyle | 允许|
| 标签颜色 |      | string | '#000'   | setDataLabelsColor | getDataLabelsColor | 允许|
| 背景颜色 |      | string | '#ddd   | setDataLabelsBackgroundColor | getDataLabelsBackgroundColor | 允许|
| 对齐方式 |      | string | 'center   | setDataLabelsAlign | getDataLabelsAlign | 允许|
| 数据     |      | object | {formatType:'0',dataDecimals:2}   | setDataLabelsDateFormat | getDataLabelsDateFormat |     
| 字体大小 |      | number | 12   | setDataLabelsFontSize | getDataLabelsFontSize | 允许|
| 内间距   |      | number | 0   | setDataLabelsPadding | getDataLabelsPadding | 允许|

**1.6\. 备注：**
| 属性| 描述信息| 类型| 默认值 | 设值方法 | 取值方法|  脚本使用 |
|-----|--------|----|--------|--------|----------|-----|
| 显示备注   |      | boolean | false | setCreditsEnabled | getCreditsEnabled | 允许|
| 备注信息   |      | string | undefined | setCreditsText | getCreditsText | 允许|
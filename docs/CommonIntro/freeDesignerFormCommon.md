## **自由布局-表单库统一属性配置项**

| 属性名   | 控件名                  | 类型    | 默认值   | 设值方法                             | 取值方法                   | 适用控件                                                      |
| :------- | :---------------------- | :------ | -------- | ------------------------------------ | -------------------------- | ------------------------------------------------------------- |
| 标题     | 输入框左边的Label       | string  | 标题     | setLabelContent\(string\)            | getLabelContent\(\)        | 输入框/下拉框/ 级联选择/单选框/复选框/日期/ 搜索框            |
| 标题宽度 | 输入框左边的Label的宽度 | number  | 70       | setTitleWidth\(string\)              | getTitleWidth\(\)          | 输入框/下拉框/ 级联选择/单选框/复选框/日期/ 搜索框            |
| 标题大小 | 输入框左边的Label的大小 | number  | 14       | setTitleFontSize\(string\)           | getTitleFontSize\(\)       | 同上                                                          |
| 标题颜色 | 输入框左边的Label的颜色 | string  | #000000  | setTitleColor\(string\)              | getTitleColor\(\)          | 同上                                                          |
| 标题字体 | 输入框左边的Label的字体 | string  | 默认字体 | setTitleFontFamily\(string\)         | getTitleFontFamily\(\)     | 同上                                                          |
| 定位层级 | 设置定位层级            | number  | 0        | setZIndex(number)                    | getZIndex()                | 除隐藏域之外所有                                              |
| 组件宽度 | 设置定位模式            | number  | -        | setWidth(number)                     | getWidth()                 | 除隐藏域之外所有                                              |
| 组件高度 | 设置定位层级            | number  | -        | setHeight(number)                    | getHeight()                | 除隐藏域之外所有                                              |
| 只读     | 设置定位层级            | number  | false    | setReadOnly(number)                  | getReadOnly()              | 输入框/下拉框/ 级联选择/单选框/复选框/日期/                   |
| 显示加载 | 设置定位层级            | boolean | false    | setIsShowLoading(boolean)            | getIsShowLoading()         | 除隐藏域之外所有                                              |
| 上固定   | 绝对定位:top            | boolean | false    | setPosition('topEnable', boolean)    | getPosition().topEnable    | 标签/输入框/下拉框/级联选择/单选框/复选框/日期/按钮/树状/表格 |
| 下固定   | 绝对定位:bottom         | boolean | false    | setPosition('bottomEnable', boolean) | getPosition().bottomEnable | 同上                                                          |
| 左固定   | 绝对定位:left           | boolean | false    | setPosition('leftEnable', boolean)   | getPosition().leftEnable   | 同上                                                          |
| 右固定   | 绝对定位:right          | boolean | false    | setPosition('rightEnable', boolean)  | getPosition().rightEnable  | 同上                                                          |

## **自由布局-表单库默认宽高**

| 控件名   | 默认宽度 | 默认高度 |
| :------- | :------- | :------- |
| 线条     | 168      | 32       |
| 标签     | 168      | 32       |
| 隐藏域   | 无       | 无       |
| 输入框   | 348      | 32       |
| 下拉框   | 348      | 32       |
| 级联选择 | 348      | 32       |
| 单选框   | 348      | 32       |
| 复选框   | 348      | 32       |
| 日期     | 348      | 32       |
| 按钮     | 120      | 36       |
| 树状     | 200      | 290      |
| 单列表   | 180      | 333      |
| 表格     | 586      | 300      |
| 图片     | 200      | 200      |
| 标签页   | 300      | 300      |
| 上传     | 120      | 120      |
| 面包屑   | 400      | 100      |
| 搜索     | 348      | 32       |



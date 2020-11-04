## **1\. 可编程控件本地环境操作手册**


**依赖**

- node环境
- vscode插件： supos-vscode-editor
- npm包：yo generator-supos-cli

**开发步骤**

1.node环境安装；

 >[node环境配置](https://www.cnblogs.com/liuqiyun/p/8133904.html)

2.全局安装`yo`、`generator-supos-cli`;

```bash
npm install -g yo generator-supos-cli
```

3.yo启动；

```bash
yo
```
    选择Supos Cli
    输入项目名称（任意）
    输入需要发布的ip地址（如10.30.52.25:8080）或域名（www.xxxx.com）
    输入supos的账号
    输入supod账号对应的密码
    选择要将代码上传到哪个APP下面
    初始化（建议Y）


4.安装vscode插件：`supos-vscode-editor`；

5.vscode插件输入命令`sync` (快捷键ctrl+shift+p打开输入命令窗口)，注：SVE Sync;

6.react语法开发组件功能，组件必须定义在`src/controls`目录下，文件夹名称必须与组件名称一致，入口文件必须是index.js；

7.上传前先执行终端命令`npm run build:libs`（快捷键ctrl+shift+`,打开一个新终端）;

8.vscode插件输入命令`publish`(快捷键ctrl+shift+p打开输入命令窗口)，注：SVE Publish，然后输入需要发布上去的文件夹名称

（`controls`目录下的文件夹名称），发布到supos app静态资源目录，;

9.app设计页面，拖动一个`可编程组件`到画布，控件名称设置成步骤6开发的react组件文件夹名称;

10.示例;

```javascript
// src/controls/MyComponent/index.js
import React, { Component } from 'react';
import echarts from 'echarts';

export default class MyComponent extends Component {
    componentDidMount() {
        var myChart = echarts.init(this.el);
        var app = {};
        var option = null;
        var xAxisData = [];
        var data1 = [];
        var data2 = [];
        for (var i = 0; i < 100; i++) {
            xAxisData.push('类目' + i);
            data1.push((Math.sin(i / 5) * (i / 5 - 10) + i / 6) * 5);
            data2.push((Math.cos(i / 5) * (i / 5 - 10) + i / 6) * 5);
        }

        option = {
            title: {
                text: '柱状图动画延迟'
            },
            legend: {
                data: ['bar', 'bar2'],
                align: 'left'
            },
            toolbox: {
                // y: 'bottom',
                feature: {
                    magicType: {
                        type: ['stack', 'tiled']
                    },
                    dataView: {},
                    saveAsImage: {
                        pixelRatio: 2
                    }
                }
            },
            tooltip: {},
            xAxis: {
                data: xAxisData,
                silent: false,
                splitLine: {
                    show: false
                }
            },
            yAxis: {
            },
            series: [{
                name: 'bar',
                type: 'bar',
                data: data1,
                animationDelay: function (idx) {
                    return idx * 10;
                }
            }, {
                name: 'bar2',
                type: 'bar',
                data: data2,
                animationDelay: function (idx) {
                    return idx * 10 + 100;
                }
            }],
            animationEasing: 'elasticOut',
            animationDelayUpdate: function (idx) {
                return idx * 5;
            }
        };
        if (option && typeof option === "object") {
            myChart.setOption(option, true);
        }
    }

    render() {
        return (
            <div style={{ width: "100%", height: "100%" }} ref={node => (this.el = node)}></div>
        )
    }
}

```

```javascript
// src/index.js文件引入react开发组件
import React from 'react';
import ReactDOM from 'react-dom';
import MyComponent from './controls/MyComponent';

const App = () => {
    return (
        <MyComponent />
    );
}

ReactDOM.render(<App />, document.getElementById('app'));
```

**组件属性步骤**

   两种实现方式，根据自己需求而定


  - 一种是可编程组件已支持的类型，暂有输入框和颜色拾色器(其他后期是否可用需要试用)；

 i. 在当前组件文件夹下新建一个index.json；

 ii. 发布到当前APP静态资源目录,同上述开发步骤第八条；

```javascript
// src/controls/MyComponent/index.json
[
  {
        "name": "text",
        "displayName": "名称",
        "inputType": "Input",
        "defaultValue": ""
    },
    {
        "name": "fontColor",
        "displayName": "颜色",
        "inputType": "ColorPicker",
        "defaultValue": ""
    },
]
```

- 另一种是由自己实现;

 i. 在当前组件文件夹下新建一个index.json(`controls`目录下的文件夹)；

 ii. 发布到当前APP静态资源目录,同上述开发步骤第八条；

```javascript
// src/controls/MyComponent/index.json
[
  {
    "name": "test",
    "displayName": "名称",
    "resource": "CustomProps.js",
    "defaultValue": ""
  }
]
```
 iii. 新建一个js文件，文件名称要与index.json中的resource字段对应的路径中的文件保持一致；

```javascrip
// CustomProps.js
import { Select } from "antd";
import React, { Component } from "react";

class CustomProp extends Component {
  handleChange = (value) => {
    this.props.edit(value);
  }

  render() {
    return (
      <div>
        <Select defaultValue="lucy" style={{ width: 120 }} onChange={this.handleChange}>
          <Option value="jack">Jack</Option>
          <Option value="lucy">Lucy</Option>
          <Option value="disabled" disabled>
            Disabled
          </Option>
          <Option value="Yiminghe">yiminghe</Option>
       </Select>
      </div>
    )
  }
}

export default CustomProp;
```
2.在当前APP的静态资源管理中找到想要配置属性的组件文件夹下创建一个props文件夹，上传新建的js文件
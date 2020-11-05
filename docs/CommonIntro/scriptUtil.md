## **ScriptUtil 用户信息**
| Api                  | 描述                                | 入参                | 出参   | 自由布局 | 网格布局 |
| -------------------- | ----------------------------------- | ------------------- | ------ | -------- | -------- |
| domain               | 变量，当前的domain                  |                     |        | 自由布局 | 网格布局 |
| getUserInfo()        | 获取用户信息                        | func                |        | 自由布局 | 网格布局 |
| getSessionUserInfo() | 从sessionStorage获取用户session信息 |                     | object | 自由布局 | 网格布局 |
| setUserInfo          | 设置用户显示信息                    | ctrlId, tip, endTip |        | 自由布局 | 网格布局 |
| setAuthority         | 退出登陆                            |                     |        | 自由布局 | 网格布局 |


#### **getUserInfo**
```
   scriptUtil.getUserInfo(function(res){
     // res 为当前用户的信息
     console.log('res', res)
   }); 
```

#### **getSessionUserInfo**
```
   var session = scriptUtil.getSessionUserInfo();
```

#### **setUserInfo**
```
   scriptUtil.setUserInfo(ctrlId, '欢迎', ',退出'); // 页面显示效果： 欢迎 XXX , 退出
```


#### **setAuthority**
```
   scriptUtil.setAuthority(); // 退出到登陆页面
```


## **ScriptUtil React组件操作**
| Api                 | 描述             | 入参                    | 出参          | 自由布局 | 网格布局 |
| ------------------- | ---------------- | ----------------------- | ------------- | -------- | -------- |
| registerReactDom    | 注册组件         | component, props        | 无            | 自由布局 |          |
| logoutReactDom      | 注销组件         | props                   | 无            | 自由布局 |          |
| getRegisterReactDom | 获取已注册的组件 | componentId             | component所有 | 自由布局 |          |
| handleReactDom      | 设置组件的方法   | ctrlId, value, funcName | 无            | 自由布局 |          |
| getFormData         | 设置组件的值     | [formIds]               | object        | 自由布局 |          |
| setFormData         | 获取组件的值     | object                  | 无            | 自由布局 |          |
| submitDefaultValue  | 提交组件联动值     | dom, value, tag        | 无            | 自由布局 |          |

#### **registerReactDom**
```
   scriptUtil.getRegisterReactDom('ctrlId'); 
```

#### **getFormData**
```
   // 批量获取数据
   scriptUtil.getFormData([formIds]); 
```

#### **setFormData**
``` 
   // 批量设置数据值 key为组件名称，value 为值
   scriptUtil.setFormData({
     key：value
   });
```

#### **submitDefaultValue**
``` 
   /**
 *
 * @param {*} dom ctrl组件对象
 * @param {*} value 默认提交初始值
 * @param {*} tag 是否默认提交查询，不填写按照当前方式，提交0为自动, 1为主动
 */
   var dom = scriptUtil.getRegisterReactDom('ctrlId'); 
   scriptUtil.submitDefaultValue(dom, value, '0');
```

## **ScriptUtil 通用工具**
| Api                 | 描述                                                                                | 入参                                     | 出参          | 自由布局 | 网格布局 |
| ------------------- | ----------------------------------------------------------------------------------- | ---------------------------------------- | ------------- | -------- | -------- |
| Alert()             | 弹窗 有确认和取消按钮                                                               | '', func                                 |               | 自由布局 |          |
| showMessage         | 展示meaasge信息， 参数可以参考antd                                                  | msg = '操作成功', type = 'success'       | 无            | 自由布局 | 网格布局 |
| moment              | 时间格式转换类 ，参考moment插件的处理方式 moment(val).format('YYYY-MM-DD HH:mm:ss') |                                          | 无            | 自由布局 | 网格布局 |
| isFunction()        | 判断是否为function                                                                  | any                                      | 无            | 自由布局 | 网格布局 |
| isEmptyObject()     | 判断是否为空对象                                                                    | any                                      | component所有 | 自由布局 | 网格布局 |
| timestampFormat     | 时间转换, 时间戳转格式                                                              | time, format: 'YYYY-MM-DD HH:mm:ss'      | 无            | 自由布局 | 网格布局 |
| timestampAntiFormat | 时间转换, 时间转时间戳                                                              | time                                     |               | 自由布局 | 网格布局 |
| valueCheck          | value 校验 是否必填 是否符合格式化需求                                              | value, type = 'none', isRequired = 'yes' |               | 自由布局 | 网格布局 |
| regRexGroup         | 正则表达式列表                                                                      | type                                     |               | 自由布局 | 网格布局 |
| getRequestUrl       | 获取url携带的参数                                                                   | 无                                       | object        | 自由布局 | 网格布局 |
| isVaild             | 用于表单提交时的校验                                                                | ctrlIds：[]                              | boolean       | 自由布局 |          |
| getTimeZone         | 获取时区                                                                            | 无                                       |               | 自由布局 | 网格布局 |
| JSONToExcelConvertor| 用于数据的导出（表格等）                                                          | {data = [], fileName, dataTitle = [], filter, extension }  |    | 自由布局 | 网格布局 |

#### **Alert**
```
   // message 是内容 回调方法为确定之后的回调
   scriptUtil.Alert('Message', function(){
     console.log('callback');
   })
```
#### **showMessage**
```
   // 参照antd message 可选类型： 'success' 'info' 'error' 'warning'
   scriptUtil.showMessage('Message', 'success');
```

#### **timestampFormat**
``` 
   scriptUtil.timestampFormat(1587109353040, 'YYYY-MM-DD HH:mm:ss');
```

#### **timestampAntiFormat**
``` 
    scriptUtil.timestampAntiFormat('2019-01-01 01:00:00');
```

#### **regRexGroup**
``` 
    // type类型 ： 'none' , 'mobilePhone',  'telephone', 'zipCode', 'idCard', 'number', 'email',  'ip' 返回不用的校验规则 
    var type = 'none';
    scriptUtil.regRexGroup('mobilePhone');

    // 自定义规则
    var type = '/\S/';
    scriptUtil.regRexGroup('mobilePhone');
```

#### **isVaild**
```
    scriptUtil.isVaild(['ctrlId']);
```

#### **JSONToExcelConvertor**
```javascript
// data 数据源 是一个数组
// dataTitle 表头文本
// dataKey 表格数据对应的字段， 顺序dataTitle对应
// fileName 文件名
// extension 扩展名， csv或者xls
scriptUtil.JSONToExcelConvertor({
  data: [
    {name: '小王' , age: '12', sex: '女'}
  ],
  dataTitle: ['姓名', '年纪', '性别'],
  dataKey: ['name', 'age', 'sex'],
  fileName: '文件',
  extension: 'xls'
})
```

## **ScriptUtil 窗口操作**
| Api              | 描述         | 入参                 | 出参          | 自由布局 | 网格布局 |
| ---------------- | ------------ | -------------------- | ------------- | -------- | -------- |
| closeCurrentPage | 关闭当前窗口 | component, props     | 无            | 自由布局 | 网格布局 |
| openPage         | 打开新的页面 | url，method, feature | 无            | 自由布局 | 网格布局 |
| openParentPage   | 打开父页面   | componentId          | component所有 | 自由布局 | 网格布局 |
| showModal        | 显示弹窗     | object               |               | 自由布局 |          |
| closeModal       | 关闭弹窗     | object               |               | 自由布局 |          |
| showLoading      | 展示loading  | object               |               | 自由布局 |          |
| closeLoading     | 关闭loading  | object               |               | 自由布局 |          |

#### **openPage**
```
    // 空页面
    scriptUtil.openPage('url', '_black');

    // 替换当前页面
    scriptUtil.openPage('url', '_self');

    //宽高配置的空页面
    scriptUtil.openPage('url', '_black'， true, {
      height: 400,
      width: 400
    });
```

#### **showModal**
```
    var pageId = 'XXX';
    scriptUtil.showModal({
      modalVisible,
      modalWidth,
      modalHeight,
      modalTitle,
      isIframe: true,
      pageId: pageId
    });
    
```
#### **showLoading**
```
    scriptUtil.showLoading({
      spinTip: '加载中...'
    });
```

## **ScriptUtil 封装接口调用**
| Api                 | 描述              | 入参        | 出参 | 自由布局 | 网格布局 |
| ------------------- | ----------------- | ----------- | ---- | -------- | -------- |
| addDataTable        | 新增DataTable数据 | object      | 无   | 自由布局 | 网格布局 |
| updateDataTable     | 编辑DataTable数据 | object      | 无   | 自由布局 | 网格布局 |
| delDataTable        | 删除DataTable数据 | object      | 无   | 自由布局 | 网格布局 |
| queryDataTable      | 查询DataTable数据 | object      | 无   | 自由布局 | 网格布局 |
| excuteScriptService | 描述              | 入参        | 出参 | 自由布局 | 网格布局 |
| request             | 请求方法          | url, object | 出参 | 自由布局 | 网格布局 |

#### **新增数据 - addDataTable**
```
 // 数据key 和 数据值
 var params = {
   key: 'value'
 };
 scriptUtil.addDataTable({
    dataSource: 'JXBasicInfo',  // dataTable 名称
    properties: [params],
  }, function(res){
    console.log('res', res);
  });
```

#### **更新数据 - updateDataTable**
```
 // 数据key 和 数据值
 var params = {
   key: 'value'
 };
 // dataTable 的主键
 var mainKey = {
   key: 'value'
 };
 scriptUtil.updateDataTable({
    dataSource: 'JXBasicInfo',  // dataTable 名称
    properties: [params],
    keys: mainKey
  }, function(res){
    console.log('res', res);
  });
```

#### **查询数据 - queryDataTable**
```
 scriptUtil.queryDataTable({
    dataSource: 'JXBasicInfo',  // dataTable 名称
    filters: {
      username:username,
      order: [{
               order:'id',
               sort:'desc'
             }]
    }
  }, function(res){
    console.log('res', res);
  });
```

#### **删除数据 - delInstance**
```
 // dataTable 的主键
 var mainKey = {
   key: 'value'
 };
 scriptUtil.queryDataTable({
    dataSource:'JXBasicInfo',
    properties: [mainKey]
  }, function(res){
    console.log('res', res);
  });
```

#### **对象实例-服务调用 - executeScriptService**
```
    scriptUtil.excuteScriptService({
       objName:"objName",  // 对象名称
       serviceName:"get_project",  // 服务名称 
       // 入参 
       params:{
         name:data.name
       },
       // 回调函数
       cb:function(function(res){
         console.log('res', res);
       }
       // 可自定义补充请求参数
    });
```

#### **自定义请求 - request**
```
    scriptUtil.request('url', {
      method: 'POST', // 'GET', 'PUT', 'DELETE',
      headers: {
          'X-Namespace': ''//命名空间，对象模板所在的命名空间
      },
      body: {
        // 入参
      }
    }).then(function(res){
     console.log('res', res);
    });
```
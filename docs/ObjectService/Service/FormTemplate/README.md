## **内置对象服务**

### **服务说明**

* [getDatatableDetails 查询表结构](/docs/ObjectService/Service/FormTemplate/getDatatableDetails)
* [AddDataTableEntry 新增一条数据](/docs/ObjectService/Service/FormTemplate/AddDataTableEntry)
* [AddDataTableEntries 新增多条数据](/docs/ObjectService/Service/FormTemplate/AddDataTableEntries)
* [GetDataTableEntries 查询数据](/docs/ObjectService/Service/FormTemplate/GetDataTableEntries)
* [UpdateDataTableEntry 更新数据](/docs/ObjectService/Service/FormTemplate/UpdateDataTableEntry)
* [DeleteDataTableEntries 删除数据](/docs/ObjectService/Service/FormTemplate/DeleteDataTableEntries)
* [getDataTableScript 查询数据脚本](/docs/ObjectService/Service/FormTemplate/getDataTableScript)

|别名|名称|命名空间|描述|输入|输出|
|:---|:---|:------|:---|:---|:---|
|getDatatableDetails|查询表结构|system|查询表结构|||
|AddDataTableEntry|新增一条数据|system|新增一条数据|params</br>参数格式：{"id":"1","name":"zhangsan"}||
|AddDataTableEntries|新增多条数据|system|新增多条数据|params</br>参数格式：{"list":[{"id":"1","name":"zhangsan"},{"id":"2","name":"lisi"}]}||
|GetDataTableEntries|查询数据|system|查询数据|distinct,fields,pageIndex,pageSize||
|UpdateDataTableEntry|更新数据|system|更新数据|updateData</br>更新的数据和条件，数据的格式：{'where':{条件},'update':{更新的参数}}||
|DeleteDataTableEntries|删除数据|system|删除数据|condition</br>参数格式：{"id":"1"}||
|getDataTableScript|查询数据脚本|system|查询数据脚本|inputs</br>传入参数（以map格式）||

### **执行表单模板服务(只能执行表单模板下的服务)**

> templates["namespace.template_alias"].executeService("namespace.service_alias", param); // namespace可以不传，但是如果存在同名服务会报错

### **在脚本中快捷调用系统内置服务**

> var result = me.AddDataTableEntry(param);         //调用AddDataTableEntry服务
>
> var result = me.AddDataTableEntries(param);       //调用AddDataTableEntries服务
>
> var result = me.GetDataTableEntries(param);       //调用GetDataTableEntries服务
>
> var result = me.UpdateDataTableEntry(param);      //调用UpdateDataTableEntry服务
>
> var result = me.DeleteDataTableEntries(param);    //调用DeleteDataTableEntries服务
>
> var result = me.getDataTableScript(param);        //调用getDataTableScript服务
>
> var result = me.getDatatableDetails(param);       //调用getDatatableDetails服务

### **控件交互事件调用 - request 方式**

#### **url获取方式**

- **/project/dam/supngin/api/dam/runtime/{命名空间}/template/{对象模板的别名}/service/system/{调用服务名称}**

#### **调用示例**

```JS
//拼接输入参数
var inputs = {};
inputs.deviceCode = scriptUtil.getFormData(["deviceCode"]).deviceCode;

scriptUtil.request('/project/dam/supngin/api/dam/runtime/liye_fdms/template/DeviceAssets/service/system/getDataTableScript',{
    method: 'POST',
    headers: {
        'X-Namespace': 'liye_fdms'
    },
    body: {
        'inputs': JSON.stringify(inputs)
    }
}).then(function(res){
    console.log('res', res);
});
```
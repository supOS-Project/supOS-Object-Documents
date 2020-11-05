## **getPropertyVQTValue**

### **功能**

对象实例下的实体模板中，查询某个对象实例中的单个属性的VQT值。

- **VQT**解析：
  - Value(属性值);
  - Quality(状态码);
  - Time(时间戳);

### **示例**

在实体模板对象「liye_fdms.DeviceTemplate」中查询实例对象「device001」的属性的VQT值。

![getPropertyVQTValue](../assets/img/getPropertyVQTValue-service.png "getPropertyVQTValue"){.img-fluid tag=1}

![getPropertyVQTValue-debug](../assets/img/getPropertyVQTValue-service-debug.png "getPropertyVQTValue-debug"){.img-fluid tag=1}


### **返回值**

```JSON
{
	"value": "type_0001",
	"tags": {
		"name": "/liye_fdms/DeviceTemplate/device001/liye_fdms/deviceTypeNo",
		"value": "type_0001",
		"status": "0",
		"timeStamp": 1604563721770
	}
}
```

### **自定义服务调用**

```JS
//获取实例对象
var instance = ObjectPool.get("device001"); //实例对象别名

//入参
var inputs = {
    propName:'deviceTypeNo', //proName:属性别名
};
//输出结果
var result = instance.executeService('getPropertyVQTValue',inputs);
result;
```
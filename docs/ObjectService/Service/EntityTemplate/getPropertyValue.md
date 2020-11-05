## **getPropertyValue**

### **功能**

对象实例下的实体模板中，查询某个对象实例中的单个属性的值。

### **示例**

在实体模板对象「liye_fdms.DeviceTemplate」中查询实例对象「device001」的属性值。

![getPropertyValue](../assets/img/getPropertyValue-service.png "getPropertyValue"){.img-fluid tag=1}

![getPropertyValue-debug](../assets/img/getPropertyValue-service-debug.png "getPropertyValue-debug"){.img-fluid tag=1}

### **自定义服务调用**

```JS
//获取实例对象
var instance = ObjectPool.get("device001"); //实例对象别名

//入参
var inputs = {
    propName:'deviceTypeNo', //proName:属性别名
};
//输出结果
var result = instance.executeService('getPropertyValue',inputs);
result;
```
## **setPropertyValue**

### **功能**

对象实例下的实体模板中，对某个对象实例中的单个属性进行赋值。

### **示例**

在实体模板对象「liye_fdms.DeviceTemplate」中设置实例对象「device001」设置其属性值。

![setPropertyValue](../assets/img/setPropertyValue-service.png "setPropertyValue"){.img-fluid tag=1}

![setPropertyValue-debug](../assets/img/setPropertyValue-service-debug.png "setPropertyValue-debug"){.img-fluid tag=1}

![setPropertyValue-success](../assets/img/setPropertyValue-service-success.png "setPropertyValue-success"){.img-fluid tag=1}

### **自定义服务调用**

```JS
//获取实例对象
var instance = ObjectPool.get("device001"); //实例对象别名

//入参
var inputs = {
    propName:'deviceTypeNo', //proName:属性别名
    propValue:'123' //propValue:写入属性值
};
//输出结果
var result = instance.executeService('setPropertyValue',inputs);
result;
```
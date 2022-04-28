## js-storeData

<table>
  <tr>
    <td>作者 ( author )</td>
    <td>tutu辣么可爱(greasyfork)<br>IcedWatermelonJuice(github)</td>
  </tr>
  <tr>
    <td>描述 ( description )</td>
    <td>轻量级原生js本地数据存储管理工具(可选localstorage或GM油猴API)</td>
  </tr>
  <tr>
    <td>最后更新时间 ( day )</td>
    <td>2022.4.29 GMT+0800 (中国标准时间)</td>
  </tr>
  <tr>
    <td>最新版本 ( version )</td>
    <td>1.0</td>
  </tr>
  <tr>
    <td>开源许可 ( license )</td>
    <td>MIT</td>
  </tr>
 </table>

## 参考DEMO 

* 创建  
    
```javascript
var store = {
	a: "aaa",
	b: "bbb",
	c: "ccc"
}
var key = "demo";
var storeDemo = new storeDataJS(key, store);
```
* 增删改查等

```javascript
storeDemo.set("d", "ddd");//增、改
storeDemo.get("d");//查
storeDemo.delete("d");//删
storeDemo.reset();//重置为初始数据store
storeDemo.save();//保存到本地
storeDemo.init();//恢复数据到上一次保存时刻
storeDemo.remove();//彻底删除本地数据
```
## 更多信息

1、storeDataJS(dataKey, defaultData, isGM) 

* 功能：构造storeDataJS对象并初始化存储数据
* dataKey: 本地数据的key，也可以叫本地数据的name
* defaultData：默认数据，是写死在代码里的初始数据
* isGM：布尔参数，默认值false。isGM=true时，本地数据使用GM油猴API；isGM=false时，本地数据使用localstorage

2、storeDataJS.set(key, val, isSave)

* 功能：增改数据
* key：存储数据项的项名
* val：存储数据项的内容
* isSave：布尔参数，默认值false。isSave=true时，增、改数据后立即保存到本地；isSave=false时，不保存到本地

3、storeDataJS.get(key, isDefault)

* 功能：查询数据
* key：本地数据的key，也可以叫本地数据的name
* isDefault：布尔参数，默认false。isDefault=true时，从初始数据(defaultData)里查询；isDefault=false时，从当前数据里查询

4、storeDataJS.delete(key, isSave)

* 功能：删除数据
* key：存储数据项的项名
* isSave：布尔参数，默认值false。isSave=true时，增、改数据后立即保存到本地；isSave=false时，不保存到本地

5、storeDataJS.reset()

* 功能：重置为初始数据defaultData
* 参数：无

6、storeDataJS.save()

* 功能：保存为本地数据
* 参数：无

7、storeDataJS.init()

* 功能：恢复数据到上一次保存时刻
* 参数：无

8、storeDataJS.remove()

* 功能：彻底删除本地数据
* 参数：无

9、storeDataJS.check(data)

* 功能：判断data是否为JSON对象，返回true或false
* data：需要判断是对象

10、storeDataJS.copy(data)

* 功能：深拷贝JSON对象
* data：需要深拷贝的JSON对象

11、storeDataJS.defaultGet(key)

* 功能：获取本地数据。通过构造storeDataJS对象时时输入的isGM选择defaultGet调用的是localStorage.getItem还是GM_getValue
* key：本地数据的key，也可以叫本地数据的name

12、storeDataJS.defaultSet(key, val)

* 功能：保存数据到本地。通过构造storeDataJS对象时输入的isGM选择defaultSet调用的是localStorage.getItem还是GM_getValue
* key：本地数据的key，也可以叫本地数据的name
* val：转换为string字符串的存储数据

13、storeDataJS.defaultRemove(key)

* 功能：保存数据到本地。通过构造storeDataJS对象时输入的isGM选择defaultRemove调用的是localStorage.removeItem还是GM_delete
* key：本地数据的key，也可以叫本地数据的name

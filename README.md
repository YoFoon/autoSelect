# autoSelect（自动筛选数据）
传入想要挑选的的数组字段和关键字，就可以完成筛选（不依赖jquery）

1.可以自动将中文转成改中文的首写字母
即 输入‘微博’的时候，也可以同时查找‘wb’的数据

2.可以忽略大小写

3.输入字母可以查找中文


比如
var arr = new Array();
		arr[0] = ['W.N','Wayfair','美股'];
		arr[1] = ['850542.SL','钨','指数'];
		arr[2] = ['0777.HK','网龙','港股'];
		arr[3] = ['WB.O','微博','美股'];

这里有一个数组名字叫做arr

数组中有4组数据

每组数据中分别有三个可以查找的字段


<input type="text" id="selectData">

var oIpt = document.getElementById('selectData');
oIpt.onkeyup = function() {
	console.log(autoSelect.query(oIpt.value,arr));
}

给input框注册keyup事件
当输入关键字 ‘w’ 的时候

输出为 [Array[3], Array[3], Array[3], Array[3]] ，即 全部得到

因为
arr[0] 中关于 ‘w’的关键字 为字段 ‘W.N’
arr[1] 中关于 ‘w’的关键字 为字段 ‘钨’ （因为钨的首写字母为 W）
arr[2] 中关于 ‘w’的关键字 为字段 ‘网龙’
arr[3] 中关于 ‘w’的关键字 为字段 ‘WB’ 和 ‘微博’

当输入关键字 ‘微博’ 的时候

输出为 [Array[3]]

因为
arr[3] 中关于 ‘微博’的关键字 为字段 ‘微博’







  

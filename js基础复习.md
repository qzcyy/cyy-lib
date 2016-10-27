 ##JavaScript包含三大部分
*  ECMAScript  规定了JS的语法规范
*  DOM   Document Object Model 文档对象模型 提供了操作页面元素的API
*  BOM  Browser Object Model  浏览器对象模型

##JavaScript的基本数据类型
*  string
*  number
*  boolean
##复杂数据类型
*  Array
*  Date
*  Object
* RegExp
* String{大写 string的内置对象}
* Number{number的内置对象}
* Boolean{boolean的内置对象}
* Object
* function

使用typeof获取数据类型{typeof是一个关键字,非方法}

 ## 两个空的类型
* null
* undefind

注:变量不可能为null值,null只能是自己设定的

什么时候要赋值为null?党要解除对象的占用(引用)的时候,释放内存资源
##全等和等于
 全等是值和类型都要相等,而等于只需要值相等 在比较的效率上,全等要慢于相等

##关键字 in
###for...in遍历对象
 for(var k in obj)
 in关键字来遍历的是索引K而不是value

判断一个对象中是否有该属性
 var res=属性 in 对象
返回True OR false

如何找到一个数组中是否含有指定的元素 使用indexof(value)
如果含有value则返回索引的k值 如果没有则返回-1

##值类型和引用类型
值类型
* string
* number
* boolean
* undefined
存储的数据本身的变量就是值类型的数据直接在内存中开辟一个空间来存储值

引用类型
* object
存储的数据在内存中是一个地址,通过地址来指向值

###值类型赋值直接拷贝一份值,两份数据完全独立,引用类型赋值则是将地址传给新的变量
```javaScript
var num = 10;
    function changeNumber( num ){
        //var num1 = num
        num = 100;
//        console.log(num);  //10 or 100
    }

    changeNumber(num);

    console.log(num);
```
输出的结果是10
##实参和形参
实参就是函数调用时,实际传的参数

形参是函数声明时,占位用的参数

在函数调用时 会默认的将实参赋值给形参
所以:如果实参为值类型,在函数中作为参数函数外的值不会改变


如果实参为引用类型 ,在函数外的值会改变,因为在将实参赋值给形参的过程中实际上是将地址给了形参,形参改变的是地址中的值,所以等到实参来解析的时候,地址中得知已经改变了

##在JavaScript中,对象是动态的,可以在使用时动态增加属性

在动态改变对象时,可以使用点语法 obj.key

也可以使用方括号obj[string]    []里面使用的是string类型) obj["key"]

##delete关键字
* 使用delete关键字可以用来删除对象的属性,还有未使用var声明的变量(window的属性)
* delete关键字有返回值 表示是否成功删除
* 如果删除的是不存在的属性,返回值为true
* 如果删除的属性存在于原形中,则返回至为true而且不能删除该属性
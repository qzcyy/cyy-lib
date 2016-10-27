##作用域

js中没有块级作用域

作用域就是一个成员的起作用的范围

当函数中没有这个成员时,函数会默认的向他的上一级寻找,如果还是找不到就会继续向上,直到0级作用域(全局作用域)

##this

当函数使函数形式调用时:

    function();
this指向的是window

当函数使用对象的方法模式调用时

    var a={
           get:function(){}
            }
    
    a.get();
   
this指向的是方法的调用者

当函数使用构造函数调用时

    function a(){}

    var aa=new a();

this指向的是new创建出来的对象

当函数使用上下文模式调用时

    function a(){}

    a.call(xxx,[args0],[args1])
    
    a.apply(xxx,[args])

指定的xxx是谁 this就是谁





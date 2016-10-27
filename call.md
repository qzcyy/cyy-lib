##apply

####使用方法

    不属于自己的方法.apply(传入的this对象,[可选的参数数组,对应到方法的参数])

####例子

        var name="xiaoming";
    function ggg(a,b,c){
        console.log(this.name+a+b+c);
    }
       var obj={
           name:"xiaozhang"
       }
    ggg.call(obj,1,2,3);
    ggg.apply(obj,[4,5,6])

使用apply方法可以改变this的指向,从而改变函数调用的结果,例如:

```js
 var ddd={
        name:"xiaoliu",
        bk: function () {
            console.log(this.name);
        }
    }
       var obj={
           name:"xiaozhang"
       }
   ddd.bk.call(obj);
```
在这里,我们将对象ddd中的方法bk中的this指向了obj,从而使this.name指向了xiaozhang

我们也可以认为是对象obj借用了对象ddd中的方法,由此我们可以得出结论,我们可以借用很多相似的方法,例如伪数组去借用数组中的方法,再比如字符串借用数组的join方法来实现中间加上特定的符号等

**字符串的join

```js
 function foo() {
//            return arguments.join("-");

            //伪数组不具有join方法，所以这个时候就要考虑去借用一下数组的join方法
//            var str = Array.prototype.join.apply(arguments,["-"]);
            var str = [].join.apply(arguments,["-"]);
            return str;
        }
        var str = foo(1, 3, "abc", "ffff", 99) // 1-3-abc-ffff-99
```

**将页面上的所有div和p加上背景色
```js
var divs = document.getElementsByTagName("div");
            var ps = document.getElementsByTagName("p");

            var arr = [];
            //little tip:  push方法可以传多个参数
            //arr.push(1,2,3,4,4,5)

            arr.push.apply(arr,divs);
            arr.push.apply(arr,ps);

            //如果使用arr.push()直接把divs传进来
            //那么相当于在arr中的第一个元素中存储了一个divs数组
            //但是我们需要把divs中的每一个元素单独的存入arr中
            //所以需要调用push方法的如下形式  push(1,2,4,4,5)
            //要实现这个形式的调用，就用到了apply方法的第二个参数的特性
            //在调用的时候，会第二个参数的数组，拆成每一个元素以（a,b,c,d,e,f,g） 传入函数

            //相当于 arr.push(divs[0],divs[1],divs[..])
//            arr.push(divs)



            for (var k = 0; k < arr.length; k++) {
                var ele = arr[k];
                ele.style.backgroundColor = "yellow";
            }
```

##call

和apply同理,只是参数变成了一个个的形式,主要使用在确定的参数个数的情况下
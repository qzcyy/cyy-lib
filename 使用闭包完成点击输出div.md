##原理
当循环进行的时候,由于js是单线程的,会在完成循环后再对oncilck方法进行赋值,所以所有oncilck方法中的所有i都是循环完成后i最后的值,如果要每次进入循环到oncilck的时候就进行赋值则需要在oncilck之后使用立即执行函数(自调用函数),当程序执行到自调用函数时,会解析为执行函数,返回一个已经将当时的i传入的函数,所以在最后解析function的时候,当时的i已经赋值成功了
```js
 window.onload= function () {

 var divs=document.querySelectorAll("div");

 for (var i = 0; i < divs.length; i++) {

 var div = divs[i];

 div.onclick= (function (k) {

 return function () {

 alert("这是第"+k+"个div");

 }

 })(i);

 }
}


```

##使用闭包来完成在for循环中的定时器中的输出

```js
for (var i = 0; i < 10; i++) {

 setTimeout((function (k) {

 return function () {

 console.log(k);

 }

 })(i),0);

 }

```
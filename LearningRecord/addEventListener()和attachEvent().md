

###  addEventListener()和attachEvent()为某个元素绑定多个事件，功能一样，写法不同。 
### 一、attachEvent() 
### 添加事件到对象，只有IE浏览器支持attachEvent()，先看个例子：

```
document.getElementById("btn").onclick = method1;  
document.getElementById("btn").onclick = method2;  
document.getElementById("btn").onclick = method3;//如果这样写,只有medhot3被执行  
```
语法element.attachEvent(type,listener)

element：元素。可以是文档节点、document、window 或 XMLHttpRequest。 

type：事件类型名称。必须含“on”，比如“onclick”、“onmouseover”、“onkeydown”等。

listener：要绑定事件的名称，也就是你写好的函数，不要加括号。 

执行顺序：后绑定的先执行。 

请看实例
```
var btn = document.getElementById("btn1");   
btn.attachEvent("onclick",method1);  
btn.attachEvent("onclick",method2);  
btn.attachEvent("onclick",method3);//执行顺序为method3->method2->method1  
```

### 二、addEventListener() 
添加事件到对象，除IE浏览器之外都支持addEventListener()。 

语法element.addEventListener(type,listener,useCapture) 

element：元素，可以是文档节点、document、window 或 XMLHttpRequest。 

type：事件类型，不含“on”，比如“click”、“mouseover”、“keydown”等。

listener：要绑定事件的名称，也就是你写好的函数，不要加括号。 

useCapture：布尔值，false或true必须填写，false代表支持浏览器事件捕获功能，true代表支持浏览事件冒泡功能，一般用 false 。
执行顺序：先绑定的先执行。 

三个参数，必须设置，缺一不可。 

请看实例
```
var btn = document.getElementById("btn1");   
btn.addEventListener("click",method1,false);  
btn.addEventListener("click",method2,false);  
btn.addEventListener("click",method3,false);//执行顺序为method1->method2->method3  
```
### 三、添加监听事件的方法。
```
if (window.attachEvent) {    
    window.attachEvent("onload", show);    
} else if (window.addEventListener) {    
    window.addEventListener("load", show, false);      
}   
```


### 事件绑定写法 兼容IE
```
function addEvent(obj,type,fn){
    if(obj.attachEvent){
        obj.attachEvent('on'+type,function(){
            fn.call(obj);
        })
    }else{
        obj.addEventListener(type,fn,false);
    }
}
addEvent(window,'scroll',function(){
    alert('first method')
});
addEvent(window,'scroll',function(){
    alert('second method')
});
```
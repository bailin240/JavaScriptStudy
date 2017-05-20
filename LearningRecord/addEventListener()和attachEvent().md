

###  addEventListener()��attachEvent()Ϊĳ��Ԫ�ذ󶨶���¼�������һ����д����ͬ�� 
### һ��attachEvent() 
### ����¼�������ֻ��IE�����֧��attachEvent()���ȿ������ӣ�

```
document.getElementById("btn").onclick = method1;  
document.getElementById("btn").onclick = method2;  
document.getElementById("btn").onclick = method3;//�������д,ֻ��medhot3��ִ��  
```
�﷨element.attachEvent(type,listener)

element��Ԫ�ء��������ĵ��ڵ㡢document��window �� XMLHttpRequest�� 

type���¼��������ơ����뺬��on�������硰onclick������onmouseover������onkeydown���ȡ�

listener��Ҫ���¼������ƣ�Ҳ������д�õĺ�������Ҫ�����š� 

ִ��˳�򣺺�󶨵���ִ�С� 

�뿴ʵ��
```
var btn = document.getElementById("btn1");   
btn.attachEvent("onclick",method1);  
btn.attachEvent("onclick",method2);  
btn.attachEvent("onclick",method3);//ִ��˳��Ϊmethod3->method2->method1  
```

### ����addEventListener() 
����¼������󣬳�IE�����֮�ⶼ֧��addEventListener()�� 

�﷨element.addEventListener(type,listener,useCapture) 

element��Ԫ�أ��������ĵ��ڵ㡢document��window �� XMLHttpRequest�� 

type���¼����ͣ�������on�������硰click������mouseover������keydown���ȡ�

listener��Ҫ���¼������ƣ�Ҳ������д�õĺ�������Ҫ�����š� 

useCapture������ֵ��false��true������д��false����֧��������¼������ܣ�true����֧������¼�ð�ݹ��ܣ�һ���� false ��
ִ��˳���Ȱ󶨵���ִ�С� 

�����������������ã�ȱһ���ɡ� 

�뿴ʵ��
```
var btn = document.getElementById("btn1");   
btn.addEventListener("click",method1,false);  
btn.addEventListener("click",method2,false);  
btn.addEventListener("click",method3,false);//ִ��˳��Ϊmethod1->method2->method3  
```
### ������Ӽ����¼��ķ�����
```
if (window.attachEvent) {    
    window.attachEvent("onload", show);    
} else if (window.addEventListener) {    
    window.addEventListener("load", show, false);      
}   
```


### �¼���д�� ����IE
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
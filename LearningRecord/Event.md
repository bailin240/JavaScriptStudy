
event代表事件的状态，例如触发event对象的元素、鼠标的位置及状态、按下的键等等。event对象只在事件发生的过程中才有效。event的某些属性只对特定的事件有意义。比如，fromElement 和 toElement 属性只对 onmouseover 和 onmouseout 事件有意义。 
```



//X:水平位置	Y：垂直位置

screenX:655     获取屏幕X坐标 ( 原点是屏幕的左上角 )
screenY:351     返回当某个事件被触发时，鼠标指针的水平坐标。

clientX:655     获取当前窗口X坐标 ( 原点是页面的左上角，会随滚动条的移动来改变值 )
clientY:261     返回当事件被触发时，鼠标指针的水平坐标。

layerX:655      获取当前窗口X坐标 ( 原点是页面的左上角，会随滚动条的移动来改变值 )
layerY:261

pageX:655       获取页面区域中的X坐标 ( 原点是窗口区的左上角，不会随滚动动的移动来改变值 )
pageY:261

offsetX:97      鼠标当前相对于网页中的某一区域的位置 ( 原点是当前触发元素的左上角)
offsetY:53      发生事件的地点在事件源元素的坐标系统中的 x 坐标和 y 坐标。

x:655           事件发生的位置的 x 坐标和 y 坐标，它们相对于用CSS动态定位的最内层包容元素。
y:261           

movementX:-8
movementY:-2

type:"mouseenter"        返回事件名     ( 返回没有“on”作为前缀的事件名，比如，onclick事件返回的type是click )
target:div#box          返回触发此事件的元素（事件的目标节点）。

bubbles:false           返回布尔值，指示事件是否是起泡事件类型。
cancelable:false        返回布尔值，指示事件是否可拥可取消的默认动作。
currentTarget:div#box       返回其事件监听器触发该事件的元素。
eventPhase:2        返回事件传播的当前阶段。它的值是下面的三个常量之一，它们分别表示捕获阶段、正常事件派发和起泡阶段。
    Event.CAPTURING_PHASE   1
    Event.AT_TARGET         2
    Event.BUBBLING_PHASE    3
timeStamp:23956.195     返回事件生成的日期和时间。


//鼠标 / 键盘属性
altKey:false        检查alt键的状态         当alt键按下时，值为True否则为False      只读
ctrlKey:false       检查ctr键的状态         当ctr键按下时，值为True否则为False      只读
shiftKey:false      检查shift键的状态       当shift键按下时，值为True否则为False    只读
relatedTarget:html      返回与事件的目标节点相关的节点
metaKey:false       返回当事件被触发时，"meta" 键是否被按下。
button:0            检查按下的鼠标键
    0 没按键 
    1 按左键 
    2 按右键 
    3 按左右键 
    4 按中间键 
    5 按左键和中间键 
    6 按右键和中间键 
    7 按所有的键
    仅用于onmousedown，onmouseup和onmousemove事件。对其他事件，不管鼠标状态如何，都返回0（比如onclick）
    
buttons:0       表示一个或多个按钮的数字。对于多个按钮按下，值相结合。
    0  : 没有按钮或未初始化
    1  : 左键
    2  : 右键
    4  : 车轮按钮或中间按钮
    8  : 第四按钮（通常是“浏览器回来”按钮）
    16 : 第五按钮（通常是“浏览器向前”按钮）

    
//IE 属性
//除了上面的鼠标/事件属性，IE 浏览器还支持下面的属性：
cancelBubble:false      如果事件句柄想阻止事件传播到包容对象，必须把该属性设为 true。
srcElement:div#box       检测onmouseover和onmouseout事件发生时，鼠标所离开的元素
toElement:div#box        检测onmouseover和onmouseout事件发生时，鼠标所进入的元素	
fromElement:html    对于 mouseover 和 mouseout 事件，fromElement 引用移出鼠标的元素。
returnValue:true        如果设置了该属性，它的值比事件句柄的返回值优先级高。把这个属性设置为 fasle，可以取消发生事件的源元素的默认动作。



//这几个不知道什么意思
composed:true
view:Window
detail:0
which:0
isTrusted:true
path:Array[5]
sourceCapabilities:InputDeviceCapabilities
defaultPrevented:false
```
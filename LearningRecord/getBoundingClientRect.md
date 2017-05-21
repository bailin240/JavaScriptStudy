### getBoundingClientRect()

#### 这个方法返回一个矩形对象，包含四个属性：left、top、right和bottom。分别表示元素各边与页面上边和左边的距离。
```
var box=document.getElementById('box');         // 获取元素

alert(box.getBoundingClientRect().top);         // 元素上边距离页面上边的距离

alert(box.getBoundingClientRect().right);       // 元素右边距离页面左边的距离

alert(box.getBoundingClientRect().bottom);      // 元素下边距离页面上边的距离

alert(box.getBoundingClientRect().left);        // 元素左边距离页面左边的距离

//注意：IE、Firefox3+、Opera9.5、Chrome、Safari支持，在IE中，默认坐标从(2,2)开始计算，导致最终距离比其他浏览器多出两个像素，我们需要做个兼容。

document.documentElement.clientTop;  // 非IE为0，IE为2

document.documentElement.clientLeft; // 非IE为0，IE为2

functiongGetRect (element) {

    var rect = element.getBoundingClientRect();

    var top = document.documentElement.clientTop;

    var left= document.documentElement.clientLeft;

    return{

        top    :   rect.top - top,

        bottom :   rect.bottom - top,

        left   :   rect.left - left,

        right  :   rect.right - left

    }

}
```
分别加上外边据、内边距、边框和滚动条，用于测试所有浏览器是否一致。



### getBoundingClientRect获取元素位置 

getBoundingClientRect用于获得页面中某个元素的左，上，右和下分别相对浏览器视窗的位置。getBoundingClientRect是DOM元素到浏览器可视范围的距离（不包含文档卷起的部分）。该函数返回一个Object对象，该对象有6个属性：top,lef,right,bottom,width,height；这里的top、left和css中的理解很相似，width、height是元素自身的宽高，但是right，bottom和css中的理解有点不一样。right是指元素右边界距窗口最左边的距离，bottom是指元素下边界距窗口最上面的距离。

getBoundingClientRect()最先是IE的私有属性，现在已经是一个W3C标准。所以你不用当心浏览器兼容问题，不过还是有区别的：IE只返回top,lef,right,bottom四个值，不够可以通过以下方法来获取width,height的值：

    var ro = object.getBoundingClientRect();
    var Width = ro.right - ro.left;
    var Height = ro.bottom - ro.top;

兼容所有浏览器写法：

    var ro = object.getBoundingClientRect();
    var Top = ro.top;
    var Bottom = ro.bottom;
    var Left = ro.left;
    var Right = ro.right;
    var Width = ro.width||Right - Left;
    var Height = ro.height||Bottom - Top;

有了这个方法，获取页面元素的位置就简单多了:

    var X= this.getBoundingClientRect().left+document.documentElement.scrollLeft;
    var Y =this.getBoundingClientRect().top+document.documentElement.scrollTop;



通过测试，至少Chrome 2+\Safari 4\Firefox3.5\0pera 9.63+已经支持getBoundingClientRect方法。

使用场景差异:

出于浏览器兼容的考虑，现在用得最多的是getBoundingClientRect，经常用来获取一个element元素的viewport坐标。 
### getBoundingClientRect()

#### �����������һ�����ζ��󣬰����ĸ����ԣ�left��top��right��bottom���ֱ��ʾԪ�ظ�����ҳ���ϱߺ���ߵľ��롣
```
var box=document.getElementById('box');         // ��ȡԪ��

alert(box.getBoundingClientRect().top);         // Ԫ���ϱ߾���ҳ���ϱߵľ���

alert(box.getBoundingClientRect().right);       // Ԫ���ұ߾���ҳ����ߵľ���

alert(box.getBoundingClientRect().bottom);      // Ԫ���±߾���ҳ���ϱߵľ���

alert(box.getBoundingClientRect().left);        // Ԫ����߾���ҳ����ߵľ���

//ע�⣺IE��Firefox3+��Opera9.5��Chrome��Safari֧�֣���IE�У�Ĭ�������(2,2)��ʼ���㣬�������վ�����������������������أ�������Ҫ�������ݡ�

document.documentElement.clientTop;  // ��IEΪ0��IEΪ2

document.documentElement.clientLeft; // ��IEΪ0��IEΪ2

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
�ֱ������߾ݡ��ڱ߾ࡢ�߿�͹����������ڲ�������������Ƿ�һ�¡�



### getBoundingClientRect��ȡԪ��λ�� 

getBoundingClientRect���ڻ��ҳ����ĳ��Ԫ�ص����ϣ��Һ��·ֱ����������Ӵ���λ�á�getBoundingClientRect��DOMԪ�ص���������ӷ�Χ�ľ��루�������ĵ�����Ĳ��֣����ú�������һ��Object���󣬸ö�����6�����ԣ�top,lef,right,bottom,width,height�������top��left��css�е��������ƣ�width��height��Ԫ������Ŀ�ߣ�����right��bottom��css�е�����е㲻һ����right��ָԪ���ұ߽�ര������ߵľ��룬bottom��ָԪ���±߽�ര��������ľ��롣

getBoundingClientRect()������IE��˽�����ԣ������Ѿ���һ��W3C��׼�������㲻�õ���������������⣬��������������ģ�IEֻ����top,lef,right,bottom�ĸ�ֵ����������ͨ�����·�������ȡwidth,height��ֵ��

    var ro = object.getBoundingClientRect();
    var Width = ro.right - ro.left;
    var Height = ro.bottom - ro.top;

�������������д����

    var ro = object.getBoundingClientRect();
    var Top = ro.top;
    var Bottom = ro.bottom;
    var Left = ro.left;
    var Right = ro.right;
    var Width = ro.width||Right - Left;
    var Height = ro.height||Bottom - Top;

���������������ȡҳ��Ԫ�ص�λ�þͼ򵥶���:

    var X= this.getBoundingClientRect().left+document.documentElement.scrollLeft;
    var Y =this.getBoundingClientRect().top+document.documentElement.scrollTop;



ͨ�����ԣ�����Chrome 2+\Safari 4\Firefox3.5\0pera 9.63+�Ѿ�֧��getBoundingClientRect������

ʹ�ó�������:

������������ݵĿ��ǣ������õ�������getBoundingClientRect������������ȡһ��elementԪ�ص�viewport���ꡣ 
��ִ�������ĵĴ����׶Σ���ֱ����ɱ������󣬽�������������ȷ��thisָ�����б��������������������Ƕ��Ѿ���ϸ�ܽ���ˣ�������Ĺؼ�������ȷ��thisָ��

�����������Ҫ�ó�һ���ǳ���Ҫһ��Ҫ�μ����ĵĽ��ۣ�this��ָ�����ں��������õ�ʱ��ȷ���ġ�Ҳ����ִ�������ı�����ʱȷ���ġ�������ǿ��Ժ����׾�����⵽��һ�������е�thisָ�򣬿����Ƿǳ����ġ���������������У�ͬһ���������ڵ��÷�ʽ�Ĳ�ͬ��thisָ���˲�һ���Ķ���
```
var a = 10;
var obj = {
    a: 20
}

function fn () {
    console.log(this.a);
}

fn(); // 10
fn.call(obj); // 20
```
����֮�⣬�ں���ִ�й����У�thisһ����ȷ�����Ͳ��ɸ����ˡ�
```
var a = 10;
var obj = {
    a: 20
}

function fn () {
    this = obj; // ��仰��ͼ�޸�this�����к�ᱨ��
    console.log(this.a);
}

fn();
```
һ��ȫ�ֶ����е�this

����ȫ�ֶ����this����֮ǰ���ܽ���������ʱ���ᵽ��������һ���Ƚ�����Ĵ��ڡ�ȫ�ֻ����е�this��ָ����������ˣ���Ҳ��Լ򵥣�û����ô�ิ�ӵ������Ҫ���ǡ�
```
// ͨ��this�󶨵�ȫ�ֶ���
this.a2 = 20;

// ͨ�������󶨵��������󣬵���ȫ�ֻ����У������������������
var a1 = 10;

// ����ֻ�и�ֵ��������ʶ������ʽ�󶨵�ȫ�ֶ���
a3 = 30;

// ��������ȫ������Ԥ��
console.log(a1);
console.log(a2);
console.log(a3);
```
���������е�this

���ܽắ����thisָ��֮ǰ�����������б�Ҫͨ��һЩ��ֵ����ӣ�������һ�º�����this��׽��������
```
// demo01
var a = 20;
function fn() {
    console.log(this.a);
}
fn();
```
```
// demo02
var a = 20;
function fn() {
    function foo() {
        console.log(this.a);
    }
    foo();
}
fn();
```
```
// demo03
var a = 20;
var obj = {
    a: 10,
    c: this.a + 20,
    fn: function () {
        return this.a;
    }
}

console.log(obj.c);
console.log(obj.fn());
```
�⼸��������Ҫ������ү�ǻ���ʱ����΢����һ�£��������ʱû��������ô���£�Ҳ�����ż�������һ��һ����������

����֮ǰ��������ֱ���˵��׳����ۡ�

��һ�������������У�this�ɵ������ṩ���ɵ��ú����ķ�ʽ����������������ߺ�������ĳһ��������ӵ�У���ô�ú����ڵ���ʱ���ڲ���thisָ��ö�����������������ã���ô�ú����ڲ���this����ָ��undefined�������ڷ��ϸ�ģʽ�У���thisָ��undefinedʱ�����ᱻ�Զ�ָ��ȫ�ֶ���

�ӽ��������ǿ��Կ�������Ҫ׼ȷȷ��thisָ���ҵ������ĵ������Լ��������Ƿ��Ƕ������þͱ��ʮ�ֹؼ���
```
// Ϊ���ܹ�׼ȷ�жϣ������ں����ڲ�ʹ���ϸ�ģʽ����Ϊ���ϸ�ģʽ���Զ�ָ��ȫ��
function fn() {
    'use strict';
    console.log(this);
}

fn();  // fn�ǵ����ߣ���������
window.fn();  // fn�ǵ����ߣ���window��ӵ��
```
������ļ������У�fn()��Ϊ���������ߣ����ն������⣬���ڲ���thisָ���Ϊundefined����window.fn()����Ϊfn��window��ӵ�У��ڲ���this��ָ����window����

��ô����������������ڻع�ͷȥ����������������ӣ�ͨ�����/ȥ���ϸ�ģʽ����ô��ͻᷢ�֣�ԭ��this�Ѿ���ò���ô������翣��Ѿ��м���ѭ�ˡ�

����������Ҫ�ر�ע�����demo03����demo03�У�����obj�е�c����ʹ��this.a + 20�����㣬�����ĵ�����obj.c������һ�������������������������Ĺ�������Ҫ�����ַ�ʽ������һ�����ۡ�

��obj��ȫ������ʱ������obj.c��ʲô�ط����ã������this��ָ��ȫ�ֶ��󣬶���obj�ں�������������ʱ�����thisָ��undefined���ڷ��ϸ�ģʽ�£����Զ�ת��ȫ�ֶ��󡣿�������������Ӳ鿴����
```
'use strict';
var a = 20;
function foo () {
    var a = 1;
    var obj = {
        a: 10, 
        c: this.a + 20,
        fn: function () {
            return this.a;
        }
    }
    return obj.c;

}
console.log(foo()); // ���лᱨ��
```
ʵ�ʿ����У������Ƽ�����ʹ��this��
�������ᵽ���ϸ�ģʽ����Ҫ�������Դ�����Ϊ��ʵ�ʿ����У����ڻ����Ѿ�ȫ�������ϸ�ģʽ�ˣ������µ�ES6��Ҳ��Ĭ��֧���ϸ�ģʽ��
������һЩ��������������ӣ�����һ�¶Ե��������Ƿ�������е���⡣
```
var a = 20;
var foo = {
    a: 10,
    getA: function () {
        return this.a;
    }
}
console.log(foo.getA()); // 10

var test = foo.getA;
console.log(test());  // 20
```
foo.getA()�У�getA�ǵ����ߣ������Ƕ������ã�������foo��ӵ�У��������thisָ����foo����test()��Ϊ�����ߣ���������foo.getA��������ͬ���������Ƕ������õģ����thisָ��undefined���ڷ��ϸ�ģʽ���Զ�ת��ȫ��window��

��΢�޸�һ�´��룬���������⡣
```
var a = 20;
function getA() {
    return this.a;
}
var foo = {
    a: 10,
    getA: getA
}
console.log(foo.getA());  // 10
```
���һ��������һ�����������ӡ�
```
function foo() {
    console.log(this.a)
}

function active(fn) {
    fn(); // ��ʵ�����ߣ�Ϊ��������
}

var a = 20;
var obj = {
    a: 10,
    getA: foo
}

active(obj.getA);
```
����ʹ��call��apply��ʾָ��this

JavaScript�ڲ��ṩ��һ�ֻ��ƣ������ǿ��������ֶ�����this��ָ�����Ǿ���call��apply�����еĺ������������������������ǳ��˲������в�ͬ���书����ȫһ�������ǵĵ�һ��������Ϊthis��Ҫָ��Ķ���

����������ʾ��fn�������ڶ���obj�ķ���������ͨ��call�����ǽ�fn�ڲ���this��Ϊobj����˾Ϳ���ʹ��this.a����obj��a�����ˡ������call/apply���÷���
```
function fn() {
    console.log(this.a);
}
var obj = {
    a: 20
}

fn.call(obj);
```
��call��applay����Ĳ�����������Ҫִ�еĺ������ݲ���������call��һ��һ������ʽ���ݣ�apply���������ʽ���ݡ���������Ψһ�Ĳ�ͬ��
```
function fn(num1, num2) {
    console.log(this.a + num1 + num2);
}
var obj = {
    a: 20
}

fn.call(obj, 100, 10); // 130
fn.apply(obj, [20, 10]); // 50
```
��Ϊcall/apply�Ĵ��ڣ�����JavaScript���ʮ������˾���call/applyӵ���˺ܶ����ô��ĳ��������ܽἸ�㣬Ҳ��ӭ��Ҳ��䡣

�����������ת��Ϊ����
```
function exam(a, b, c, d, e) {

    // �ȿ����������Դ����� arguments ʲô�����ӵ�
    console.log(arguments);

    // ʹ��call/apply��argumentsת��Ϊ����, ���ؽ��Ϊ���飬arguments������ı�
    var arg = [].slice.call(arguments);

    console.log(arg);
}

exam(2, 8, 9, 10, 3);

// result: 
// { '0': 2, '1': 8, '2': 9, '3': 10, '4': 3 }
// [ 2, 8, 9, 10, 3 ]
// 
// Ҳ����ʹ�ø÷�����DOM�е�nodelistת��Ϊ����
// [].slice.call( document.getElementsByTagName('li') );
```

�����Լ�����Ҫ����޸�thisָ��
```
var foo = {
    name: 'joker',
    showName: function() {
      console.log(this.name);
    }
}
var bar = {
    name: 'rose'
}
foo.showName.call(bar);
```
ʵ�ּ̳�
```
// ���常���Ĺ��캯��
var Person = function(name, age) {
    this.name = name;
    this.age  = age;
    this.gender = ['man', 'woman'];
}

// ��������Ĺ��캯��
var Student = function(name, age, high) {

    // use call
    Person.call(this, name, age);
    this.high = high;
}
Student.prototype.message = function() {
    console.log('name:'+this.name+', age:'+this.age+', high:'+this.high+', gender:'+this.gender[0]+';');
}

new Student('xiaom', 12, '150cm').message();

// result
// ----------
// name:xiaom, age:12, high:150cm, gender:man;
```
�򵥸������������������ѽ���һ�¡���Student�Ĺ��캯���У�����call�������������Ĺ��캯��ִ����һ�Σ��൱�ڽ�Person�еĴ��룬��Sudent�и�����һ�ݣ����е�thisָ��Ϊ��Student��new������ʵ������call������֤��this��ָ����ȷ����˾��൱��ʵ���˻��㡣Student�Ĺ��캯����ͬ���¡�
```
var Student = function(name, age, high) {
    this.name = name;
    this.age  = age;
    this.gender = ['man', 'woman'];
    // Person.call(this, name, age); ��һ�仰���൱���������仰�����ʵ���˼̳�
    this.high = high;
}
```
��������ִ�������ĵĴ����У�ȷ��this��ָ�򱣳ֲ���
������������У������ڴ�����getA��obj����ʱ��thisָ��obj�������������������Ĵ��ڵ�����thisָ��Ķ�ʧ�����������������thisָ����ȫ�֣����������Ҫ��һЩ�취�һ���ȷ��thisָ��
```
var obj = {
    a: 20,
    getA: function() {
        setTimeout(function() {
            console.log(this.a)
        }, 1000)
    }
}

obj.getA();
```
����Ľ���취�ܼ򵥣�����ʹ��һ����������this�����ñ������������ǳ������õ��ⷽ������������ҲҪ�������潲������֪ʶ�����ж�this�Ƿ��ڴ����б��޸��ˣ����û�б��޸ģ���û�б�Ҫ����ʹ���ˡ�
```
var obj = {
    a: 20,
    getA: function() {
        var self = this;
        setTimeout(function() {
            console.log(self.a)
        }, 1000)
    }
}
```
������ǽ����հ���apply��������װһ��bind������
```
function bind(fn, obj) {
    return function() {
        return fn.apply(obj, arguments);
    }
}

var obj = {
    a: 20,
    getA: function() {
        setTimeout(bind(function() {
            console.log(this.a)
        }, this), 1000)
    }
}

obj.getA();
```
��Ȼ��Ҳ����ʹ��ES5���Ѿ��Դ���bind�����������������װ��bind������һ����Ч����
```
var obj = {
    a: 20,
    getA: function() {
        setTimeout(function() {
            console.log(this.a)
        }.bind(this), 1000)
    }
}
```
�ġ����캯����ԭ�ͷ����ϵ�this

�ڷ�װ�����ʱ�����Ǽ��������õ�this�����ǣ�ֻ�������˸�����������������е�thisָ�򣬾������������ԭ�ͣ�Ҳ��һ�������this��������һ���֣�����Ϊ����Ϊ��ƪ��������Ҫ����ĵĲ��֡����������������ѧϰJS�����������޴�İ�����

�����������ӣ����������׳�����������˼��һ�¡�
```
function Person(name, age) {

    // �����thisָ����˭?
    this.name = name;
    this.age = age;   
}

Person.prototype.getName = function() {

    // �����this��ָ����˭��
    return this.name;
}

// �����2��this����ͬһ���������Ƿ�ָ����ԭ�Ͷ���

var p1 = new Person('Nick', 20);
p1.getName();
```
�����Ѿ�֪����this�����ں������ù�����ȷ������ˣ�������new�Ĺ����е��׷�����ʲô�ͱ��ʮ����Ҫ��

ͨ��new���������ù��캯�����ᾭ������4���׶Ρ�

����һ���µĶ���
�����캯����thisָ������¶���
ָ���캯���Ĵ��룬Ϊ�������������ԣ������ȣ�
�����¶���
��ˣ���new���������ù��캯��ʱ��this��ʵָ���������´����Ķ�������ֽ��µĶԷ����س�������ʵ������p1���ա���ˣ����ǿ���˵�����ʱ�򣬹��캯����this��ָ�����µ�ʵ������p1��

��ԭ�ͷ����ϵ�this�ͺ������ˣ������ϱ߶Ժ�����this�Ķ��壬p1.getName()�е�getNameΪ�����ߣ�����p1��ӵ�У����getName�е�this��Ҳ��ָ����p1��
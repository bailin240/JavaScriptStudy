### Location reload() 方法
```

#### 定义和用法

reload()方法用于刷新当前文档。

reload() 方法类似于你浏览器上的刷新页面按钮。

如果把该方法的参数设置为 true，那么无论文档的最后修改日期是什么，它都会绕过缓存，从服务器上重新下载该文档。

这与用户在单击浏览器的刷新按钮时按住 Shift 健的效果是完全一样。

//可选。如果把该方法的参数设置为 true，那么无论文档的最后修改日期是什么，它都会绕过缓存，从服务器上重新下载该文档。

语法：location.reload(forceGet)
```


### Location search 属性
```
假设当前的URL就是http://www.runoob.com/submit.htm?email=someone@ example.com

//search 属性是一个可读可写的字符串，可设置或返回当前 URL 的查询部分（问号 ? 之后的部分）。

document.write(location.search);

输出结果: ?email=someone@example.com
```
### Location hash 属性
```
假设当前的URL是http://www.w3cschool.cc/test.htm＃PART2

//hash 属性是一个可读可写的字符串，该字符串是 URL 的锚部分（从 # 号开始的部分）。

语法:document.write(location.hash);

输出结果: #part2
```
### Location hostname 属性
```
假设当前的URL是http://www.w3cschool.com/test.htm＃PART2

//hostname 属性是一个可读可写的字符串，可设置或返回当前 URL 的主机名。

语法:document.write(location.hostname);

输出结果: www.w3cschool.com
```
### Location href 属性
```
假设当前的URL是http://www.w3cschool.cc/test.htm＃PART2

//href 属性是一个可读可写的字符串，可设置或返回当前显示的文档的完整 URL。

语法:document.write(location.href);

输出结果: http://www.w3cschool.cc/test.htm＃PART2
```
### Location pathname 属性
```
假设当前的URL是http://www.runoob.com/jsref/prop-loc-pathname.html

//pathname 属性是一个可读可写的字符串，可设置或返回当前 URL 的路径部分。

语法:document.write(location.pathname);

输出结果: /jsref/prop-loc-pathname.html
```
### Location protocol 属性
```
假设当前的URL是http://www.runoob.com/jsref/prop-loc-pathname.html

//protocol 属性是一个可读可写的字符串，可设置或返回当前 URL 的协议。

语法:document.write(location.protocol);

输出结果: http:
```

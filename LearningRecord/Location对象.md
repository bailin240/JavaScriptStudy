### Location reload() ����
```

#### ������÷�

reload()��������ˢ�µ�ǰ�ĵ���

reload() ������������������ϵ�ˢ��ҳ�水ť��

����Ѹ÷����Ĳ�������Ϊ true����ô�����ĵ�������޸�������ʲô���������ƹ����棬�ӷ��������������ظ��ĵ���

�����û��ڵ����������ˢ�°�ťʱ��ס Shift ����Ч������ȫһ����

//��ѡ������Ѹ÷����Ĳ�������Ϊ true����ô�����ĵ�������޸�������ʲô���������ƹ����棬�ӷ��������������ظ��ĵ���

�﷨��location.reload(forceGet)
```


### Location search ����
```
���赱ǰ��URL����http://www.runoob.com/submit.htm?email=someone@ example.com

//search ������һ���ɶ���д���ַ����������û򷵻ص�ǰ URL �Ĳ�ѯ���֣��ʺ� ? ֮��Ĳ��֣���

document.write(location.search);

������: ?email=someone@example.com
```
### Location hash ����
```
���赱ǰ��URL��http://www.w3cschool.cc/test.htm��PART2

//hash ������һ���ɶ���д���ַ��������ַ����� URL ��ê���֣��� # �ſ�ʼ�Ĳ��֣���

�﷨:document.write(location.hash);

������: #part2
```
### Location hostname ����
```
���赱ǰ��URL��http://www.w3cschool.com/test.htm��PART2

//hostname ������һ���ɶ���д���ַ����������û򷵻ص�ǰ URL ����������

�﷨:document.write(location.hostname);

������: www.w3cschool.com
```
### Location href ����
```
���赱ǰ��URL��http://www.w3cschool.cc/test.htm��PART2

//href ������һ���ɶ���д���ַ����������û򷵻ص�ǰ��ʾ���ĵ������� URL��

�﷨:document.write(location.href);

������: http://www.w3cschool.cc/test.htm��PART2
```
### Location pathname ����
```
���赱ǰ��URL��http://www.runoob.com/jsref/prop-loc-pathname.html

//pathname ������һ���ɶ���д���ַ����������û򷵻ص�ǰ URL ��·�����֡�

�﷨:document.write(location.pathname);

������: /jsref/prop-loc-pathname.html
```
### Location protocol ����
```
���赱ǰ��URL��http://www.runoob.com/jsref/prop-loc-pathname.html

//protocol ������һ���ɶ���д���ַ����������û򷵻ص�ǰ URL ��Э�顣

�﷨:document.write(location.protocol);

������: http:
```

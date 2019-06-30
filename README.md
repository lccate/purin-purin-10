# 多级指针
## const的使用  
const修饰一个变量为只读  
```
const int a = 100;
a=100;   //err, 无法更改a的值
```
```
char buf[] = "abcd";
const char *p = buf;  //等价于char const *p1 = buf;
```
怎样分辨是指针常量还是常量指针？  
从左往右看，去掉类型，看const修饰什么，如果是※（常量指针，const+※），不能通过指针来修改内存的值  
```
const char *p = buf；//不能通过*p来修改buf的值，但是可以修改指针p(即让他指向别的内存)，也可以直接修改buf的值
```
如果修饰指针变量（指针常量，※+const），说明指针不能修改，即指针的指向不能修改  
```
char * const p = buf; //指针p只能指向buf，不能指向其他内存
```
const既修饰※又修饰指针  
```
const char * const p = buf;
```
c语言中的const是一个冒牌货，可以通过指针进行修改  
```
const int b = 10;
b = 20; //err
int *p = &b;
*p = 20; //ok
```
## 二级指针
值传递与地址传递比较  
![值传递](1.png)  
![参数传递](2.png)  


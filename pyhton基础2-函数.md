### 函数  
def关键字声明函数  
def sum(num,num2):   //num,num2 为形参  
&emsp;result = num + num2  
&emsp;print(result)  
sum(22,33)  //调用函数，22，33为实参  
\------------------------------------------  
关键字参数  
def some(name,word):  
&emsp;print(name + '和' + word)  
some(word='我’，name='你')  
\----------------------------------------  
默认参数  
def some(name='李白',word='诗'):  
&emsp;print(name +'和'+word)  
some(word='杜甫')  //调用函数，输出李白和杜甫  
\-----------------------------------------  
收集参数  
def test(*params,hh):     //*号，不确定有多少个参数  
&emsp;print('参数长度：',len(params))    //输出 4  
&emsp;print('第二个参数是：',params[1])  //输出 2  

test(1,2,3,4,hh='abcde')  

#### 全局和局部  
def fun():  
&emsp;num1=2  
&emsp;print('函数修改后num1=',num1)  
num1=1  
print('初始num1=',num1)    //输出 初始num1=1  
fun()                       //输出  函数修改后num1=2  
print('运行函数后num1=',num1)  //输出   运行完函数后num1=1  
函数内部对全局变量修改后 修改的结果是无效的，全局变量不会受影响  

def fun1():  
&emsp;global num1  
&emsp;num1 = 2  
&emsp;print('函数修改后num1=',num1)  
num1 = 1 
print('初始num1=',num1)     //输出 初始num1=1  
fun1()                      //输出  函数修改后num1=2  
print('运行完函数后num1=',num1)  //输出   运行完函数后num1=2  
使用global关键字就是告诉python编译器这个变量不是局部变量而是全局  

def fun3():  
&emsp;num3 = 3  
&emsp;def fun33():   
&emsp;&emsp;nonlocal num3    //num3不是全局，只是fun33函数的外层变量，用global会报错，要用nonlocal.  
&emsp;&emsp;num3+=3  
&emsp;&emsp;print('num3=',num3)  //输出  num3=6  
&emsp;return fun33()  
fun3()  

#### 闭包  
在一个函数中定义了一个内函数，内函数里运用了外函数的临时变量，并且外函数的返回值是内函数的引用，这样就构成了一个闭包。  
def outer(a):  
&emsp;b = 10  
&emsp;def inner():  
&emsp;&emsp;print(a+b)  
&emsp;return inner  
if __name__=='__main__':  
 &emsp;demo = outer(5)  
 &emsp;demo()      //输出15  
 &emsp;demo2 = outer(7)  
 &emsp;demo2()  输出   17    

#### lambda 表达式  
def s(x):  
&emsp;return 2*x+1  

lambda写法  
a = labda x:2*x+1
a(5)   //输出  11

可以多个参数
b = labda x,y,z:x + y +z  
prirnt(b(3,4,5))  


#### 递归  
在函数内部，可以调用其他函数。如果一个函数在内部调用自身本身，这个函数就是递归函数  
递归就是函数调用自身的这么一个行为  

非递归求阶乘  
def jiecheng():  
&emsp;result =n  
&emsp;for i in range(1,n):  
&emsp;&emsp;result *=i  
&emsp;return result  

num = int(input('输入'))  
result = jiecheng(num)  
print("%d 的阶乘是:%d" % (num,result))  


递归求 :   
def factorial(n):  
&emsp;if n ==1:  
&emsp;return 1  
&emsp;else:  
&emsp;&emsp;return n * factorial(n-1)  

num = int(input('输入'))  
result = jiecheng(num)  
print("%d 的阶乘是:%d" % (num,result)) 

符合两个条件：1，有调用函数自身的行为；2，有一个正确的返回条件。  

斐波那契  
def fab(n):  
&emsp;n1=1  
&emsp;n2=1  
&emsp;n3=1  
&emsp;if n<1:  
&emsp;&emsp;print(‘输入有误‘)  
&emsp;&emsp;return -1  
&emsp;while (n-2)>0:  
&emsp;&emsp;n3 = n2 + n1  
&emsp;&emsp;n1 = n2  
&emsp;&emsp;n2 = n3  
&emsp;&emsp;n -= 1  
&emsp;eturn n3  

result = fab(20)  
if result != -1:  
&emsp;print(‘共有%d对兔子诞生‘ % result)  

用递归  
def fab(n):  
&emsp;if n<1:  
&emsp;&emsp;print("输入有误")  
&emsp;&emsp;return -1  
&emsp;if n == 1 or n == 2:  
&emsp;&emsp;return 1  
&emsp;else:  
&emsp;&emsp;return fab(n-1) + fab(n-2)  
result = fab(20)  
if result !=1:  
&emsp;print("共有%d对兔子诞生" % result)  









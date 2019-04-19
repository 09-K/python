对象 = 属性 + 方法  把静态的特征称之为属性，而把动态的动作称之为方法  

面向对象特征：封装、继承、多态  
列表有很多方法供我们使用，但是我们不知道这些方法里边时如何实现的、方法里有哪些变量，这就是所谓的封装   
继承：子类自动共享父类之间数据和方法的机制;吐火子类中定义与父类同名的方法或属性，则会自动覆盖父类对应的方法和属性  
多态：不同对象对同意方法响应不同的行动  

class Hello:&emsp;&emsp;//创建类 ，类名约定用大写开头  
&emsp;def sayhello(self):  
&emsp;&emsp;print('hello;')  

h = Hello()&emsp;类的实例  
h.sayhello()  

class Hi(Hello):&emsp;//继承Hello类  


class Mylist(list):&emsp;//继承list类  
&emsp;pass  
list2 = Mylist()  
list2.append(5)&emsp;//list2也就继承了list的方法  

#### self是什么  
self只有在类的方法中才有，独立函数或方法是不必带有self的，self在定义类的方法时是必须有的；self名称不是必须的，可以写成其他名字aa、name、b等都行，但是约定成俗。  
self指的是类实例对象本身，不是类本身 
```
class Ball:  
  def setName(self,name):  
    self.name = name  
  def kikl(self):  
    print('my name is %s:' % self.name)  

a = Ball()  
a.setName('A')  
b = Ball()  
b.setName('B')  
a.kikl()&emsp;//输出 my name is A  
b.kikl()&emsp;//输出 my name is B  
```
都是调用kikl()方法，输出却不一样，为什么？a.kikl()他有一个参数，他是隐藏的，就是把a这个对象的标志传进去


#### 公有和私有  
默认对象的属性和方法都是公有的，可以通过点操作符进行访问  
在python中定义私有变量只需要在变量名或函数前加上 __ 两个下划线，那么这个函数或变量就会为私有的了。  

class Person:  
&emsp;name = 'AA'  
p = Person()    
p.name  



##### 组合  
所谓组合：把类的实例化放到一个新类里边，就是说把几个不是很有继承关系的放到一起  
```
class Gui:  
  def __init__(self,x):  
    self.num=x  
class Fish:  
  def __init__(self,x):  
    self.num=x  

class Pool:  
  def __init__(self,x,y):  
  self.gui = Gui(x)  把需要实例化的类放进来  
  self.fish = Fish(y)  
  def print_num(self):  
    print("有龟%d 只，鱼%d 条" % (self.gui.num,self,fish.num)  
```

##### 一些相关的BIF  
issubclass(class,classinfo)  //第一个参数是第二个参数的子类，返回ture  
1,一个类被认为是自身的子类   
2，classinfo可以是类对象组成的元组，只要class与其中任何一个候选类的子类，则返回ture  
\>>> class A:  
	pass  
\>>> class B(A):  
	pass  
\>>> issubclass(B,A)  
True  
\>>> issubclass(B,B)  
True  

isinstance(object,classinfo)//第一个对象传入一个实例对象，第二传入一个类；检查一个实例对象是否属于一个类的  
1，如果第一个参数不是对象，则永远返回false  
2,如果第二个参数不是有类或者由类对象组成夫人元组，会抛出typeError异常  
\>>> isinstance(b1,B)  
Trueb&emsp;//1是B的实例化对象,所以ture  
\>>> isinstance(b1,A)  
True&emsp;因为B类 继承A类  


hasattr(object,name)//测试一个对象，里边是否有指定的属性  
\>>> class C:  
&emsp;def __init__(self,x=0):  
&emsp;&emsp;self.x=x  	     
\>>> c1=C()  
\>>> hasattr(c1,'x')&emsp;//属性名要有引号  
True  

getattr(object,name[,defult])//返回对象指定的属性值，如果指定的属性不存在，若设置了defult，会把defult打印出来，否则抛出异常  
\>>>getadttr(c1,'x')  
0  
\>>>getattr(c1,'a',"属性不存在返回defult...")  
'属性不存在返回defult...'  

setattr(object,name,value)//可以设置指定属性的值，若属性不存在，会新建一个新的属性并给它赋值  
setattr(c1,'y','ok')

delattr(object,name)//删除对象中指定的属性，若属性不存在，则抛出异常  
delattr(c1,'y')  

property(fget=None,fset=None,fdel=None,doc=None)//通过属性来设置属性  

class A:  
&emsp;def __init__(self,size=10):  
&emsp;&emsp;self.size=size  
&emsp;def getSize(self):  
&emsp;&emsp;return self.size  
&emsp;def setSize(self,value):  
&emsp;&emsp;self.size=value  
&emsp;def delSize(self):  
&emsp;&emsp;del self.size  
&emsp;x= property(getSize,setSize,delSize)  

\>>>a1=C()  
\>>>a1.x  
10
\>>>a1.x=11  
\>>>del a1.x  































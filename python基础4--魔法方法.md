### 魔法方法  
python中，有一些内置好的特定的方法，这些方法在进行特定的操作时会自动被调用，称之为魔法方法  
\_\_new\_\_(cls[,..])//new__是在一个对象实例化的时候所调用的第一个方法，第一个参数是这个类，其他参数直接传递给__init__  

class C(str): //C继承字符串(不可改变的类)  
def new(cls,string):  
string=string.upper()  
return str.new(cls,string)  

\_\_init\_\_(self[,..])//构造器，当一个实例被创建的时候调用的初始方法；在创建实例对象为其赋值时使用。  
\_\_del\_\_(self) //析构器，当一个实例被销毁的时候调用的方法  

```
class A:  
  def new(self):  
    print('我是__init__,我被调用了..')  
  def del(self):  
    print('我是__del__,我被调用了..')  
\>>>a1=A()  
我是__init__,我被调用了..  
\>>>del a1  
我是__del__,我被调用了..  
```

```
__init__(self)  
把init方法称为构造方法  
class Ball:  
  def __init__(self,nmae):&emsp;//还可以把name参数设置为默认参数  
    self.name = name  
  def kikl(self):  
    print('my name is %s:' % self.name)  

b = Ball('AA')&emsp;//实例化对象的时候是可以传入参数的，参数会自动传到init方法中  
b.kikl()  
```

### 迭代器  
迭代的意思就类似于循环，每一次重复的过程就称之为迭代的过程，而每一次迭代的结果将用来作为下一次迭代的初始值，
那么提供迭代方法的容器我们称之为迭代器，通常我们接触的迭代器有 序列，字符串列表元组字典啊。  

我们通常呢使用for语句进行迭代  
```
for i in "abcdefg":  
  print(i)  //每一次迭代的过程把i打印出来
```
字符串是一个容器，同时也是一个迭代器,for语句的作用就是触发这个迭代器的迭代功能，每次从容器里边拿出一个数据，就是所谓的迭代操作。  

迭代操作，python提供了两个内置函数(BIF): iter()  ,   next()
![](https://github.com/19969/python/blob/master/img/diedai.PNG)


































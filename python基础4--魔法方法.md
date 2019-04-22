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

迭代操作，python提供了两个内置函数(BIF): iter()  , next()  
![](https://github.com/19969/python/blob/master/img/diedai.PNG)  
it 就是一个迭代器了，获得这个字符串容器的迭代器  


for语句，其实它是这么工作的
```
str = "abcdef"
it = iter(str)
while True:  
  try:
    each = next(it)
  except StopIteration:
    break
  print(each)
```

迭代器他的魔法方法有两个：  
\_\_iter\_\_()  
\_\_next\_\_()  
一个容器，如果是迭代器，必须实现__iter__()这魔法方法,这个方法实际上是返回迭代器本身，事实上就是return srlf  

```
class Fibs:
  def __init__(self):
    self.a = 0
    self.b = 1
  def __iter__(self):
    return self
  def __next__(self):
    self.a,self.b = self.b,self.a + self.b
    return self.a
    
fibs = Fibs()
for each in fibs:
  if each < 20:
    print(each)
  else:
    break
```


### 生成器  
生成器的学习并不涉及到高级的魔法方法，甚至巧妙的避开了类和对象，仅需要普通的函数就可以实现了  
迭代器需要我们去定义一个类和实现相关的方法才可以定义一个灵活的迭代器，  
而生成器，则需要在普通的函数里边加上一个yield语句  
```
def myGen():  
  print('生成器被执行')  
  yield 1  
  yield 2  
```
![](https://github.com/19969/python/blob/master/img/%E7%94%9F%E6%88%90%E5%99%A8.PNG)  
一旦一个函数里边出现 yield语句，那说明这函数被定义为生成器，yield呢相当于函数里边的return语句，  
但是普通函数它的return一返回那么这个函数就结束；但是呢，对于生成器来说，出现yield它就会把yield后边的参数给返回去，  
返回去之后，是暂停在这个yield这里。  
因为生成器是个特殊的迭代器，所以用next(g)  
没有元素的时候就抛出 StopIteration的异常  

  
列表推导式  
a = [i for i in range(50) if not(i%2) and i%3]   //不能被3整除但是能被2整除  
[2, 4, 8, 10, 14, 16, 20, 22, 26, 28, 32, 34, 38, 40, 44, 46]  

字典推导式  
b = {i:i % 2==0 for i in range(10)}  //是否为偶数  
{0: True, 1: False, 2: True, 3: False, 4: True, 5: False, 6: True, 7: False, 8: True, 9: False}  

集合推导式  
s = {i for i in [1,2,4,4,6,7,8,0,2]}  
{1,2,4,6,7,8,0}  


生成器推导式  
e = (i for i in range(10))  
next(e)  

生成器推导式作为函数的参数  
sum(i for i in range(100) if i %2)   //所有不能被2整除的 加起来  





























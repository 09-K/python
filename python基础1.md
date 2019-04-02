#### 简述
Python是一种程序设计语言，是一种动态的面向对象的脚本语言；<br>
发行时间：1991， 发行人:Guido van Rossum

#### 运算符
Python中的变量赋值不需要类型声明，<br>
A = 9<br>
B = ‘hello’ <br>
c = d =1<br>
x,y,z=2,3,”ppppp”<br>

运算符：+ - * /   %(取余)  **  //(取整)  <br> 
5除 2 ：  5/2  输出2.5<br>
5余2 ：   5%2  输出 1<br>
5取整2 :  5//2 输出 2<br>
Python2.x 里 整数除整数只能得出整数，如果要得到小数部分，把其中一个数改成浮点数即可<br>

###### 位运算
& 按位与   两个相应位为1则为1，<br>
|  按位或   有一个为1则为1<br>
^ 按位异或 两对应的二进位相异时，为1  
~ 取反     把1变0，0变1；如 ~6  
<<         左移n位，就是乘以2的n次方；   
\>>        右移n位，就是除以2的n次方  
5左移2 ： 5<<2  左移2位，就是乘以2的2次方，输出20  

#### 列表  
list1 = [1, 2, 3, 4, 5 ];   
list2 = ["a", "b", "c", 0，2];  

print (list1[:3])  //输出1，2，3  
print (list2[-4：-2])  //输出 b,c  

**列表的操作**
del list[2]            删除数据  
list+list2             列表相加  
list.append(‘hhh’)    添加数据到列表末尾，，，如果放两个参数的话会报错  
list.extend([‘bbbb’,’yyy’])   extend方法，括号里的要中括号  
list.insert(1,'mm’)    下标为1的位置，插入数据  
list.count(1)        统计某个元素在列表中出现的次数  
list.pop()         移除某个元素   
list.reverse()     反向列表中元素  
list.sort()       对列表进行排序，默认从小到大  
list.sort(reverse=true)  
列出所有方法：dir(list)  
 
 列表的比较  
List=[123]  
List2=[456]  
List>list2    //输出false  ,列表的比较近从0位开始，只要有一位比出了，后面的也就pass了  

列表里的列表  
List = [1,[‘ooooo’,’kk’],3]  
Print ‘list[1][1]’      输出 kk  
Print ‘list[1][0]’      输出 ooooo  

#### 元组
tup1 = (1.2, 'Runoob', 1997, 2000)  
tup2 = (1, )  只有一个元素时，要在元素后面加逗号  
tup3 = "a", "b", "c", "d"   # 不需要括号也可以  
tup = ()  空元组  

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合  
tup1 = (12, 34.56)  
tup2 = ('abc', 'xyz')                   
 tup3 = tup1 + tup2  
print(tup3)     
del tup1;       //元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组  

cmp(tup,tup2)   比较两个元素  

#### 字典
字典是另一种可变容器模型，且可存储任意类型对象；  
键必须是唯一的，但值则不必。值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。  
dict1 = { 'abc': 456 };  
dict2 = { 'abc': 123, 98.6: 37 };  

访问字典里的值  
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}   
print ("dict['Name']: ", dict['Name'])  
print ("dict['Age']: ", dict['Age'])  
dict['Age'] = 8;       # 更新   
Age dict['School'] = "菜鸟"   # 添加信息  
del dict['Name']     # 删除键 'Name'  
dict.clear()           # 清空字典  
del dict              # 删除字典  

不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住  


#### 集合
使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。  

basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}   
print(basket) # 这里演示的是去重功能   
{'orange', 'banana', 'pear', 'apple'}   
 'orange' in basket # 快速判断元素是否在集合内  
 True  
 'crabgrass' in basket  
False   
 #下面展示两个集合间的运算. ...  
a = set('abracadabra')   
b = set('alacazam')   
a   
{'a', 'r', 'b', 'c', 'd'}   
a - b # 集合a中包含而集合b中不包含的元素  
 {'r', 'd', 'b'}   
\>>> a | b # 集合a或b中包含的所有元素  
 {'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}  
\>>> a & b # 集合a和b中都包含了的元素   
{'a', 'c'}   
\>>> a ^ b # 不同时包含于a和b的元素  
{'r', 'd', 'b', 'm', 'z', 'l'}  


将元素 x 添加到集合 s 中  
thisset = set(("Google", "Runoob", "Taobao"))   
thisset.add("Facebook")     //add方法  
thisset.update({1,3})      //updata方法，参数可以是列表，元组，字典等  
print(thisset)  
输出{1, 3, 'Google', 'Taobao', 'Runoob'}  

thisset.remove("Taao") #将元素从集合中移除，如果元素不存在，则会发生错误  
thisset.discard("Fack"） #还有一个方法也是移除集合中的元素，且如果元素不存在，不会发生错误  
x = thisset.pop()    #设置随机删除集合中的一个元素  
print(x)  

len(thisset)  #计算集合元素个数。  
thisset.clear() #清空集合  

#### 循环
n = 100   
sum = 0   
counter = 1   
while counter <= n:   
    sum = sum + counter   
    counter += 1  
print("1 到 %d 之和为: %d" % (n,sum))  


**while 循环使用 else 语句**
count = 0   
while count < 5:   
    print (count, " 小于 5")   
    count = count + 1  
else:   
    print (count, " 大于或等于 5")  

**for**
sites = ["Baidu", "Google","Runoob","Taobao"]  
for site in sites:  
if site == "Runoob":   
    print("菜鸟教程!")   
        break   
    print("循环数据 " + site)   
else:   
    print("没有循环数据!")   
print("完成循环!")  


for i in range(0, 10, 3) :   
print(i)  

输出 0 3 6 9  

pass是空语句，是为了保持程序结构的完整性。pass 不做任何事情，一般用做占位语句  
while True: ... pass # 等待键盘中断  














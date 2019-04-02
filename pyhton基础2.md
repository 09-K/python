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






















想着 github.com/100  到 github.com/1000  内哪些可以。  
当然是看状态码，  
起先是用if判断code为200，但非200的就报错停止运行了，  
百度，用了try.  


import urllib.request  
import urllib.error  

url='https://github.com/'  
for i in range(100,1000):  
&emsp;req = urllib.request.Request(url+str(i))  
&emsp;try:  
&emsp;&emsp;response = urllib.request.urlopen(req)  
&emsp;&emsp;x = response.getcode()  
&emsp;&emsp;print(i)  
&emsp;except:  
&emsp;&emsp;print(str(i)+':404')


#### urllib访问网页  
``` 
import urllib.request
response = urllib.request.urlopen('http://www.runoob.com')
html = response.read().decode('utf-8')
print(html)
```

下载一只猫  
```
import urllib.request
response = urllib.request.urlopen('http://placekitten.com/g/500/600')
cat_img = response.read()
with open('cat.jpg','wb') as f:
  f.write(cat_ing)
```





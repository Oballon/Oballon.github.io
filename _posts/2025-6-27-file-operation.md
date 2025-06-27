---
title: "文件编程处理"
categories: [技术,文件处理]
pin: false
---


### 处理函数

#### 字符处理 
python<br>
#字符规范化
def standard(number):
    number_str=str(number)
    if len(number_str)==1:
        number_str='00'+number_str
    elif len(number_str)==2:
        number_str='0'+number_str
    elif len(number_str)==3:
        number_str=number_str
    
    return number_str

<br>

#### 获取文件大小并换行写入

```

#获取编号文件大小并换行写入
import os
def collect(diff_number):
    #diff_path = os.path.join("C:/Users/admin/Desktop/4964A", str(diff_number)+'.txt')
    size = os.path.getsize("C:/Users/admin/Desktop/4964A"+'/'+str(diff_number)+'.txt')

    with open("C:/Users/admin/Desktop/PY/diff_size.txt",'a') as f:
        f.write(str(size)+'\n')

#collect('001_002')

```

#### 正则表达式匹配目标字符

```
import re
#正则表达式检索文件中目标字符数量
def count(file_number_str,compare,folder_name):
    with open(folder_name+file_number_str+".txt",'rb') as f:
        binary_data = f.read()
        hex_data= binary_data.hex()
        pattern=re.compile(compare)
        matches=pattern.findall(hex_data)

    # print(file_number_str)
    # print(f"{file_number_str}.txt中匹配的内容: {matches}")
    print(f"{file_number_str}.txt中匹配的数量: {len(matches)}")

```

**腾讯AI开放平台语音合成**

操作文档：
- [腾讯AI开放平台](https://ai.qq.com/)
- [语音合成](https://ai.qq.com/product/aaitts.shtml)
- [技术文档 PHP](https://ai.qq.com/doc/aaitts.shtml)

操作面包屑导航：
控制台-创建应用-在应用管理找到应用信息里面的APPID APPKEY-首页技术引擎-语音合成-语音合成 

### 可复用腾讯AI开放平台语音合成API调用代码

```
# 调取代码修改必要参数直接使用

# -*- coding: utf-8 -*-
"""
Created on Mon Oct 21 20:57:24 2019

@author: HUI
"""
import time
from os import path
from urllib.request import urlopen
from urllib.parse import urlencode
from urllib.parse import quote_plus
import hashlib
import random
import base64

#生成sign 
def getReqSign(params,key):
    dict_kl = sorted(params)
    s = ''
    for k in dict_kl:
        v = params[k]
        if v != '':
            v0 = str(quote_plus(str(v))) 
            s = s + k + '=' + v0 + '&'
    s = s + 'app_key=' + key;          
    m = hashlib.md5() 
    m.update(s.encode("utf8"))
    sign = m.hexdigest()
    sign = sign.upper()
    print('sign:',sign)
    return sign
                                                      # 下面的1ID与KEY都是需要在控制台应用里面将语音合成能力库来接入能力才有权限
appid = '1000001'                                     # 换成自己的ID
appkey = 'a95eceb1ac8c24ee28b70f7dbba912bf'           # 换成自己的KEY
text = '腾讯ai语音合成'                                # 改变文本输入的内容，不能太长会容易请求失败
url = 'https://api.ai.qq.com/fcgi-bin/aai/aai_tts'
time_s = int(time.time())
m = hashlib.md5()
m.update(str(time_s).encode("utf8"))
nonce_s = m.hexdigest()
nonce_s = nonce_s[0:random.randint(1,31)]
params ={'app_id':appid,
         'speaker':'1',
         'format':'2',
         'volume': '0',
         'speed':'100',
         'text':text,
         'aht':'0',
         'apc':'58',
         'time_stamp':time_s,
         'nonce_str':nonce_s,
         'sign':''
         }
params['sign'] = getReqSign(params,appkey)
s = urlencode(params)
res = urlopen(url,s.encode()) #网络请求
res_str = res.read().decode()
res_dict = eval(res_str)
print('return result : ')
print('ret:',res_dict['ret'])
print('msg:',res_dict['msg'])

if res_dict['ret'] == 0:
    res_data = res_dict['data']
    res_data_format = res_data['format']
    res_data_speech = res_data['speech']
    res_data_md5sum = res_data['md5sum']
    filepath = path.dirname(__file__)  #目录                          # 必须更改为自己想要保存的目录下面，但是目录里面只能用/不能用\，否则下面以fout开头的三行代码会报错，三行是写入代码不可以删除，并且报错信息会是 ValueError: embedded null character
    file = '/wav01.wav'
    base64_data = res_data_speech
    ori_image_data = base64.b64decode(base64_data)
    fout = open(filepath+file, 'wb')
    fout.write(ori_image_data)
    fout.close()
    print("output file '",filepath,file,"' success")
print('over')

```


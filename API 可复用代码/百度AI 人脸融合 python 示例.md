百度大脑 AI开放平台 人脸融合API 操作文档：

- [百度大脑人脸融合官方文档](https://ai.baidu.com/ai-doc/FACE/5k37c1ti0)
- [错误码对照](https://ai.baidu.com/ai-doc/FACE/5k37c1ujz)

找到“Access Token 获取”。的文档

- [Access Token 获取](https://ai.baidu.com/ai-doc/REFERENCE/Ck3dwjhhu)

### 请求 token 代码

```
# 第一步先是来请求token
# access_token 的有效期为 30 天，切记需要每 30 天进行定期更换，或者每次请求都拉取新 token

# encoding:utf-8
import requests 

# client_id 为官网获取的AK=API Key， client_secret 为官网获取的SK=Secret Key
host = 'https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=【官网获取的AK】&client_secret=【官网获取的SK】'  # Key 不要用双引号括起来只是部分参数而已
response = requests.get(host)
if response:
    print(response.json())

```

### 可复用百度大脑人脸融合API调用代码

```
# encoding:utf-8

import requests

'''
人脸融合
'''

request_url = "https://aip.baidubce.com/rest/2.0/face/v1/merge"

params = "{\"image_template\":{\"image\":\"sfasq35sadvsvqwr5q...\",\"image_type\":\"BASE64\",\"quality_control\":\"NONE\"},\"image_target\":{\"image\":\"sfasq35sadvsvqwr5q...\",\"image_type\":\"BASE64\",\"quality_control\":\"NONE\"}}"
access_token = '[调用鉴权接口获取的token]'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/json'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())

```


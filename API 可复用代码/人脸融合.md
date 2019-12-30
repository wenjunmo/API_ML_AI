Face++ 人脸融合API 操作文档：
- [Face++ 人脸融合API使用文档](https://console.faceplusplus.com.cn/service/image/intro)
- [Merge Face API (V1):使用本 API，可以对模板图和融合图中的人脸进行融合操作](https://console.faceplusplus.com.cn/documents/20813963)

操作面包屑导航：Face++旷视 人工智能开放平台-技术能力-人像处理-人脸融合（点击会跳转到图像识别/功能的API里面，被归类为识物）




```
# 可复用代码-Face++ 人脸融合API

# 第一块
import requests  # 导入requests库

# 第二块
url= "https://api-cn.faceplusplus.com/imagepp/v1/mergeface"
key = "jjT7ZzAzwiHZ7bcVGicD6ajkER7YXsaH"
secret = "Vjo_hOWLd8GUcFV0d_tjGtlWf0nATCw-"                    # 3个必备的参数

files={
    'template_file':('mouluren.jpg',open(r'H:\Junior_Study\09_API_AI_ML_\week16\test\mouluren.jpg','rb')), 
    'merge_file':('xusong.jpg',open(r'H:\\Junior_Study\09_API_AI_ML_\week16\test\xusong.jpg','rb'))      
}

# requests 发送 / 上传多个文件，文档明确表示需要两个上传文件，一张模板图一张融合图，将使用requests上传本地文件

# 第三块

data={
    'api_key':key,
    'api_secret':secret,
}

rdata=requests.post(url,data,files=files)
rdata                                           # 返回post请求

rdata.json()                                    # 输出合成图片的base64


# 第四块——转换


import base64 

idata=base64.b64decode(rdata.json()['result'])
file=open('1.jpg','wb')
file.write(idata)
file.close()

```

报错信息参考：
- [Python 报错：SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3:，其实就是转义的问题就是需要//来进行转义](https://blog.csdn.net/caibaoH/article/details/78335094)
- [python 的 requests 发送 / 上传多个文件，看好字典类型的 files 参数的应用](https://blog.csdn.net/five3/article/details/74913742)
- [Python -- post 方式上传文件:
files = {'file': open('D:/test.apk', 'rb')}    ](https://blog.csdn.net/wudj810818/article/details/50903416)
- [base64 转图片 python python 将 base64 字符串还原成图片保存，代码简写](https://blog.csdn.net/QZC295919009/article/details/42712801)



```
# 不可复用代码-Face++ 人脸融合API

# -*- coding: utf-8 -*-
import urllib.request
import urllib.error
import time

http_url = 'https://api-cn.faceplusplus.com/facepp/v3/detect'
key = "填上你的KEY"
secret = "填上你的SECRET"
filepath = r"本地图片的路径"

boundary = '----------%s' % hex(int(time.time() * 1000))
data = []
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'api_key')
data.append(key)
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'api_secret')
data.append(secret)
data.append('--%s' % boundary)
fr = open(filepath, 'rb')
data.append('Content-Disposition: form-data; name="%s"; filename=" "' % 'image_file')
data.append('Content-Type: %s\r\n' % 'application/octet-stream')
data.append(fr.read())
fr.close()
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'return_landmark')
data.append('1')
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'return_attributes')
data.append(
    "gender,age,smiling,headpose,facequality,blur,eyestatus,emotion,ethnicity,beauty,mouthstatus,eyegaze,skinstatus")
data.append('--%s--\r\n' % boundary)

for i, d in enumerate(data):
    if isinstance(d, str):
        data[i] = d.encode('utf-8')

http_body = b'\r\n'.join(data)

# build http request
req = urllib.request.Request(url=http_url, data=http_body)

# header
req.add_header('Content-Type', 'multipart/form-data; boundary=%s' % boundary)

try:
    # post data to server
    resp = urllib.request.urlopen(req, timeout=5)
    # get response
    qrcont = resp.read()
    # if you want to load as json, you should decode first,
    # for example: json.loads(qrount.decode('utf-8'))
    print(qrcont.decode('utf-8'))
except urllib.error.HTTPError as e:
    print(e.read().decode('utf-8'))  
```

参考文档：
- [react-native 使用 Face++ 识别身份证，读取信息展示](http://www.pianshen.com/article/266759574/)
- [markdown：API 编写模板](https://blog.csdn.net/weixin_33871366/article/details/94609694)
- [C语言写的 FacePlusPlus，“error_message”：“ MISSING_ARGUMENTS：api_key”，带有 React Native 提取请求](https://stackoverflow.com/questions/48652293/faceplusplus-error-message-missing-arguments-api-key-with-react-native-f?rq=1)
- [非常详细的教程用Face++来人脸融合 手把手教学](http://help.ih5.cn/question/3276.html)
- [纯前端实现人脸融合 - 调用 Face++ 的人脸融合 API 接口实现 用C来写得](https://blog.csdn.net/gaofei880219/article/details/80805558)

操作问题：
- 查看以上官方文档，无论如何调用都是缺少参数，"error_message":"MISSING_ARGUMENTS: merge_url, merge_file, merge_base64"}
- 回到最终的API调用文档中来，好好观察看出问题出现的地方是在哪里
1. 调用的API入门测试的文档这个不是一成不变的必须要来依靠示例来进行修改并且知道是什么样子的参数调用才可以来进行使用，第一次直接就是调用了原始文档，吧并且将人脸融合的示例文档来进行添加就是没有办法还是报错：缺少必要的参数"error_message":"MISSING_ARGUMENTS: merge_url, merge_file, merge_base64"}
2. 修改参数名称和参数的位置，仔细观察data的书写方式只有一个是上传文件，但是人脸融合必须是有一个模板图一个融合图是上传两个图片猜对，但是将data的fe修改后也同样是不可以，，所以说文档代码示例给得不明不白必须是自己要学会使用requests库来进行调用，不能够依靠初始的API调用代码
3. Face++在 @煜华 帮助下来重写requests的调用




百度大脑 AI开放平台 人脸融合API 操作文档：

- [百度大脑人脸融合官方文档](https://ai.baidu.com/ai-doc/FACE/5k37c1ti0)
- [错误码对照](https://ai.baidu.com/ai-doc/FACE/5k37c1ujz)

找到“Access Token 获取”。的文档
- [Access Token 获取](https://ai.baidu.com/ai-doc/REFERENCE/Ck3dwjhhu)


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



- [Python3 - 中把图片进行 - base64 - 编码-用了这个](https://blog.csdn.net/CoderPai/article/details/80222947)
- [诡异错误一： ValueError: embedded null character](https://blog.csdn.net/quintind/article/details/77371402)
- [Python 将图片转换为 base64 编码](https://blog.csdn.net/J__Max/article/details/82424551)




```
# 可复用百度大脑人脸融合API调用代码

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

在一系列的操作后就是出现了 {'error_code': 6, 'error_msg': 'No permission to access data'} 没有权限，
 
 >![没有权限](https://images.gitee.com/uploads/images/2019/1224/205142_8a4f8fb4_1831543.png "屏幕截图.png")
 
- [【应用勾选】AI 应用如何查看是否勾选](https://ai.baidu.com/forum/topic/show/492868)
- [{"error_msg":"No permission to access data","error_code":6} 处理方案](https://www.cnblogs.com/erph/p/9186204.html)
 

提交工单来进行处理，反馈挺快的要求重新获取token，返回就是直接来返回json格式了











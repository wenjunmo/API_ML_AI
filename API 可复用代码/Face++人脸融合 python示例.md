Face++ 人脸融合API 操作文档：

- [Face++ 人脸融合API使用文档](https://console.faceplusplus.com.cn/service/image/intro)
- [Merge Face API (V1):使用本 API，可以对模板图和融合图中的人脸进行融合操作](https://console.faceplusplus.com.cn/documents/20813963)

操作面包屑导航：Face++旷视 人工智能开放平台-技术能力-人像处理-人脸融合（点击会跳转到图像识别/功能的API里面，被归类为识物）


### 可复用代码-Face++ 人脸融合API

```
# 直接拷贝到本地端并且按照提示参数进行修改即可

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



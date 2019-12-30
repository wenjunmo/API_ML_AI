
**腾讯AI开放平台语音合成**

操作文档：
- [腾讯AI开放平台](https://ai.qq.com/)
- [语音合成](https://ai.qq.com/product/aaitts.shtml)
- [技术文档 PHP](https://ai.qq.com/doc/aaitts.shtml)

操作面包屑导航：
控制台-创建应用-在应用管理找到应用信息里面的APPID APPKEY-首页技术引擎-语音合成-语音合成 

参考文档：
- [吐槽腾讯语音合成python 腾讯语音合成](https://www.cnblogs.com/zepc007/p/10360557.html)
- [良心博主：Python 调用腾讯 API 合成语音](https://www.codeleading.com/article/72342390067/)
- [上面文章的CSDN出处](https://blog.csdn.net/hui_0_/article/details/102675804)

实验心得:
参考良心博主的代码说明
1. 需要去官网 https://ai.qq.com/ 创建应用，得到 APPID 和 APPKEY，然后将代码中默认的 appid = '1000001’和 appkey = 'a95eceb1ac8c24ee28b70f7dbba912bf’替换一下。
2. text 是想要被转换成语音的文字，这个文字似乎不能太长，否则特别容易请求失败。
3. 如果一切正常，会在代码所在目录下新增一个 wav 格式的音频文件，这个就是返回的腾讯合成的音频。
4. 有时候会提示‘system busy, please try again later’，原因暂时不清楚。

改好后要来对参数进行查看报错信息参考文档：
- [异常处理](https://ai.qq.com/doc/returncode.shtml)
- 完成后出现了ret: 16389查看异常处理是因为缺失 API 权限 请检查应用是否勾选当前 API 所属接口的权限 应该是接口没有被允许，所以要返回控制台为应用来添加能力库，在能力库里面找到语音合成并且点击接入能力到该创建的应用下面才可以调用权限
- 完成后出现了ret: -2147483634是表示系统出错，例如网络超时，那就来刷新一下还是msg: system busy, please try again later
- 退出来再来刷新一遍就是成功但是还是会报错：ret: 0 msg: ok 68     filepath = path.dirname(__file__)  #目录 NameError: name '__file__' is not defined 目录没有被定义就是我没有定义好目录在哪里，
- 定义好后又发现诡异的报错：fout = open(filepath+file, 'wb'       ValueError: embedded null character
- 这是写入文件的内容而不是可以乱删除，可能是文件的路径/\的区别
- [诡异错误一： ValueError: embedded null character](https://blog.csdn.net/quintind/article/details/77371402)

所以就是这样子的区别：

1. 通过测试，确定错误确实是文件读取语句；
2. 是否是文件中包含 null 字符呢？用 ultraedit 工具用 16 进制形式检查数据文件，没有发现有 null 字符；
3. 是否是因为 Windows 中的编码和 python 中的编码形式不一样造成的呢？查看到文件编码为 GBK 格式，但 python 是可以正确读取 GBK 文件的，试了其它 GBK 文件，读取没有任何问题；
4. 是不是因为文件名太长？把数据文件放在当前文件夹下，尝试读取确实没有问题。但真的是文件名太长的原因吗？这时候我才发现文件名中有个 ‘\0’ ，才如梦初醒。
注意：一般情况下，Python 解释器会将遇到的‘\’识别为路径，会自动增加一个’\’以便和转义字符进行区分，但若遇到转义字符则不增加‘\’。
例如：上述文件名将被转换为 F:\eclipse_workspace\machine_learning_example\Ch02\trainingDigits\0_38.txt。因而出错。
文件路径中若包含‘\0’、’\t’ 等特殊转义字符时要特别注意。
推荐文件路径写法：

>F:/eclipse_workspace/machine_learning_example/Ch02/trainningDigits/0_38.txt ，斜杠反过来了，这样就不会出现歧义了。
>F:\eclipse_workspace\machine_learning_example\Ch02\trainningDigits\0_38.txt

在 stackoverflow АлексейСеменихин的回答也是一样-似乎您在使用字符 “\” 和 “ /” 时遇到了问题。 如果您在输入中使用它们 - 尝试将它们更改为另一种.. [使用 open（）时出现 “ValueError：嵌入的空字符”](https://stackoverflow.com/questions/33977519/valueerror-embedded-null-character-when-using-open/33981557)



```
# 可复用腾讯AI开放平台语音合成API调用代码

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






百度大脑 AI开放平台语音合成

操作文档：
- [百度大脑 AI开放平台](https://ai.baidu.com/)
- [在线合成API接口](https://ai.baidu.com/ai-doc/SPEECH/Gk38y8lzk)
- [有官网的demo语音合成示例代码，python-Baidu-AIP/speech-demo](https://github.com/Baidu-AIP/speech-demo/tree/master/rest-api-tts)
- [百度语音合成python代码下载](https://github.com/Baidu-AIP/speech-demo/tree/master/rest-api-tts/python)
- [直接点击就是可以来进行查看复制粘贴](https://github.com/Baidu-AIP/speech-demo/blob/master/rest-api-tts/python/tts.py)

操作面包屑路径：
开放能力-语音合成-在线语音合成-技术文档
登录百度大脑AI开放平台-控制台-语音技术-创建应用-管理应用-APIID API Key Secret Key 三个资料

参考文档：
[Python 人工智能之路 - 第二篇：算法实在太难了有现成的直接用吧 进阶版的百度云语音合成](http://www.uml.org.cn/python/201911293.asp) 没有采用这个

```
# 可复用百度大脑 AI开放平台语音合成API调用代码 

# coding=utf-8
import sys
import json

IS_PY3 = sys.version_info.major == 3
if IS_PY3:
    from urllib.request import urlopen
    from urllib.request import Request
    from urllib.error import URLError
    from urllib.parse import urlencode
    from urllib.parse import quote_plus
else:
    import urllib2
    from urllib import quote_plus
    from urllib2 import urlopen
    from urllib2 import Request
    from urllib2 import URLError
    from urllib import urlencode

API_KEY = '4E1BG9lTnlSeIf1NQFlrSq6h'                        # 修改API KEY
SECRET_KEY = '544ca4657ba8002e3dea3ac2f5fdd241'             # 修改SECRET_KEY

TEXT = " 欢迎使用百度语音合成。"                              # 修改需要语音合成的文本

# 发音人选择，基础音库：0 为度小美，1 为度小宇，3 为度逍遥，4 为度丫丫，
# 精品音库：5 为度小娇，103 为度米朵，106 为度博文，110 为度小童，111 为度小萌，默认为度小美 
PER = 4
# 语速，取值 0-15，默认为 5 中语速                             # 要调好缩进
SPD = 5
# 音调，取值 0-15，默认为 5 中语调
PIT = 5
# 音量，取值 0-9，默认为 5 中音量
VOL = 5
# 下载的文件格式，3：mp3 (default) 4： pcm-16k 5： pcm-8k 6. wav
AUE = 3

FORMATS = {3: "mp3", 4: "pcm", 5: "pcm", 6: "wav"}
FORMAT = FORMATS[AUE]

CUID = "123456PYTHON"

TTS_URL = 'http://tsn.baidu.com/text2audio'


class DemoError(Exception):
    pass


"""  TOKEN start """

TOKEN_URL = 'http://openapi.baidu.com/oauth/2.0/token'
SCOPE = 'audio_tts_post'  # 有此 scope 表示有 tts 能力，没有请在网页里勾选


def fetch_token():                                             # 要调好缩进
    print("fetch token begin")
    params = {'grant_type': 'client_credentials',
              'client_id': API_KEY,
              'client_secret': SECRET_KEY}
    post_data = urlencode(params)
    if (IS_PY3):
        post_data = post_data.encode('utf-8')
    req = Request(TOKEN_URL, post_data)
    try:
        f = urlopen(req, timeout=5)
        result_str = f.read()
    except URLError as err:
        print('token http response http code : ' + str(err.code))
        result_str = err.read()
    if (IS_PY3):
        result_str = result_str.decode()

    print(result_str)
    result = json.loads(result_str)
    print(result)
    if ('access_token' in result.keys() and 'scope' in result.keys()):
        if not SCOPE in result['scope'].split(' '):
            raise DemoError('scope is not correct')
        print('SUCCESS WITH TOKEN: %s ; EXPIRES IN SECONDS: %s' % (result['access_token'], result['expires_in']))
        return result['access_token']
    else:
        raise DemoError('MAYBE API_KEY or SECRET_KEY not correct: access_token or scope not found in token response')


"""  TOKEN end """

if __name__ == '__main__':
    token = fetch_token()
    tex = quote_plus(TEXT)  # 此处 TEXT 需要两次 urlencode
    print(tex)
    params = {'tok': token, 'tex': tex, 'per': PER, 'spd': SPD, 'pit': PIT, 'vol': VOL, 'aue': AUE, 'cuid': CUID,
              'lan': 'zh', 'ctp': 1}  # lan ctp 固定参数

    data = urlencode(params)
    print('test on Web Browser' + TTS_URL + '?' + data)

    req = Request(TTS_URL, data.encode('utf-8'))
    has_error = False
    try:
        f = urlopen(req)
        result_str = f.read()

        headers = dict((name.lower(), value) for name, value in f.headers.items())

        has_error = ('content-type' not in headers.keys() or headers['content-type'].find('audio/') < 0)
    except  URLError as err:
        print('asr http response http code : ' + str(err.code))
        result_str = err.read()
        has_error = True

    save_file = "error.txt" if has_error else 'result.' + FORMAT
    with open(save_file, 'wb') as of:
        of.write(result_str)

    if has_error:
        if (IS_PY3):
            result_str = str(result_str, 'utf-8')
        print("tts api  error:" + result_str)

    print("result saved as :" + save_file)


```





```
# 可复用百度大脑 AI开放平台语音合成API调用代码注意事项

测试试流程
修改 tts.py
从网页中申请的应用获取 appKey 和 appSecret

# 填写网页上申请的appkey 如 API_KEY="g8eBUMSokVB1BHGmgxxxxxx"
API_KEY = '4E1BG9lTnlSeIf1NQFlrxxxx'

# 填写网页上申请的APP SECRET 如 SECRET_KEY="94dc99566550d87f8fa8ece112xxxxx"
SECRET_KEY = '544ca4657ba8002e3dea3ac2f5fxxxxx'
运行 tts.py，进行合成
命令为 python tts.py

结果在 result.mp3，如果遇见错误，结果在 error.txt

其中

Content-Type: audio/mp3，表示合成成功，可以播放 MP3 result.mp3
Content-Type: application/json 表示错误 error.txt 打开可以看到错误信息的 json
修改合成参数
TEXT = "欢迎使用百度语音";

# 发音人选择, 基础音库：0为度小美，1为度小宇，3为度逍遥，4为度丫丫，
# 精品音库：5为度小娇，103为度米朵，106为度博文，110为度小童，111为度小萌，默认为度小美 
PER = 0;
#语速，取值0-9，默认为5中语速
SDP = 5;
#音调，取值0-9，默认为5中语调
PIT = 5;
#音量，取值0-9，默认为5中音量
VOL = 5;

CUID = "123456PYTHON";

```


方法2
还有一种来生成python 的百度语音合成方法智能语音，这个也是百度云的项目第一种实现方式，百度云来调取API来进行语音合成，其实获取ID等之类的和上面的文档是一样的，百度大脑的后台就是百度智能云是一样的道理，查看的路径也是一样就是在应用管理里面来查看就是一样的

- [百度智能云](https://cloud.baidu.com/)
- [Python 实现百度云API语音合成](https://www.codeleading.com/article/89462502729/;jsessionid=51D7386B97ED1DE97DB1033D1A6D7047)

```

# 可复用百度大脑 AI开放平台语音合成API调用代码 

from aip import AipSpeech # 在导入模块之前一定要查看是否已经有此模块，没有就是要来下载百度云的API SDK ，在jupyternotebook 就是打开 在anoconda prompt 来 pip install baidu-aip


""" 你的 APPID AK SK """
# 去百度云申请一个账号然后创建API接口              # 就是你要新建应用才能查看下面三种东西
APP_ID = 'your_APP_ID'                          # 你的APP_ID
API_KEY = 'your_API_KEY'                        # 你的API_KEY
SECRET_KEY = 'your_SECRET_KEY'                  # 你的SECRET_KEY

client = AipSpeech(APP_ID, API_KEY, SECRET_KEY)

text = input("请输入转换为语音的文字：")          # 这个是输入框，不要改动，是在代码运行后输入你想要转换为语音的文字，比如：我是产品小白
result = client.synthesis(text, 'zh', 1, {
    'vol': 5,
    'spd': 5,
    'pit': 5,
    'per': 3,
})
outfile = input("请输入音频输出路径(绝对路径，类似于F:\xxx.mp3)： ")   # 这个也是输入框，但是你可以填想要保存文件的路径请输入音频输出路径(绝对路径，类似于F:\xxx.mp3)，但是代码运行后就是在输入框里面写上要生成的音频文件的全称及后缀比如：测试.mp3

# 识别正确返回语音二进制 错误则返回dict 参照下面错误码
if not isinstance(result, dict):
    with open(outfile, 'wb') as f:
        f.write(result)
input("转换成功!")                                                   # 产生结束后要来输入一句话，最后会输出这句话来结束整个流程


```

第一次是报错没有API这个模块所以就是要来导入，他应该是有使用了sdk python
安装使用 Python SDK 有如下方式：
如果已安装 pip，执行 pip install baidu-aip 即可。试试
在anoconda prompt 来 pip install baidu-aip
现在下载 baidu-aip 的 sdk才可以来调用模块
所以下载好后就是重新来运行代码



方法3

参考文档：
[博客来源 百度云实现语音识别及语音合成](https://blog.csdn.net/weixin_38241876/article/details/84949534)


```
# 可复用百度大脑 AI开放平台语音合成API调用代码

from aip import AipSpeech
 
""" 你的 APPID AK SK """
APP_ID = '15079673'
API_KEY = 'mGxvq3Nwr3aVjD4UFIFGsaMD'
SECRET_KEY = 'YIN3wxizj16zCRYZ6EGpdopuA6FwHRhB'
 
client = AipSpeech(APP_ID, API_KEY, SECRET_KEY)
result  = client.synthesis('欢迎入住酒店，祝您入住愉快', 'zh', 1, {
    'vol': 5,
})
 
# 识别正确返回语音二进制 错误则返回dict 参照下面错误码
if not isinstance(result, dict):
    with open('test.mp3', 'wb') as f:
        f.write(result)


```




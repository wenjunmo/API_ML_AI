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


### 可复用百度大脑 AI开放平台语音合成API调用代码  方法一
```
# 直接调用代码修改必要参数

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




### 可复用百度大脑 AI开放平台语音合成API调用代码 方法一 注意事项

```


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



### 可复用百度大脑 AI开放平台语音合成API调用代码  方法二
```

# 直接调用代码修改必要参数

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

### 可复用百度大脑 AI开放平台语音合成API调用代码 方法二 注意事项

```

第一次是报错没有API这个模块所以就是要来导入，他应该是有使用了sdk python
安装使用 Python SDK 有如下方式：
如果已安装 pip，执行 pip install baidu-aip 即可。试试
在anoconda prompt 来 pip install baidu-aip
现在下载 baidu-aip 的 sdk才可以来调用模块
所以下载好后就是重新来运行代码
```

### 可复用百度大脑 AI开放平台语音合成API调用代码 方法三 



```

# 直接调用代码修改必要参数

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









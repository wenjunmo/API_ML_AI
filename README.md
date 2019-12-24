<div align="center">
  <h1>:whale2: Project Name：想念 :whale2:</h1>
  <p>基于微信平台开发的 智能毕业纪念相册 APP</p>
  <p>Seeking True from Fact 网新人，有态度，不认输，不头秃</p>
</div>

> PRD 价值主张设计（目标：多层次多长度版本）
> 1. 一句话版本<br>
    此款 **智能毕业纪念册** APP 通过调取 **人脸融合API** 与 **语音合成API** ，用户只需将本地照片与个性化本人语音上传，APP 会直接合成含有语音的智能暂时匿名化照片，发布在“ **你合我猜** ”游戏模块，当猜对一张照片上传者名字即可解锁上传者的校园资料，秉持用游戏改变纪念形式的态度做出不一样的纪念相册。
> 2. 一分钟60s版本 (图文线上可阅读含可查连结)<br>
    这款 **智能毕业纪念册** APP 调取 **Face++** 人像处理中的 **人脸融合API** 与 **科大讯飞** 语音识别中的 **语音合成** 来实现 **你合我猜** 游戏化模块。用户只需将需要进行融合处理的照片和需要语音合成的个人语音上传至 APP，程序会依照个人喜好来合成新语音照片，可选择发布在 APP 特色功能的“ **你合我猜** ” 游戏模块。只有当对方猜对了合成后语音照片的人名后才能够解锁照片所属同学的校园资料。该 APP 抓住 **你对身边朋友的了解程度如何** 的痛点心理，推出 “**你合我猜**” 模块，并绘制 **最小可行性产品原型** ，减少同学之间 **见面不认人** 的尴尬处境。
> 3. 400 秒版本 Pecha Kucha 20x20 版本 (线上投影片含可查连结)<br>

## Product Documentation(产品需求文档)

|标题|内容|
|----|---|
|产品名称(Product Name)|想念|
|文档作者(Document Owner)|莫文俊|
|产品经理(Product Manager)|莫文俊|
|交互设计师(Interaction Designer)|莫文俊|
|软件工程师(Software Engineer)|莫文俊|
|测试运维师(Test Operation and Maintenance Division)|莫文俊|
|发布日期(Release Date)|2019.12|
|发布版本(Release Version)|v5.0|
|体验环境(Release Version)|iOS11|

- 版本修订记录

|修订版本号|迭代日期|修订内容|迭代者|
|---------|-------|--------|-----|
|v1.0|11.20-12.01|文档初稿撰写，建立基本产品文档框架，添加重要产品理念与技术开发项目流程|莫文俊|
|v2.0|12.01-12.08|测试可用 API 并进行可用性测试比对，进行市场回访调查|莫文俊|
|v3.0|12.08-12.15|选定 API 类型并实现测试运行，产品后台代码实现可用|莫文俊|
|v4.0|12.15-12.22|开发 APP 原型，制作低保真原型初步实现逻辑|莫文俊|
|v5.0|12.23-     |产品上线并进行不断功能反馈|莫文俊|

## Documentation Directory(文档目录)

- [产品介绍](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D)
- [市场背景](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#%E5%B8%82%E5%9C%BA%E8%83%8C%E6%99%AF)
- [价值主张设计](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#%E4%BB%B7%E5%80%BC%E4%B8%BB%E5%BC%A0%E8%AE%BE%E8%AE%A1)
  - [加值宣言](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E5%8A%A0%E5%80%BC%E5%AE%A3%E8%A8%80)
  - [核心价值宣言](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E6%A0%B8%E5%BF%83%E4%BB%B7%E5%80%BC%E5%AE%A3%E8%A8%80)
  - [用户痛点宣言](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E7%94%A8%E6%88%B7%E7%97%9B%E7%82%B9%E5%AE%A3%E8%A8%80)
  - [人工智能概率性与用户痛点](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD%E6%A6%82%E7%8E%87%E6%80%A7%E4%B8%8E%E7%94%A8%E6%88%B7%E7%97%9B%E7%82%B9)
  - [需求列表与人工智能API加值](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E9%9C%80%E6%B1%82%E5%88%97%E8%A1%A8%E4%B8%8E%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BDapi%E5%8A%A0%E5%80%BC)
- [原型](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#%E5%8E%9F%E5%9E%8B)
  - [交互及界面设计](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BA%A4%E4%BA%92%E5%8F%8A%E7%95%8C%E9%9D%A2%E8%AE%BE%E8%AE%A1)
  - [信息设计](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BF%A1%E6%81%AF%E8%AE%BE%E8%AE%A1)
  - [原型文档](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E5%8E%9F%E5%9E%8B%E6%96%87%E6%A1%A3)
  - [口头操作说明](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E5%8F%A3%E5%A4%B4%E6%93%8D%E4%BD%9C%E8%AF%B4%E6%98%8E)
- [API 产品使用关键AI或机器学习之API的输出入展示](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#api-%E4%BA%A7%E5%93%81%E4%BD%BF%E7%94%A8%E5%85%B3%E9%94%AEai%E6%88%96%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E4%B9%8Bapi%E7%9A%84%E8%BE%93%E5%87%BA%E5%85%A5%E5%B1%95%E7%A4%BA)
  - [使用水平](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BD%BF%E7%94%A8%E6%B0%B4%E5%B9%B3)
  - [使用比较分析](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BD%BF%E7%94%A8%E6%AF%94%E8%BE%83%E5%88%86%E6%9E%90)
  - [使用后风险报告](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E4%BD%BF%E7%94%A8%E5%90%8E%E9%A3%8E%E9%99%A9%E6%8A%A5%E5%91%8A)
  - [加分项](https://github.com/wenjunmo/API_ML_AI_SmartMemorial#--%E5%8A%A0%E5%88%86%E9%A1%B9)


## :sparkles: 产品介绍

> “我们，重新定义毕业纪念册”<br>
> “想念，是好久不见的表达”
> “想念，恋你的颜和言”

本软件基于人脸融合和语音合成研发的智能毕业纪念册，适用于任何想快速生成个性化毕业纪念册图集与校友连结的通讯录用户，不再为毕业后各自分飞而找不到联系方式而苦恼，不再为电子相册保存平台过多整理繁琐以及扫码失效，游戏化模块组件 “**你合我猜**” 更是能够解决多年老友不相见而健忘的尴尬场景，主打游戏化解锁新合成语音照片，在享受猜脸乐趣同时回忆逝去的青春美好。

## :sparkles: 市场背景

通过调查研究发现，移动互联网端以及通讯设备的普及，市面上新型毕业纪念册大部分都是基于上传图片形成个人图片库，搭配个性化音乐来产出音乐纪念相册，观赏性用大于实际联系性用。在高速发展的信息时代，信息不再局限于文本格式，相较于传统纸质毕业纪念相册，更多的是伴随着语音信息和影像信息，纸质媒介渐渐被人遗忘。<br>
APP 形式无疑是一种可以涵盖更多不同信息形式的新型毕业纪念册，在进行了人脸融合和语音合成API的调取后生成，而使用游戏化模块的智能毕业纪念相册会更有实际意义。

:star: **优势**

>- 涵盖多样化信息（ 相较传统纸质纪念册），使用便捷性提高（相较于网页版）
>- 市场上占比少可忽略，而大多数 APP 纪念册多为个人开发专用，忽视大多数大学生群体的市场，市场有待进一步扩张
>- 大部分产品功能设计往全社交类方向进行引导，模糊了本身的产品定位，阻碍发展

:star: **竞品分析**

>1. 竞品一：微吾H5自助工具制作毕业纪念册<br>
优点：<br>
>- 采用接龙的形式进行信息收集、纪念册制作。将工作量平摊到每个人，每人负责完成自己的纪念模块
>- 无需下载软件，接收链接或二维码编辑者，可个人和集体编辑，可随时随地欣赏分享
>- 更新方便及时，易于维护，可转换成电子书下载成pdf
>- 互相赠言，还有很邪恶的悄悄话功能<br>
缺点：<br>
- 停留在传统毕业纪念册，没有科技感，信息留存较少<br>

>2. 竞品二：时光流影网站<br>
优点:<br>
>- 直接上传图片进行模板个性化定制设计，有成熟模板供选择
>- 分享链接与生成二维码<br>
缺点:<br>
>- 网页编辑不容易，没有轻便和简洁，更新慢<br>

>3. 竞品三：微信公众号微影相册<br>
优点:<br>
>- 直接选择手机里的照片，然后选主题模板滤镜音乐，就能做出来影集了
>- 支持一键保存在手机内存中<br>
缺点:<br>
>- 没有分享功能，只能直接发送不够方便，没有乐趣模块只有简单的纪念留存<br>

:star: **设计用户调查问卷**

>1. 对纪念大学生生涯和同学友谊最有意义的形式是：毕业纪念册、聚餐、拍视频照片、送礼物
>2. 假如推出个性定制化毕业纪念册会买吗：很有意义，买、内容设计吸引，考虑买、不买，浪费钱
>3. 买毕业纪念册看重哪一种因素：设计新颖、内容丰富、流行
>4. 考虑的性价比有哪些因素：价格贵质量好但便于保存、价格适中质量过得去、价格便宜普遍接受没有很大需求、价格无所谓没有要求
>5. 毕业纪念册的价格多少可以接受：10-30、30-60、60-100
>6. 购买毕业纪念册的最佳时机：4月、5月、6月、7月
>7. 希望添加额外的功能：个人基本信息姓名联系方式、全体毕业照、同学留言、学院老师寄语、个人感言、校园风景、专业特色、校卡使用
>8. 你心目中理想的毕业纪念册的样式（内容、封面设计、排版）是（开放题）

:star: **产品定位**

>- 功能上还原传统纸质纪念册中的信息填写，同学寄语等，适当减少社交类的功能
>- 对各种格式信息进行保存，加入图片信息、语音信息、视频信息等

:star: **目标群体大学生**

>- 主要针对的人群集中在即将毕业的大学生，对新型模式的纪念册排斥度会较小，接受度较高，而且善于接受新鲜事物
>- 大学生是手机用户的一大类人群，使用手机主要表现在满足沟通、娱乐、学习等需求上，情感价值主要表现在对个性化、时尚、分享交流的追求上
>- 现代信息的多元化，信息的交流和保存不再局限于文字的格式，更多的信息是图片格式、语音格式和视频格式
>- 功能设计中加入语音和视频信息的储存交流功能既满足大学生群体沟通的需求同时也满足大学生对个性化分享交流的追求

:star: **商业模式**

根据毕业生提供的影印照片和成长资料，专门为其量身定做了毕业纪念册。
>- 针对阶段性的学习生活进行记录，并采取前期免费模式推广，使用部分匿名社交模式进行收费与互动
>- 规范制作纪念册的“生产线”，推出精装版、简装版和平装版，不同的版式有着不同的价格，并针对于”贵宾“客户推出折扣
>- 提供图文的排版设计、礼品制作，策划活动，提供聚会地安排、DV拍摄、礼物派送、纪念册制作等完整服务链
>- 除具备聊天加好友的功能之外，还加入招聘、婚恋、聚会、创业等辅助功能（有待商榷）
>- 同时提供纸质版服务，配合平面设计建立多模板，为用户提供多样性的选择空间进行个性化定制

本着满足大部分人群对 APP 形式便捷的需求，同时满足小部分人群对纸质毕业纪念册传统感的追求，同时最新颖的特点是应用了高新技术 API 的调用，基于人脸融合与语音合成 API 场景化使用，通过对照片与语音合成处理，将用户数据上传云端并进行备份，可随时进行调取<br>

综合分析市场研究和调查，目前市面上并没有推出一款具体的使用人工智能 API与机器学习 的智能毕业相册APP，市面上的大多数都是以链接或者是纸质版留存为准，纪念意义大于使用意义，没有后续的使用价值，没有办法通过毕业纪念册来进行产品后续的自我价值，也没有很好起到沟通的效果，与产品设计的初衷有悖，并且通过调查，使用线上的程序或者是 APPs 在移动互联网下会有更多的使用场景和可以辨别的，使用频率和次数会增加，并且用户场景会更多<br>

## :sparkles: 价值主张设计

### :star: 加值宣言
(以机器学习或人工智能 API 对产品加值的表述是否精确丶专业及中肯 1%*3=3%)

1. **个性化定制，人脸融合与语音合成，千人千面**<br>
用户有千人千面的个性化照片与语音，基于用户画像行为为用户推荐更加精准好玩的人脸合成与语音合成的设计功能。依托人脸识别算法和深度学习引擎，快速精准地定位人脸关键点，将用户上传的照片与特定形象进行面部层面融合，使生成的图片既有用户的五官特点，也呈现出对应形象的外貌特征。同时合成语音自然流畅，近乎真人发声
2. **游戏式功能设计，贴合匿名查看，用户好奇心理重**<br>
在娱乐为王的现代，大部分用户早已经不仅仅满足于功能的达成，美观的界面还有轻松的交互，杠杆点正在向情感体验和自我实现等需求倾斜。使用游戏式设计将人脸融合与语音合成进行包装展现在用户面前，通过猜对即可解开隐藏在匿名照片下的个人联系资料，基于用户同理心和对新技术好奇的心理，来促进更多的人际联系
3. **互动留念方式新颖，辅助线上社交，适当提高粘连度**<br>
与传统毕业纪念册的线下耗费时间与人力填写，使用线上的 APP 会更加注重时间利用的效率，在半隐形社交的圈子内可以更好兼顾校园资源，打造不一样的社交圈子

### :star: 核心价值宣言
(加值的表述是否找到产品核心价值，也就是最小可用产品（Minimum Viable Product，最小可用产品），而不会过份夸大价值或只是点缀性质 1%*3=3%)

>运用价值主张(Value propositions)来对商业模式(Business models)进行剖析，使用应用程序编程接口(Application Programming Interface API)来对API经济(API Economy)、API开放平台(API Open Platform)以及模块化(Modularization)来对利害关系(Stakeholder)的两方：API面向客户(API Customer)和API使用者(API Consumer)来进行资源合理配置。<br>
>利害关系图的阐述：产品设计开发人员（API客户）+ 系统整合开发人员（API使用者）+ 终端用户 + API/智能云端供货商（API提供者）这4个角色的活动流程如下：<br>
>1. API客户也就是产品经理来对智能产品的价值主张进行设计（对应到终端用户的用户需求的任务、痛点及增长点），对智能/平台/模块成本效益进行分析（对应供货商的技术及数据的价值主张）<br>
>2. API使用者也就是后台开发人员对终端用户提出的需求任务、痛点及增长点按照API客户设计的价值主张来系统整合开发APPs，基于API供货商提供的APIs开放平台以及数据库服务，<br>
>3. 从APPs-APIs-DataService的回路：<br>
>- 将已有成功的APPs或平台，用模块化设计拆出人机交互组件API、云端等等可再组合模块
>- 将已有模块化设计拆出人机交互组件，API、云端等等可再组合设计出符合用户需要的APP或交互产品<br>

```
+ 智能毕业纪念册基于 API开放平台技术的支持来对该款 APP 进行模块化设计，针对用户的不同使用场景来对该款APP的价值主张来进行补充，并且在可实际操作的商业模式下来对API客户和API使用者进行资源的合理调度。
- 用户对于身边即将毕业的同学熟悉度远远低于自身的心理预期，从期望提升用户之间黏连性出发，使用了 人脸融合和语音合成 API接入技术，来对使用场景进行模块化设计，创新使用游戏式模式推出“你合我猜”模块，让用户在互相识别的同时加深对身边同学的了解。
- API客户也就是产品设计人员基于市场调查发现智能毕业纪念册的市场空缺大，并且可复用性低，加上使用智能 API 对产品的特性加成大可为产品带来一定的用户流量
- API使用者也就是产品开发者直接使用已经封装打包好的应用程序接口可以更高效率来进行软件开发，而不是重新去写接口会大大提高识别的准确率，减少bug
- 从APPs-APIs-DataService的回路是需要来进行后台数据库的备份以及上传云端方便进行随时调取，通过使用API提供的云存储服务
```

1. **产品背景**<br>
在 API 开放平台资源丰富情况下，对毕业纪念册进行 API 的调用可以使用最前沿的科技研究成果，将开发效率有效提高，并且在产品的产出过程中使用用户画像与用户同理心来进行功能设计，有效开发出最小可行性产品。针对市面上传统毕业纪念册占比的逐渐减少，而聚合人脸融合和语音合成的新型毕业纪念册市场空缺大，没有相关产品进行有效填补 API 调用的市场空白。语音留言、影像传递很常见，但是将照片进行融合再配上一段语音合成再保存，相信比起只是文字叙述式的保存更有趣和有意义的多，以人脸融合语音猜人的形式为同学之间打开又一道交流之门，意义的价值是翻倍的。

2. **产品目的**<br>
使用最小可行性产品，通过游戏式设计“你合我猜”游戏模块来吸引用户对产品的热度，在对人脸融合和语音合成的技术上合成新语音新照片来进行游戏的同时赋予半社交功能，有效解决同学之间陌生感以及相见的尴尬感降低到最低值，帮助用户走出社交弱圈，提高同学之间的黏连性。

3. **产品目标**<br>
不断对游戏式功能进行迭代设计，并在对用户进行可用性测试与用户研究后比对功能来进行取舍。特色功能对 智能API 的使用来为本产品增加用户的留存率以及提升用户之间的粘连性。

### :star: 用户痛点宣言
(加值的表述是否明文且合理有实据地对映到用户痛点的表述。用户痛点参见 吴雪. 人工智能产品经理 1%*3=3%)

|用户痛点|解决方案|
|千篇一律的模板相册套用没有新意，没有可玩性|自主创作，个性化精准服务并提供游戏化模块进行交流互动，扭转弱社交关系|
|电子相册更多是照片的留存，信息更新不及时，实用性弱联系性弱观赏性强|提升效率和准确率，线上查看方便，更新及时，联系快捷|
|自己制作太麻烦，等待周期长|提升用户体验，个人编辑所属页面，使用标签化归属分类|
|特定时间使用，用完即卸载，重复使用率不高|强化功能设计，增加游戏式模块功能，日常激活用户兴趣|

### :star: 人工智能概率性与用户痛点
(AI 概率性考量：使用人工智能的加值的表述是否纳入判断有错的（如假阳 False Positive 假阴 False Negative）的精确概率考量，以确保判错对用户体验的负面影响不会压过正面影响的机率。概率性参见 吴雪. 人工智能产品经理 1%*3=3%)

>判断愿景：实现推断的概率无限逼近100%<br>
>判断标准：在具体的业务场景中，判断人工智能可以达到的推断概率是否能解决用户的需要，及这种概率被用户接收的最低标准是什么、能够超出用户预期的标准是什么，并判断这些判断决定对产品研发的投入策略。<br>
>判断目的：实现概率最优和成本投入（资金投入、技术投入、时间周期选择）之间的平衡<br>

|概率性|用户痛点|
|阳性 Positive|千篇一律的模板相册套用没有新意，没有可玩性|
|假阳 False Positive|电子相册更多是照片的留存，信息更新不及时，实用性弱联系性弱观赏性强|
|假阴 False Negative|自己制作太麻烦，等待周期长|
|阴性 Negative|特定时间使用，用完即卸载，重复使用率不高|

### :star: 需求列表与人工智能 API 加值
(使用人工智能的加值是否反映到需求列表（核心功能的排序上）且 PRD 列出明显有可行及可用的 API 1%*3=3%)

|经典使用场景|需求列表|核心功能|优先级|可用人工智能API|
|-------|-------|-------|-------|-------|
|点击“你合我猜”进入匿名游戏|对人脸/图像进行融合|你合我猜游戏模块|首要|旷世Face++人脸融合、腾讯AI开放平台人脸融合、百度AI开放平台人脸融合|
|点击“你合我猜”进入匿名游戏|对用户语音进行合成|你合我猜游戏模块|首要|科大讯飞语音合成、百度AI开放平台语音合成、腾讯AI开放平台语音合成|

## :sparkles: 原型

### :star: 交互及界面设计
(在 PRD 文件中是否有说明且原型是否有做到：交互及界面设计的某个核心交互环节使用了人工智能的加值 1*5%=5%)

1. 有界面交互
2. 有核心你合我猜的人工智能
3. 协同过滤的推荐算法交互

设计APP界面布局达到可视性从而使用户产生可记忆性，流畅的APP交互流程设计可使用户提高对产品的使用效率，增强用户对产品的可学习性









### :star: 信息设计
(在 PRD 文件中是否有说明且原型是否有做到：信息设计的某个核心信息或设计使用了人工智能的加值 1%*5=5%)


1. 有界面交互
2. 有核心你合我猜的人工智能
3. 协同过滤的推荐算法交互

流程图要好好写出来



产品结构图
1 产品功能结构图
2 产品信息结构图


### :star: 原型文档
(多少程度上有提供 MVP 可交互的原型文档，供它人在 Github 上下载使用 1%*5=5%)

1. 有界面交互
2. 有核心你合我猜的人工智能
3. 协同过滤的推荐算法交互

- 最小可行性产品的交互界面可以交互的文档，
- 原型文件要上传GitHub来进行可下载

GitHub 代码下载地址：







1. 功能权限
- 功能权限分为登录/未登录两个状态
（1）登录：用户登录状态下可对APP进行所有功能操作
（2）未登录
-未登录状态可以搜索联系人活动，查看联系人部分信息，私密信息进行隐藏。。。
-但是无法查看信息，签到，打开联系人，查看我的福利，参与评论，打开个人tab等需要个人账号信息的功能

- 键盘说明
(1)点击输入手机号码、手机验证时从页面底部弹出数字键盘；
(2)点击输入其它内容时从页面底部弹出字母键盘
- 页面内交互
- 页面异常
- 页面间交互
- 更多操作

2. 主要业务逻辑流程图
登录注册
订单业务

3. 页面详细功能说明
启动页

### :star: 口头操作说明
(多少程度上在 2-3 分钟时间限制内，对听众留下了「的确这是个可行丶可用的人工智能加值产品」的印象 1%*5=5%)

2-3分钟让观众来对这个产品留下深刻的印象，这是个可以使用的人工智能产品




1. 页面逻辑&交互说明：
登录注册触发条件
- 登录
(1)页面逻辑内容
(2)页面交互说明
- 注册
(1)页面逻辑内容
(2)页面交互说明
- 首页
(1)首页交互说明
- 搜索
(1)页面逻辑内容
(2)页面交互说明
- 推荐
(1)页面逻辑内容
(2)页面交互说明
- 新品
(1)页面逻辑内容
(2)页面交互说明
- 众筹
(1)页面逻辑内容
(2)页面交互说明
- 识物
(1)页面逻辑内容
(2)页面交互说明
- 分类
(1)页面逻辑内容
(2)页面交互说明




## :sparkles: API 产品使用关键 AI 或机器学习之API的输出入展示

### :star: 使用水平
(在 PRD 文件中是否有说明且展示，核心功能所应用的 API 之输入及输出 1%*5=5%)

核心功能的你画我猜的代码展示两个API再来一个推荐算法
显示两个API的调用来上传代码
可以调用多个平台的PI同类型没有问题可以实同一个公司的



1. 人脸融合

- [Face++ 人脸融合API使用文档](https://console.faceplusplus.com.cn/service/image/intro)
[Merge Face API (V1):使用本 API，可以对模板图和融合图中的人脸进行融合操作](https://console.faceplusplus.com.cn/documents/20813963)
Face++旷视 人工智能开放-技术能力-人像处理-人脸融合（点击会跳转到图像识别/功能的API里面，应该是被归类为识物里面）


```

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



[react-native 使用 Face++ 识别身份证，读取信息展示](http://www.pianshen.com/article/266759574/)
[markdown：API 编写模板](https://blog.csdn.net/weixin_33871366/article/details/94609694)
[C语言写的 FacePlusPlus，“error_message”：“ MISSING_ARGUMENTS：api_key”，带有 React Native 提取请求](https://stackoverflow.com/questions/48652293/faceplusplus-error-message-missing-arguments-api-key-with-react-native-f?rq=1)
[非常详细的教程用Face++来人脸融合 手把手教学](http://help.ih5.cn/question/3276.html)
[纯前端实现人脸融合 - 调用 Face++ 的人脸融合 API 接口实现 用C来写得](https://blog.csdn.net/gaofei880219/article/details/80805558)



- 腾讯AI开放平台人脸识别
- 百度AI开放平台人脸识别

2. 语音合成

- 科大讯飞语音识别
- 腾讯AI开放平台语音识别
- 百度AI开放平台语音识别



网易AI语音合成没有文档
科大讯飞的语音合成找不到文档就是按照上课来进行书写代码的调用了
Face++没有语音合成
腾讯没有语音合成的pythn代码不友好只有PHP的代码

[吐槽腾讯语音合成python 腾讯语音合成](https://www.cnblogs.com/zepc007/p/10360557.html)在代码层次上讲，官方压根没有合成示例文档啊 (咆哮 ing)，全自己摸索的啊 (咆哮 ing)，SDK 都开发出来了，示例代码给一下能死啊 (咆哮 ing)，怪不得没人用啊 (咆哮 ing)！在合成效果上讲，声音难听爆了有木有，语音文件还得解码再 I/O, 吃饱了撑的了啊，还是那句话：怪不得没人用，百度语音合成效果比你强多了。

[良心博主：Python 调用腾讯 API 合成语音](https://www.codeleading.com/article/72342390067/)
[上面文章的CSDN出处](https://blog.csdn.net/hui_0_/article/details/102675804)

实验心得


先来使用腾讯语音合成

人脸融合没有开放就是没有成熟
[腾讯AI开放平台](https://ai.qq.com/)-控制台-创建应用-在应用管理找到应用信息里面的APPID APPKEY
首页技术引擎-语音合成-语音合成 [语音合成](https://ai.qq.com/product/aaitts.shtml)
[技术文档 PHP](https://ai.qq.com/doc/aaitts.shtml)

参考良心博主的代码
说明
1. 需要去官网 https://ai.qq.com/ 创建应用，得到 APPID 和 APPKEY，然后将代码中默认的 appid = '1000001’和 appkey = 'a95eceb1ac8c24ee28b70f7dbba912bf’替换一下。
2.text 是想要被转换成语音的文字，这个文字似乎不能太长，否则特别容易请求失败。
3. 如果一切正常，会在代码所在目录下新增一个 wav 格式的音频文件，这个就是返回的腾讯合成的音频。
4. 有时候会提示‘system busy, please try again later’，原因暂时不清楚。

改好后要来对参数进行查看报错信息
[异常处理](https://ai.qq.com/doc/returncode.shtml)
完成后出现了ret: 16389查看异常处理是因为缺失 API 权限 请检查应用是否勾选当前 API 所属接口的权限 应该是接口没有被允许，所以要返回控制台为应用来添加能力库，在能力库里面找到语音合成并且点击接入能力到该创建的应用下面才可以调用权限
完成后出现了ret: -2147483634是表示系统出错，例如网络超时，那就来刷新一下还是msg: system busy, please try again later
退出来再来刷新一遍就是成功但是还是会报错：ret: 0 msg: ok 68     filepath = path.dirname(__file__)  #目录 NameError: name '__file__' is not defined 目录没有被定义就是我没有定义好目录在哪里，
定义好后又发现诡异的报错：fout = open(filepath+file, 'wb'       ValueError: embedded null character
这是写入文件的内容而不是可以乱删除，可能是文件的路径/\的区别
[诡异错误一： ValueError: embedded null character](https://blog.csdn.net/quintind/article/details/77371402)
所以就是这样子的区别：

1、通过测试，确定错误确实是文件读取语句；

2、是否是文件中包含 null 字符呢？用 ultraedit 工具用 16 进制形式检查数据文件，没有发现有 null 字符；

3、是否是因为 Windows 中的编码和 python 中的编码形式不一样造成的呢？查看到文件编码为 GBK 格式，但 python 是可以正确读取 GBK 文件的，试了其它 GBK 文件，读取没有任何问题；

4、是不是因为文件名太长？把数据文件放在当前文件夹下，尝试读取确实没有问题。但真的是文件名太长的原因吗？这时候我才发现文件名中有个 ‘\0’ ，才如梦初醒。

注意：一般情况下，Python 解释器会将遇到的‘\’识别为路径，会自动增加一个’\’以便和转义字符进行区分，但若遇到转义字符则不增加‘\’。

例如：上述文件名将被转换为 F:\eclipse_workspace\machine_learning_example\Ch02\trainingDigits\0_38.txt。因而出错。

文件路径中若包含‘\0’、’\t’ 等特殊转义字符时要特别注意。

推荐文件路径写法：

F:/eclipse_workspace/machine_learning_example/Ch02/trainningDigits/0_38.txt ，斜杠反过来了，这样就不会出现歧义了。
F:\eclipse_workspace\machine_learning_example\Ch02\trainningDigits\0_38.txt
————————————————
版权声明：本文为CSDN博主「桂小林」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/quintind/article/details/77371402


在 stackoverflow АлексейСеменихин的回答也是一样-似乎您在使用字符 “\” 和 “ /” 时遇到了问题。 如果您在输入中使用它们 - 尝试将它们更改为另一种.. [使用 open（）时出现 “ValueError：嵌入的空字符”](https://stackoverflow.com/questions/33977519/valueerror-embedded-null-character-when-using-open/33981557)




```
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

**腾讯语音合成调取成功**

调用的代码展示：

>![腾讯语音合成notebook代码截图](https://images.gitee.com/uploads/images/2019/1224/101352_71f36a7f_1831543.png "屏幕截图.png")

>![腾讯语音合成wav01.wav存储位置截图](https://images.gitee.com/uploads/images/2019/1224/101547_57bc3ec5_1831543.png "屏幕截图.png")


百度语音合成

[Python 人工智能之路 - 第二篇：算法实在太难了有现成的直接用吧 进阶版的百度云语音合成](http://www.uml.org.cn/python/201911293.asp) 没有采用这个

一、官网
[百度大脑 AI开放平台](https://ai.baidu.com/)
开放能力-语音合成-在线语音合成-技术文档-
[在线合成API接口](https://ai.baidu.com/ai-doc/SPEECH/Gk38y8lzk)
有官网的demo
有语音合成示例代码，有python的 [Baidu-AIP/speech-demo](https://github.com/Baidu-AIP/speech-demo/tree/master/rest-api-tts)
[百度语音合成python代码下载](https://github.com/Baidu-AIP/speech-demo/tree/master/rest-api-tts/python)
[直接点击就是可以来进行查看复制粘贴](https://github.com/Baidu-AIP/speech-demo/blob/master/rest-api-tts/python/tts.py)

登录百度大脑AI开放平台-控制台-语音技术-创建应用-管理应用-APIID API Key Secret Key 三个资料


```

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
代码生成截图

>![百度AI语音合成nupyternotebook运行成功](https://images.gitee.com/uploads/images/2019/1224/111344_f8a5df61_1831543.png "屏幕截图.png")



上面的代码都是已经调试成功了
因为是用jupyternotebook来进行打开并且存储的，那么生成的 result.mp3的文件就是可以保存生成在和书写这个代码的文件是放在一起的，不是notebok的目录，而是在哪个文件里面生成他就是在哪个文件夹里面找到生成的文件就是好了

文件放置截图

>![百度AI语音合成生成 result.mp3 生成位置](https://images.gitee.com/uploads/images/2019/1224/110947_c01f3dad_1831543.png "屏幕截图.png")





我在使用命令行来进行搜索，是因为当时没有找到，在文件快速访问里面也没有，后来可以下载everything很多人来推荐后面还是找哦命令行来进行下载


dir C:\ G:\ H:\ W:\ X:\ /s /b | find "result.mp3"

>![使用命令行来搜索生成 mp3 的具体位置](https://images.gitee.com/uploads/images/2019/1224/111716_81ed72ac_1831543.png "屏幕截图.png")




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








### :star: 使用比较分析
(在 PRD 文件中是否有说明且提供连结证据，所使用的 API 是查找过最适用的（主要竞争者无或比较次），如考量其成熟度丶性价比丶等等 1%*5=5%)

可以借鉴表格
需要有链接也就是API的链接，
判断最实用的
比较主要竞争者合比较次的竞争者，成熟度丶性价比等比较来做好表格





1. 人脸识别-人脸检测与属性分析

- 旷世Face++人脸识别



![Face++Face](https://images.gitee.com/uploads/images/2019/1211/083658_bc4cf548_1831543.png "屏幕截图.png")


- 腾讯AI开放平台人脸识别

![TencentFace](https://images.gitee.com/uploads/images/2019/1211/083940_ef1ea3b9_1831543.png "屏幕截图.png")

- Axure人脸识别

- 百度AI开放平台人脸识别

![baiduFace](https://images.gitee.com/uploads/images/2019/1211/084319_597fac32_1831543.png "屏幕截图.png")


2. 语音识别

- 科大讯飞语音识别

![XunfeiVoice](https://images.gitee.com/uploads/images/2019/1211/084823_cbe441aa_1831543.png "屏幕截图.png")

- 腾讯AI开放平台语音识别

![TencentVoicelab](https://images.gitee.com/uploads/images/2019/1211/085133_7012276f_1831543.png "屏幕截图.png")
![TencentVoiceChat](https://images.gitee.com/uploads/images/2019/1211/085308_712c8375_1831543.png "屏幕截图.png")

- 百度AI开放平台语音识别








### :star: 使用后风险报告
(在 PRD 文件中是否有说明且提供连结证据，所使用的 API 类别的现在及未来发展性，如 API 市场竞争程度丶输入输出限制丶定价丶及可替代的程序库（改用自己开发的代码及数据库而不用 API）等等 1%*5=5%)

现在及未来发展性
API 市场竞争程度丶输入输出限制丶定价丶及可替代的程序库（改用自己开发的代码及数据库而不用 API）都要写上来

准确度
响应度
价格
优点缺点

弄符号和自己实验过程中出现的展示和数据来进行说明














1. 人脸识别

- 旷世Face++人脸识别

- 腾讯AI开放平台人脸识别

- Axure人脸识别

- 百度AI开放平台人脸识别

2. 语音识别

- 科大讯飞语音识别

- 腾讯AI开放平台语音识别

- 百度AI开放平台语音识别




### :star: 加分项
(使用复杂度：用了 2 个以上机器学习与人工智能的 API 之输入及输出 1%*3=3%)

最少要3个的API的测试文档和实践好的代码链接翻上来

附件加清单自己的代码下载和原型展示和下载



基于协同过滤的推荐算法，常见的包括基于用户、基于物品的协同过滤。





### :sparkles: 六、总结

先来船传江



附录：

[Reveal.js：把你的 Markdown 文稿变成 PPT](https://sspai.com/post/40657)
[Marp：用 Markdown「写」PPT 的新选择](https://sspai.com/post/55718)


我们大多数人所理解的人工智能技术可能还停留在算法本身，但实际上真正的人工智能应用针对不同的领域，不仅有各自的算法，事实上还包括其他领域知识的应用，如自动化控制理论、电子技术、通信技术、机械工程等等，因此我们所理解的人工智能，应该是一个系统工程。网络中有一张图，讲述的是人工智能的深渊，毫不夸张的说，这其中的随便挑一项技术都是科研学者花费大量时间和精力去研究的，很少有人能够全面了解所有知识领域。
市场的接受情况

产品的架构和路径是什么样的
产品的流量是如何运作的
产品的商业化是如何完成的：

产品化决定了产品的价值空间，商业化则决定了产品将价值变现的能力。

这造成了一方面产品在研发阶段投入的成本具有不确定性，另一方面技术的预期效果也比较难评估。

制定产品的定价策略，而是需要站在用户角度考虑产品定价策略，深入理解场景和用户的痛点在哪里。







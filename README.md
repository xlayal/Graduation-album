# 智能毕业纪念册APP
 |  发布日期 | 2019-11-30 |
 | -- | -- |
 |  项目名称 | 智能毕业APP |
 |  项目现状 | 进行中 |
 |  项目的主人 | 詹晓燕|
 |  项目的设计师 | 詹晓燕 |
 |  项目的开发者 | 詹晓燕 |
 |  项目头的测试者 | 詹晓燕  |
 
## 一、价值主张设计
### 1、加值宣言
毕业对于所有人来说，那是人生中最美好的一段光景，假若能将它以美好的形式呈现给自己，自己的朋友，以后的孩子看，都是一件可以流传的故事。智能毕业纪念册APP由此上线，针对以往的传统的毕业纪念册不宜保存且分享的问题，以云端形式保存纪念照并且还可以增加社交功能的手机端APP很好地解决了这个问题，同时还接入语音识别的API接口，可以对用户选择的语音上传并识别成文本反馈给用户。
##### 优先级：采用百度AI中的人脸检测与属性分析对用户上传照片中的人脸进行识别，反馈给用户人脸识结果的多种属性信息（包括年龄、性别、表情），同时用户在选择语音上传时，可以通过语音识别API将其识别成文本输出。
##### 次优先级：通过地标识别API将用户上传照片识别出对应的地标，并且通过集成地标识别服务，实现自动给地标图片打标签并进行分类，生成智能相册。
### 2、核心价值（最小可用产品）
本产品着力于为用户提供一个方便快捷上传分享自己的毕业照并且附注语音留言的功能，给即将毕业的学生们留下美好的纪念。后期会加上定位上传照片，并且在地图上显示出来的功能。

### 3、核心价值与用户痛点
* ##### 智能分类
通过集成分类服务，将地标分类存放，方便用户在上面寻找对应的标签图片，快速定位用户自身的需求。
* ##### 实时查看
通过手机APP去查看毕业相册，解决了以往使用纸质版毕业册不易查看，不方便携带的问题，同时APP上的语音交互也可以使用户实时分享储存。

### 4、人工智能概率性与用户痛点 
* #### 百度AI人流量识别功能的保障：
##### 1、算法领先，高精度头肩检测算法，准确率90%以上，静态人数统计不限人数，适应各种人群密集场所。
##### 2、服务稳定，可提供企业级稳定、精确的大流量服务，拥有毫秒级识别响应能力及99.9%的可靠性保障。
#### **据此，该产品人流量识别功能准确率有保障，通常不会出现与实际数据偏差太大的情况，但是由于此功能以外的因素（如网络延迟或者卡顿无法使视频图像被正确识别）会导致数据输出延迟或者不准确，此概率事件可以通过改进得到缓解，对用户的负面影响不会过大。**
* #### 百度AI中的通用物体和场景识别技术有三大产品优势：
##### 1、准确性高，基于百度海量数据，利用深度学习技术及高精度算法不断迭代模型，准确率业界领先。
##### 2、标签体系丰富，可识别出10万+物体及场景标签，并在不断丰富中，持续提供更精细的识别服务。
##### 3、简单易用，支持标准化接口封装，调用简单，只需上传单张图片，即可获取识别结果。
#### **因此，该APP用户通过拍照上传，使用了通用物体和场景识别照片中的物体返回大类及细分类的名称结果。此功能技术准确率较高，普遍情况下返回结果比较精准。但由于一些环境因素（如光线太暗）或者照片原因（如照片不清晰、识别主体精确等）造成返回识别结果不准确的状况，这些事件为小概率事件，对用户体验的负面影响不会压过正面影响的机率。**

### 5、需求列表与人工智能API加值
|  用户需求  | API接口  | 重要程度  |
|  ----  | ----  | ----  |
| 用户想要上传自己的毕业照并且识别人脸信息 |人脸检测与属性分析 API | 重要 |
| 上传分享自己的语音及文字 | 语音识别API | 重要 |
| 对上传照片中的地标进行识别分类| 地标识别API | 重要 |

### API调用示例
```
Python代码示例

# encoding:utf-8

import requests
import base64

'''
人流量统计
'''

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num"
# 二进制方式打开图片文件
f = open('human.jpg', 'rb')  #上传毕业照
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '[此处输入你获取到的token]'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
## 价值主张练习
* **1句话版本**
### 智能毕业册通过人脸检测与语音识别API加持，帮助目标用户更好地留住青春的痕迹。

* **1分钟版本** 
#### 本产品着力于为用户提供一个方便快捷，可以上传分享自己的毕业照并且附注语音留言的功能，给即将毕业的学生们留下美好的纪念。我们希望通过毕业相册服务，帮助用户解决以往使用纸质版毕业册不易查看，不方便携带的问题，同时APP上的语音交互，可以对用户选择的语音上传并识别成文本反馈给用户，同时用户可以实时分享储存。另外，通过集成分类服务，我们将用户上传的毕业照识别出对应的地标分类存放，方便用户在上面寻找对应的标签图片，减少了用户查找自己想要照片的时间，快速定位用户自身的需求。

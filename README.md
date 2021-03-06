# 基于指静脉识别的校园安全保障系统设计与实现
本程序用于指静脉图像的识别，需与MySQL结合使用。

## 使用步骤
**一、设置MySQL**   
1. MySQL用户名设为“root”，密码设为“123456”。  
2. 建立名为“FVRT”的数据库。  
3. 在“FVRT”数据库下通过下列语句建立名为“image”的数据表：  
CREATE TABLE if NOT EXISTS image ( id int unsigned primary key auto_increment,imname text NOT NULL,imdata mediumblob NOT NULL,
imcount INT NOT NULL,KEY(imname(15)))character set = utf8;  

**二、运行程序（1、2任意一种方法）**  
1. 编译脚本  
在您的IDE（建议Pycharm）中建立文件夹，将路径为“./源码”的源码拷入。因本程序用wxPython编写GUI以方便使用，故从路径为“./源码/FVRT_FrameStart.py”中的代码开始启动本程序界面，结合路径为“./指静脉样本”中附带的指静脉样本运行。  
2. 运行可执行文件  
路径为“./exe.win-amd64-3.5.7z”的文件为可执行文件，结合路径为“./指静脉样本”中附带的指静脉样本运行。

## 程序运行截图
### 1. 程序界面
#### 1.1 主界面
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A2/%E4%B8%BB%E7%95%8C%E9%9D%A2.png" width="60%"/>  

#### 1.2 图像匹配界面
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A2/%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%95%8C%E9%9D%A2.png" width="60%"/>

#### 1.3 图像处理界面
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A2/%E5%9B%BE%E5%83%8F%E5%A4%84%E7%90%86%E7%95%8C%E9%9D%A2.png" width="60%"/>

#### 1.4 图像输入界面
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A2/%E5%9B%BE%E5%83%8F%E8%BE%93%E5%85%A5%E7%95%8C%E9%9D%A2.png" width="60%"/>

#### 1.5 图像输出界面
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A2/%E5%9B%BE%E5%83%8F%E8%BE%93%E5%87%BA%E7%95%8C%E9%9D%A2.png" width="60%"/>

### 2. 指静脉图像匹配结果示例
#### 2.1 待识别的图像_原图：“F0101.bmp”
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/1%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E5%8E%9F%E5%9B%BE%EF%BC%9A%E2%80%9CF0101.bmp%E2%80%9D.bmp" width="20%"/>

#### 2.2 待识别的图像_尺寸归一化
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/2%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E5%B0%BA%E5%AF%B8%E5%BD%92%E4%B8%80%E5%8C%96.bmp" width="20%"/>

#### 2.3 待识别的图像_灰度归一化
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/3%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E7%81%B0%E5%BA%A6%E5%BD%92%E4%B8%80%E5%8C%96.bmp" width="20%"/>

#### 2.4 待识别的图像_方向谷型检测
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/4%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E6%96%B9%E5%90%91%E8%B0%B7%E5%9E%8B%E6%A3%80%E6%B5%8B.bmp" width="20%"/>

#### 2.5 待识别的图像_模糊增强
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/5%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E6%A8%A1%E7%B3%8A%E5%A2%9E%E5%BC%BA.bmp" width="20%"/>

#### 2.6 待识别的图像_阈值分割
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/6%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E9%98%88%E5%80%BC%E5%88%86%E5%89%B2.bmp" width="20%"/>

#### 2.7 待识别的图像_去噪
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/7%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E5%8E%BB%E5%99%AA.bmp" width="20%"/>

#### 2.8 待识别的图像_细化
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/8%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E7%BB%86%E5%8C%96.bmp" width="20%"/>

#### 2.9 待识别的图像_去除残余斑点
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/9%E3%80%81%E5%BE%85%E8%AF%86%E5%88%AB%E7%9A%84%E5%9B%BE%E5%83%8F_%E5%8E%BB%E9%99%A4%E6%AE%8B%E4%BD%99%E6%96%91%E7%82%B9.bmp" width="20%"/>

#### 2.10 与之匹配的图像：“F0108.bmp”
<img src="https://github.com/bmxbmx3/Finger_Vein_Recognition/blob/master/%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E6%88%AA%E5%9B%BE/%E6%8C%87%E9%9D%99%E8%84%89%E5%9B%BE%E5%83%8F%E5%8C%B9%E9%85%8D%E7%BB%93%E6%9E%9C%E7%A4%BA%E4%BE%8B/10%E3%80%81%E4%B8%8E%E4%B9%8B%E5%8C%B9%E9%85%8D%E7%9A%84%E5%9B%BE%E5%83%8F%EF%BC%9A%E2%80%9CF0108.bmp%E2%80%9D.bmp" width="20%"/>

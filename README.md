# 进度提示（标志：仓库程序文件还没有完善好）
2018.6.6 完成代码提交(下一步对代码进行检测是否可以运行)

# 工程内容    
这个程序是基于Pytorch实现Faster-RCNN功能。    
参考代码链接：https://github.com/jwyang/faster-rcnn.pytorch.git    
参考代码特点：代码健壮，功能齐全，使用方便，过于庞大不方便阅读学习   
本代码目的：方便学习faster-rcnn细节，如果项目应用还是用参考代码比较好   
本代码特点：在保证基础功能的前提下，对数据处理部分进行整理，对模型部分进行注释    

### 开发环境  
Ubuntu16.04（i5-7500 + GTX 1070Ti ） + python3.5 + Pytorch0.3.0    

### 文件夹说明
1、Data：   
　　　picture_data/Annotations--存放图片标注的xml文件（手动存放）   
　　　picture_data/Images --存放用于训练与测试的图片（手动存放）   
　　　picture_data/cache --存放处理xml文件之后形成图片label信息文件（程序执行）   
　　　train.txt --存放训练图片序号（手动存放）  
　　　pretrained_model --用于存放VGG的预训练模型  
2、Output --存放训练完成的模型（程序执行）   
3、demo/images  -- 存放测试图片  
4、demo/result  -- 存放测试结果  
5、lib -- 模型各个部分的程序文件  

### 程序运行   
1.下载代码到本地： git clone https://github.com/Liu-Yicheng/Faster-rcnn.git   
2.安装程序需要的包：pip install -r requirements.txt   
3. 进入lib文件夹 ：cd lib  
　编译程序需要用到的组件如nms与roi-pooling：sh make.sh 
  
4.程序使用流程：---------------------训练过程---------------------------  
　　　　　　　　A.将需要训练与测试的图片放入Data/picture_data/Images文件夹   
　　　　　　　　　将XML文件放入Data/picture_data/Annotation文件夹  
　　　　　　　　B.训练图片的编号写入train.txt  
　　　　　　　　C.下载VGG预训练模型，放入Data/pretrained_model文件夹。  
　　　　　　　　　权重下载地址：[Dropbox](https://www.dropbox.com/s/s3brpk0bdq60nyb/vgg16_caffe.pth?dl=0)　　[VT Server](https://filebox.ece.vt.edu/~jw2yang/faster-rcnn/pretrained-base-models/vgg16_caffe.pth)  
　　　　　　　　　　　　　　　　[百度云](https://pan.baidu.com/s/1nHezTm6xKXjHYZXKHAl3KQ) 密码：or0m  
　　　　　　　　D.针对自己的项目修改config文件中的参数  
　　　　　　　　E.运行trainval.py 开始训练  
　　　　　　　　----------------------测试过程---------------------------  
　　　　　　　　A.修改demo中的139行改为你训练之后的模型  
　　　　　　　　B.将测试图片放入demo/images文件夹  
　　　　　　　　C.运行demo.py进行测试，结果在demo/result中查看  
3.本代码方便学习faster内部细节与整个流程，但是用于项目中还是用参考代码  
  参考代码实现了多个模型与roi-crop，并且有计算map的函数等等，比较完备   

# Faster-Rcnn模型详解
# Pytorch使用
				
				


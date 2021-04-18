# 测试资源及测试结果
1. **测试资源**<br> 
代码：<https://github.com/HRNet/Lite-HRNet>（测试以COCO数据集为基础且输入大小为256x192的一项）<br>其配套论文：<https://arxiv.org/abs/2104.06403>（Lite-HRNet）
2. **测试结果**<br>  
github上代码已跑通，但该程序仅能对COCO数据集进行测试评估，不能更换数据集（因为其预训练模型checkpoint文件已经把COCO数据集中的json注释文件写死，这是为了在测试数据集时通过json注释文件进行准确率评估）。因此，不能对预训练模型checkpoint修改，只能改test model与config file文件，若更换数据集，则运行错误。综上，本人改用Higher-HRNet的预训练模型checkpoint文件，对TestVideo测试，得到新的TestVideo输出视频。
# 测试过程
1. **安装所需的Python包**<br> 具体安装内容请参见 [Python包](https://github.com/HRNet/Lite-HRNet)
2. **按要求在控制台中运行程序**<br>本人输入的指令是：（python命令后有三个参数，分别表示测试模型、配置文件、预训练模型）<br>
```
python C:\Users\87361\PycharmProjects\HRNet2\tools\test.py C:\Users\87361\PycharmProjects\HRNet2\configs\top_down\lite_hrnet\coco\litehrnet_18_coco_256x192.py C:\Users\87361\PycharmProjects\HRNet2\checkpoint\coco_256x192 --out C:\Users\87361\PycharmProjects\HRNet2\results\a.json
```
对CoCo数据集进行测试，运行结果如下（因数据集太大，仅设置测试10张照片）：<br><br>
![](https://github.com/MuJinlong1/TestHRNet/blob/main/img/first.jpg) <br>
输出的内容是Json文件，该文件表示人体的关键点信息，用OpenCV库可以根据该Json文件以及COCO数据集中对应的图片输出运行的图片标注结果。<br>
3. **运行命令**<br>由于该Lite-HRNet的CheckPoint预训练模型文件已经把COCO数据集中的annotations解释文件（类型是Json文件）写死，故无法对数据集进行修改，只能使用COCO数据集进行测试，无法更改为TestVideo数据集。因此，本人改用higherHRNet中的CheckPoint预训练模型文件对TestVideo数据集进行测试，在控制台下运行如下命令：（python命令后有5个参数，分别表示测试模型、配置文件、预训练模型、输入视频数据集路径、输出目标视频路径）<br>
```
python C:\Users\87361\PycharmProjects\HRNet2\higherHRNet\test.py C:\Users\87361\PycharmProjects\HRNet2\higherHRNet\higher_hrnet32_coco_512x512.py C:\Users\87361\PycharmProjects\HRNet2\higherHRNet\higher_hrnet32_coco_512x512.pth --video-path C:\Users\87361\PycharmProjects\HRNet2\higherHRNet\Video.mp4 --out-video C:\Users\87361\PycharmProjects\HRNet2\results\
```
4. **运行结果**<br>运行视频截图如下：<br>
![](https://github.com/MuJinlong1/TestHRNet/blob/main/img/second.jpg) <br>

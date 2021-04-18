# TestHRNet
 1. 测试资源<br> 代码：https://github.com/HRNet/Lite-HRNet
（测试以COCO数据集为基础且输入大小为256x192的一项 ）
其配套论文：
https://arxiv.org/abs/2104.06403
（Lite-HRNet）
 2. 测试结果<br>  github上代码已跑通，但该程序仅能对COCO数据集进行测试评估，不能更换数据集（因为其预训练模型checkpoint文件已经把COCO数据集中的json注释文件写死，这是为了在测试数据集时通过json注释文件进行准确率评估）。因此，不能对预训练模型checkpoint修改，只能改test model与config file文件，若更换数据集，则运行错误。综上，本人改用Higher-HRNet的预训练模型checkpoint文件，对TestVideo测试，得到新的TestVideo输出视频。
 3. 补充详情<br>  代码及测试过程可见本人github：
https://github.com/MuJinlong1/TestHRNet

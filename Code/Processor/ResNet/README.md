# ReadMe
该模块为整个回归系统的回归器。分为4个部分，分别是：数据处理、Resnet搭建、网络训练、模型预测
模块的主要功能为：

1. 从本地目录获取所有清洗好的数据，将数据按照Resnet的要求加载到内存。
2. 对数据自动分为训练数据和预测数据，其中训练数据喂入Resnet进行模型训练。
3. 对训练好的模型进行预测结果的输出。
4. 支持断点续训，训练过程中模型会每10轮保存一次，可以自由跳转到已经保存好的模型进行继续训练或者模型输出。
5. 支持迁移学习。即利用已经训练好的模型训练新的场景，提高训练的效率和降低对样本数量的需求。
6. getdataTHU.py: 搜索当前目录下所有.csv,.txt文件，以这些文件作为所需的数据。请将待训练的数据放入当前目录。
7. ResnetTHU.py: 定义网路结构，可以根据需要改变卷积核大小（CONV_SIZE）和激活函数。
8. trainTHU.py: 训练模块，也为反向传播模块，根据需要可以改变图片大小IMAGE_WIDTH,IMAGE_HIGHT,改变通道数NUM_CHANNELS1,NUM_CHANNELS2,NUM_CHANNELS3,同时BATCH_SIZE2,BATCH_SIZE3,BATCH_SIZE4也要相应的改变来保持一致（现为取最近3小时，一天前的4小时，一周前的2小时）。
9. predictTHU.py: 预测模块，需要设置预测天数（现为7天）。

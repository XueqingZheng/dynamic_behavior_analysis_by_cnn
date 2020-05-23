# dynamic_behavior_analysis_by_cnn

## 安装
### 安装numpy
```
pip install numpy
```

### 安装gensim
```
pip install gensim
```

如果安装失败，并且提示更新pip
```
python -m pip install --upgrade pip
```
更新完成后就可成功安装gensim

### 安装tensorflow
```
pip install --upgrade --ignore-installed tensorflow
```

成功安装后激活tensorflow
```
activate tensorflow
```

## 运行方法  
1.  格式转换json->txt
    1.  将原始cuckoo跑出的报告report.json都拷贝到文件夹data/cuckoo_reports中 
    2.  用下面指令转换cuckoo报告格式,结果保存在data/cuckoo_report_txts中  
```
python cuckoo2txt.py
```   

2.  准备训练样本  
    把转换为txt格式的动态行为报告，根据类别存放到data/train下的不同目录。  
    例：二分类，分别把样本存入data/train/pos和data/train/neg   
    
3.  训练  
    main函数中有可调节的参数，可根据需要修改。
```
python train.py
```   

4.  测试  
    将txt格式的测试文件存入data/test子目录下   
```
python test.py
```    

5. 查看tensorboard   
```
tensorboard --logdir runs/
打开http://localhost:6006/
```

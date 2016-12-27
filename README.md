# SERPROJ

## 准备工作：

### 1. 下载并解压数据集到 `emotiondetection/` 目录，大概长这样：
```
emotiondetection/
├── fbank/
├── features_labels_lld/
├── features_labels_raw_wav/
├── mfcc_csv/
```

### 2. 运行 `SER-DATA-PROC.ipynb` 生成 `pickle` 格式的训练集和测试集（仅针对lld特征），大概生成如下文件：
```
pickle_test_x_list
pickle_test_y_list
pickle_train_x_list
pickle_train_y_list

pickle_mfcc_test_x_list
pickle_mfcc_train_x_list
```

### 3. 运行其他 `*.ipynb` 查看结果



### Tips

1. Jupyter 转 Python 脚本命令： `jupyter nbconvert --to script [XXX.ipynb]`， 参见链接：http://stackoverflow.com/questions/17077494/how-do-i-convert-a-ipython-notebook-into-a-python-file-via-commandline

2. 用MFCC特征训练模型，或训练其他比较大的模型时，最好直接在Python下执行，避免负载过大导致Jupyter卡死或挂掉影响其他Jupyter工作环境



### TODO

1. MLP 的实验是用MXNet做的，学习率优化目前是默认的sgd。但根据 SER-Classifiers.ipynb 里用 sklearn MLPClassifier (相应配置请参见sklearn的文档) 的结果反而更好来看，我们的 MXNet MLP 需要优化，比如尝试 adam/rmsprop/... 等优化学习率的方法

2. 目前的实验都基于LLD特征，估计很难有比较好的结果。帧级别的MFCC特征已经提供了，所以需要尝试直接用该特征做实验。由于每个句子的帧数不同，最好用生成式的模型来做，比如可以用 GMMHMM/RNN/CNN 等。。。

3. 不同模型的融合（类似 DNN+HMM / DNN+SVM / RNN+SVM ...）

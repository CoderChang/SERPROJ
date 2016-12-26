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

### 2. 运行 `SER-DATA-PROC.ipynb` 生成 `pickle` 格式的训练集和测试集（仅针对lld特征），大概生成四个文件：
```
pickle_test_x_list
pickle_test_y_list
pickle_train_x_list
pickle_train_y_list
```

### 3. 运行其他 `*.ipynb` 查看结果


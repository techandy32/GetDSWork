# GetDSWork
Get DeepSpeed Work

# task
- 搞懂模型訓練時內部的詳細運作 

# Reference
[DeepSpeedExamples](https://github.com/microsoft/DeepSpeedExamples/tree/master)

DeepSpeed Examples from microsoft

[DeepSpeed系列教程1](https://zhuanlan.zhihu.com/p/671026708)

# daily note
## 0427

> deepspeed train_bert_ds.py --checkpoint_dir . --num_layers 24 --h_dim 4096 --num_iterations 1000

目前下這條指令，在train_bert_ds.py 500行報錯

```
in train_bert_ds.py", line 500, in create_experiment_dir
handle.write(gitlog.stdout.decode("utf-8")) 
AttributeError: 'str' object has no attribute 'stdout'
```



## 0425
跟著DeepSpeed Examples裡的HelloDeepSpeed

# related work
[Smart-Infinity](https://github.com/AIS-SNU/smart-infinity)

HPCA'24 make deepspeed work on Samsung SmartSSD

## Aware
目前環境跟**smart-infinity**環境不相同
- smart-infinity : CUDA 11.6, PyTorch 1.12.1
- current :        CUDA 12.1, PyTorch 2.2.1

BTW
smart-infinity的example readme中有說
> We officially support only python 3.6, pytorch 1.5, cuda 10, and nccl 2.6 versions and above.

# GetDSWork
Get DeepSpeed Work

# task
- 搞懂模型訓練時內部的詳細運作 

研究過程放[DailyNote](./DailyNote.md)

# Reference
[DeepSpeedExamples](https://github.com/microsoft/DeepSpeedExamples/tree/master)

DeepSpeed Examples from microsoft

[DeepSpeed系列教程1](https://zhuanlan.zhihu.com/p/671026708)

[DeepSpeed详解-源码分析](https://www.zhangzhenhu.com/deepspeed/%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86.html)

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

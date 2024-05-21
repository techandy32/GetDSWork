# link
- [0520](./DailyNote.md#0520)
- [0505](./DailyNote.md#0505)
- [0427](./DailyNote.md#0427)
- [0425](./DailyNote.md#0425)

# 0520
> /deepspeed/runtime/swap_tensor/

這部份負責將Tensor從NVMe中讀取或寫入的操作

# 0505

train_bert_ds.py 801行
```python
model, _, _, _ = deepspeed.initialize(model=model,
                                          model_parameters=model.parameters(),
                                          config=ds_config)
```            
**deepspeed.initialize**()由deepspeed接管了整個訓練過程，這將model包裝起來

根據config選擇DS engine的模式 :
1. PipelineEngine : 平行化訓練的模式
2. DeepSpeedHybridEngine : 可以同時進行訓練及推理的模式
3. DeepSpeedEngine : 最基本的模式，進行模型的訓練

[DeepSpeed详解-源码分析](https://www.zhangzhenhu.com/deepspeed/%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86.html)


要看
[stage3-前后向过程](https://www.zhangzhenhu.com/deepspeed/stage3-%E5%89%8D%E5%90%8E%E5%90%91%E8%BF%87%E7%A8%8B.html)
還是
[Stage3 - 参数分割](https://www.zhangzhenhu.com/deepspeed/stage3-%E5%8F%82%E6%95%B0%E5%88%86%E5%89%B2.html)
?

在`engine.py`中有一個`deepespeed_io()`的function，他呼叫了`DeepSpeedDataLoader()`
看看這邊做啥


# 0427

> deepspeed train_bert_ds.py --checkpoint_dir . --num_layers 24 --h_dim 4096 --num_iterations 1000

目前下這條指令，在train_bert_ds.py 500行報錯

```
in train_bert_ds.py", line 500, in create_experiment_dir
handle.write(gitlog.stdout.decode("utf-8")) 
AttributeError: 'str' object has no attribute 'stdout'
```



# 0425
跟著DeepSpeed Examples裡的HelloDeepSpeed

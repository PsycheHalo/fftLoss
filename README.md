# fftLoss
The fftLoss @PyTorch is a frequency domain loss function that prevents the problem of weak frequency components being suppressed by strong frequency components when using a regular loss function. 

## 思路说明
在使用MSE等从时域或空域计算的损失函数时,常常得到模糊的结果.这是由于强势频率压制了弱势频率的表达.通过在频域对相位和幅值分别计算差异缓解了这个问题.这使得网络更偏向于生成边缘锐利的结果.

## Install
```bash
pip install fftLoss
```

## Use
```python
from fftLoss import fftLoss
...
loss=fftLoss(input,target,dim=-1,meanOut=True,norm="ortho",absGain=1,angleGain=1)
```


转置卷积要根据设定参数后的具体行为决定kernels维度要填到哪里,可以先写到inDim中尝试

如果zeroMean为False,返回矩阵将没有小于零的值,并且是插值矩阵.否则,返回矩阵将对插值矩阵逐元素随机取反.   


## HomePage
<https://github.com/PsycheHalo/glassInit/>

## [ torch 参数更多 ] torch.fft.hfft

### [torch.fft.hfft](https://pytorch.org/docs/stable/generated/torch.fft.hfft.html?highlight=hfft#torch.fft.hfft)

```python
torch.fft.hfft(input,
                n=None,
                dim=- 1,
                norm='backward',
                *,
                out=None)
```

### [paddle.fft.hfft](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/fft/hfft_cn.html)

```python
paddle.fft.hfft(x,
                n=None,
                axis=- 1,
                norm='backward',
                name=None)
```

其中，PyTorch 相比 Paddle 支持更多其他参数，具体如下：
### 参数映射

| PyTorch       | PaddlePaddle | 备注                                                   |
| ------------- | ------------ | ------------------------------------------------------ |
| input         | x            | 输入 Tensor，仅参数名不一致。                            |
| n             | n            | 输出 Tensor 在傅里叶变换轴的长度。                      |
| dim           | axis         | 傅里叶变换的轴，如果没有指定，默认是使用最后一维，仅参数名不一致。|
| norm           |norm          |傅里叶变换的缩放模式，缩放系数由变换的方向和缩放模式同时决定，完全一致。|
| out            | -            |输出 Tensor，Paddle 无此参数，需要转写。              |

### 转写示例
#### out：指定输出
```python
# PyTorch 写法
torch.fft.hfft(x, n=5, out=y)

# Paddle 写法
paddle.assign(paddle.fft.hfft(x), y)
```

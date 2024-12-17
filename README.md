## This is a pytorch implementation of the paper *[Unsupervised Domain Adaptation by Backpropagation](http://sites.skoltech.ru/compvision/projects/grl/)*


#### Environment
- Pytorch 1.0
- Python 2.7

#### Network Structure


![p8KTyD.md.jpg](https://s1.ax1x.com/2018/01/12/p8KTyD.md.jpg)

#### Dataset

First, you need download the target dataset mnist_m from [pan.baidu.com](https://pan.baidu.com/s/1pXaMkVsQf_yUT51SeYh27g) fetch code: kjan or [Google Drive](https://drive.google.com/open?id=0B_tExHiYS-0veklUZHFYT19KYjg)

```
cd dataset
mkdir mnist_m
cd mnist_m
tar -zvxf mnist_m.tar.gz
```

#### Training

Then, run `main.py`

python 3 and docker version please go to [DANN_py3](https://github.com/fungtion/DANN_py3) 


# 代码修正

因为代码比较旧了，不能做到开箱即用，做一下适配。

main.py 和 test.py 从train文件夹，放到项目根目录下，方便vscode直接运行，以及识别库函数。

因为改变了main.py和test.py的路径，在识别数据集时，所有路径，均去除了前面的'..'。

print函数更新了，需要加上'()'

next函数调用方式改变，code.next() ==> next(code)

model.py文件：nn.Dropout2d()未来弃用，改为nn.Dropout()

UserWarning: Implicit dimension choice for log_softmax has been deprecated. Change the call to include dim=X as an argument.
nn.LogSoftmax() 隐形指定未来弃用，改为nn.LogSoftmax(dim=X)
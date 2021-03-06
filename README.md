# What's this
Implementation of Wide Residual Networks (WRN) by chainer  

# Dependencies

    git clone https://github.com/nutszebra/wide_residual_net.git
    cd wide_residual_net
    git submodule init
    git submodule update

# How to run
    python main.py -g 0

# Details about my implementation
All hyperparameters and network architecture are the same as in [[1]][Paper] except for data-augmentation.  
* Data augmentation  
Train: Pictures are randomly resized in the range of [32, 36], then 32x32 patches are extracted randomly and are normalized locally. Horizontal flipping is applied with 0.5 probability.  
Test: Pictures are resized to 32x32, then they are normalized locally. Single image test is used to calculate total accuracy.  

# Cifar10 result
| network           | depth | k  | total accuracy (%) |
|:------------------|-------|----|-------------------:|
| WRN [[1]][Paper]  | 16    | 8  | 95.4               |
| my implementation | 32    | 8  | 95.83              |
| my implementation | 28    | 10 | 95.76              |
| WRN [[1]][Paper]  | 28    | 10 | 96.0               |

* depth=32, k=8
<img src="https://github.com/nutszebra/wide_residual_net/blob/master/loss.jpg" alt="loss" title="loss">
<img src="https://github.com/nutszebra/wide_residual_net/blob/master/accuracy.jpg" alt="total accuracy" title="total accuracy">

* depth=28, k=10
<img src="https://github.com/nutszebra/wide_residual_net/blob/master/loss2.jpg" alt="loss" title="loss">
<img src="https://github.com/nutszebra/wide_residual_net/blob/master/accuracy2.jpg" alt="total accuracy" title="total accuracy">

# References
Wide Residual Networks [[1]][Paper]

[paper]: https://arxiv.org/abs/1605.07146 "Paper"

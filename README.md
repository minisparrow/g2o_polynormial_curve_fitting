# G2O graph optimization

顶点 vertex： 保存要优化的变量

边 Edge: 保存target值 与 预测值的 差值， 即error

## g2o 编译与安装

```
sudo apt install libqt4-dev qt4-qmake libqglviewer-dev libsuitesparse-dev libcxsparse3.1.1 libcholmod-dev
```


g2o 头文件保存： 

```
/usr/local/g2o
```
g2o 库文件保存: 
```
/usr/local/lib
```

## g2o做优化的主要步骤

1. 定义顶点和边的类型
2. 构建图
3. 选择优化算法
4. 调用g2o进行优化，返回结果。


## g2o 的 类：

保存要优化估计的变量a,b,c
```
定义顶点类 
CurveFittingVertex
继承自:
g2o::BaseVertex<3, Eigen::Vector>
```

保存误差error
```
定义边类:
CurveFittingEdge
继承自：
g2o::BaseUnaryEdge<1, double, CurveFittingVertex>
```
# NLOS-NN
## 2020,22 Refine dataset
Refine parameters(shape, positions, light intensity)
之前的数据集，我使用了原始算法计算了一下，发现还原效果不太好，于是重新调整了具体的参数，然后争取得到了较好的结果
![contrast.png](attachment:contrast.png)
## DataSet 
我目前使用的是MNIST数据集作为GroundTruth，使用Blender渲染出漫反射图像作为网络输入，图像数目10000张，分辨率800，800
因为MNIST数据集是黑白的，相对渲染出来的图像也应是黑白，所以对数据集灰度处理，然后分辨率缩小到126，126
## Render details
所有的数据集都是使用Blender脚本渲染得到的
### SceneOfInterest: 
(size = 1 ,location = (0.221,0,0.286),rotation = (math.pi/2,0,math.pi),scale = (0.816/2,0.620/2,0.500))
Materal: Emisson with strengh of 100W
### Occluder: 
(size = 0.075 ,location = (0.4893,0.5908,0.228),rotation = (math.pi/2,0,math.pi),scale = (1,1,1))
Materal: Diffuse surface, black
### ImagingWall:
(size = 1 ,location = (0.75,1.03,0.25),rotation = (math.pi/2,0,math.pi),scale = (2,2,2))\
Materal: Diffuse surface, white, and set to standard lamber surface
The size of ImagingWall is not necessorily be acurate because the camera only pictures part of it.  
然后为了证实Blender的有效性，我分别使用了Blender模拟结果和实际场景拍摄结果，分别使用原始算法运算，结果如下
![contrast.png](attachment:contrast.png)
## Net structure 
## Loss function 
$$ \min_{A, CNN} \sum_i \| A CNN(x_i) - y_i \|^2 + \lambda \| A - \hat{A} \|^2$$
## Auto encoder decoder 

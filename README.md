# NLOS-NN
## 2020,10,22 week01 更新数据集，学习VAE等生成模型，学习torch
优化数据集
之前的数据集，我使用了原始算法计算了一下，发现还原效果不太好，于是重新调整了具体的参数，然后争取得到了较好的结果  
### DataSet 

	规模：10000张  
	MNIST  ---- GroundTruth  
	Blender模拟 ---- 漫反射输入   原始大小为800，800，缩小至126，126
#### Render details


	所有的数据集都是使用Blender脚本渲染得到的
+ SceneOfInterest: 
`(size = 1 ,location = (0.221,0,0.286),rotation = (math.pi/2,0,math.pi),scale = (0.816/2,0.620/2,0.500))`

Materal: Emisson with strengh of 100W
+ Occluder: 
`(size = 0.075 ,location = (0.4893,0.5908,0.228),rotation = (math.pi/2,0,math.pi),scale = (1,1,1))`

Material: Diffuse surface, black
+ ImagingWall:
`(size = 1 ,location = (0.75,1.03,0.25),rotation = (math.pi/2,0,math.pi),scale =(2,2,2))\ `

Material: Diffuse surface, white, and set to standard lamber surface

然后为了证实Blender的有效性，我分别使用了Blender模拟结果和实际场景拍摄结果，分别使用原始算法运算，结果如下
![Alt text](https://github.com/wenruiLiA15/NLOS-NN/blob/main/contrast.png)
### 网络设计

+ Loss function 

	![](http://latex.codecogs.com/svg.latex?\min_{A,CNN}\sum_i\|ACNN(x_i)-y_i\|^2+\lambda\|A-\hat{A}\|^2)


+ 简单修改Alexnet 
## 2020,10,31 week02 学习torch，以及基础知识
## 2020,11,4 week03 编写代码

+ 完成数据导入
+ 确定模型和loss function
+ 训练

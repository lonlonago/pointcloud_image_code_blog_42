#  First, the principle of the algorithm 

##  1. Median filtering 

   The method of median filtering is to treat the current sampling point to be processed, select a template, which is composed of several data points in its vicinity, sort the point cloud data in the template from small to large, and then use the median value of the template to replace the value of the current sampling point. For a three-dimensional point cloud, the template is a sphere (as shown in Figure 1c), and for a sampling point in a three-dimensional point cloud, its neighborhood. All points in the neighborhood, for each channel (xyz axis direction) from large to small: 

   Take the data at the middle value as the surrogate value at the sampling point. From this, the point-to-point mapping of median filtering is obtained: 

 ![avatar]( 20210602184900801.png) 

   In this algorithm, the noise suppression effect is better, the detail information of the point cloud is basically maintained, and the noise reduction effect is also good for impulse noise, but the noise suppression effect is not very good for Gaussian noise.  

##  2. References 

>  [1] Zhu Zhihua, Liu Jin, Hu Xiyuan. Research on three-dimensional point cloud denoising technology of linear traces [J]. Criminal Technology, 2020, 45 (06): 556-561. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574483418
  ```  
#  III. Display of results 

 ![avatar]( 20210603082148106.png) 

 1. Point cloud before filtering 2. Point cloud after filtering  

#  IV. Reference link 

 [1] numpy库矩阵求最大值、最小值、平均值、方差标准差、中值、求和 


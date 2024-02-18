#  First, the principle of the algorithm 

##  1. Mean filtering 

   For the current sampling point to be processed, select a template composed of several adjacent data points, and replace the value of the current sampling point with the mean value of the template. For a three-dimensional point cloud, the template is a sphere (as shown in Figure 1c), that is, the value at a sampling point in the three-dimensional point cloud is replaced by the average value of the point set in its neighborhood: 

   Among them, is the neighborhood radius, the larger the radius value, the smoother the point cloud after denoising, but at the same time the loss of detail information will be more serious, usually artificially set in advance according to experience, is the number of midpoints. This method is simple to calculate, fast to calculate, and strong robustness to white noise. Its disadvantage is that it loses the details of the point cloud while reducing noise, which is prone to too smooth phenomenon. 

 ![avatar]( 20210602184900801.png) 

##  2. References 

>  [1] Zhu Zhihua, Liu Jin, Hu Xiyuan. Research on three-dimensional point cloud denoising technology of linear traces [J]. Criminal Technology, 2020, 45 (06): 556-561. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957444740
  ```  
#  III. Display of results 

 ![avatar]( 20210602190506724.png) 

 1. Point cloud before filtering 2. Point cloud after filtering  


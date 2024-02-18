#  First, the principle of the algorithm 

##  1. Implementation process 

   Guided Filter is generally used to denoise 2D images and other processing. In fact, 3D point clouds can be denoised after a slight modification. From the basic assumption of Guided Filter, the processing method for 3D data can be deduced. Here only the case where the guide data is the point cloud itself is considered. First, according to the local linear assumption, there are: In the formula, it is the three-dimensional point output after filtering, it is the point that currently needs to be filtered, it is a 3x3 matrix, and it is a 3x1 vector. We hope that this local linear model will have the smallest reconstruction error in the neighborhood of. To solve the above optimization problem, we can obtain: where is the 3x3 covariance matrix composed of all points in its neighborhood, which is the identity matrix, and is the mean of all points in its neighborhood. The Guided Filter for the three-dimensional case still maintains the advantage of the two-dimensional case, that is, it has a better protection effect on edges or sharp shapes. The strength of the smoothing effect can be changed by adjusting the radius sum of the domain search. In fact, the bilateral filter can also be used for 3D point cloud noise reduction, and the biggest advantage of the Guided Filter over the bilateral filter in the three-dimensional case is that it does not need to estimate the normal direction of each point in the point cloud. 

##  2. References 

>  [1] He K, Jian S, Tang X. Guided image filtering. [C]//European Conference on Computer Vision. Springer, Berlin, Heidelberg, 2010. [2] Wang Jian, Chen Zheng, Zhang Hualiang. Research on preprocessing of 3D point cloud data [J]. Science and Technology Innovation, 2021 (22): 115-118. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574463950
  ```  
#  III. Display of results 

 ![avatar]( 20210602111514674.png) 

 noise_bunny.png  denoise_bunny.png  

#  IV. Reference link 

 [1] https://github.com/aipiano/guided-filter-point-cloud-denoise [2]导向滤波(Guided Filter)公式详解 [3] Guided Filter对三维点云降噪 


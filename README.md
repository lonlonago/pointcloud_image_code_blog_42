 + 1, x-field filtering 2, y-field filtering 3, z-field filtering

#  First, the principle of the algorithm 

    The function of the pass filter is to filter out the points whose values are not within the given range in the direction of the specified dimension. The implementation principle is as follows: First, specify a dimension and the range under that dimension. Secondly, traverse each point in the point cloud to determine whether the value of the point on the specified dimension is within the range. Delete the points whose values are not within the range. Finally, the traversal is completed, and the remaining points constitute the filtered point cloud. The pass filter is simple and efficient, and is suitable for operations such as eliminating background. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574483017
  ```  
#  III. Display of results 

##  1. X-field filtering 

 ![avatar]( a51f90a6c40540c7b10ca9a6517df3fe.png) 

##  2. Y-field filtering 

 ![avatar]( 85575ee3e00746f8b954498990b8545f.png) 

##  3. Z-field filtering 

 ![avatar]( 138ef14c5f0a449c81d8b5ff9b4d050b.png) 



--------------------------------------------------------------------------------

#  code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574471797
  ```  
#  result display 

 ![avatar]( 93d39e3614cc49d0bdf62b606315852f.png) 

#  Related Links 

 [1] Scipy空间–计算凸包（convexHull) 



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

##  1. Definition of Gaussian noise 

   The Gaussian distribution, also known as the normal distribution, is denoted as the parameters of the distribution, which are the expectation and variance of the Gaussian distribution, respectively. When there is a definite value, it is also determined that the distribution, especially when, is the standard normal distribution. The so-called Gaussian noise refers to a type of noise whose probability density function obeys the Gaussian distribution (i.e. normal distribution). Note that in the generation of simulated measurement point clouds, this noise is only equivalent to moving an existing point by one position, rather than adding new points. 

##  2. Python Gaussian distribution function 

 Fitting from np.random.normal () to normal distribution 

>  Relevant literature on adding Gaussian noise: [1] Sun Wenxiao, Wang Jian, Liang Zhouyan, Ma Weili, Chen Zhe. Accurate registration of laser point clouds constrained by normal features [J]. Journal of Wuhan University (Information Science Edition), 2020, 45 (07): 988-995. [2] Peng Zhen, Lu Yuanjian, Qu Chao, Zhu Dahu. Point cloud registration based on key point extraction and optimization of iterative closest points [J]. Advances in Laser and Optoelectronics, 2020, 57 (06): 68-79. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574429444
  ```  
#  III. Display of results 

 ![avatar]( 20210305102646657.png) 

#  IV. Relevant links 

 [1] PCL 点云添加高斯噪声并保存 



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

##  1. Evenly distributed 

   In probability theory and statistics, a uniform distribution, also known as a rectangular distribution, is a symmetric probability distribution in which the probability of a distribution at the same length interval is equally likely. The uniform distribution is defined by two parameters, a and b, which are the minimum and maximum values on the number line, usually abbreviated as. 

##  2. Main functions 

   The uniform () method of the random module in numpy will randomly generate the next real number in the range [x, y]. The function returns a floating-point number N with values in the range: x < = N < = y if x < y, y < = N < = x if y < x. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574483481
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574483481
  ```  
#  III. Display of results 

 ![avatar]( dd8f5051cb8a40a39c70cc672db1525e.png) 



--------------------------------------------------------------------------------

#  Function analysis 

   Point clouds and triangular meshes are very flexible but irregular geometric types. Voxel meshes are another type of geometry in 3D that is defined on a regular 3D mesh, and voxels can be thought of as 3D counterparts of 2D pixels. VoxelGrid in Open3D, can be used to work with voxel meshes. 

##   1. Building voxels from triangulation networks 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574424760
  ```  
 Creates a voxel mesh from the given triangle mesh. Does not convert color information. The boundaries of the created voxel mesh are computed from the triangle mesh. 

   Function create_from_triangle_mesh implementation creates a voxel mesh from a triangle mesh. It returns a voxel mesh where all voxels intersecting the triangle are set to 1 and all other voxels are set to 0. The parameter voxel_size defines the resolution of the voxel mesh. 

##   2. Building voxels from point clouds 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574424760
  ```  
   Function create_from_point_cloud implements creating a voxel mesh from a point cloud. A voxel is occupied if at least one point of the point cloud is within that voxel. The color of a voxel is the average of all points within the voxel. The parameter voxel_size defines the resolution of the voxel mesh. 

##   3. Determine whether the point is in the voxel 

   A voxel grid can also be used to test whether a point is inside an occupied voxel. Method check_if_includes takes an (n, 3) array as input and outputs a bool array. 

#  Code implementation 

##   1. Building voxels from triangulation networks 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574424760
  ```  
 ![avatar]( 20201204171127406.png) 

##   2. Building voxels from point clouds 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574424760
  ```  
 ![avatar]( 20201204171935838.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm flow 

 ![avatar]( fb64df3973984b36ae684a4cca16a0ed.png) 

   Delaunay triangulation is a bridge between computer vision and computer graphics. It connects scattered point clouds in three-dimensional space into an optimized spatial triangular grid, reflecting the topological connection relationship between data points and their adjacent points, maintaining the global information of point cloud data and establishing local relevance. The established triangular network reflects the topology of the target object represented by the scattered data set. Feature 1 The triangular network is unique, and there are no other points within the circumscribed circle of any triangle in the Delaunay triangular network. The empty circle characteristics are shown in Figure 1 (a). Feature 2 In the triangulation formed by the scatter set, the minimum angle of the triangle formed by the Delaunay triangulation is the largest. After exchanging two adjacent triangles to form the diagonal of the convex quadrilateral, the minimum angle of the two inner angles no longer increases. The maximum minimum angle characteristic is shown in Figure 1 (b).  

 ![avatar]( 38f7c763012841e5ae741488e1d88bf7.jpg) 

   According to the above characteristics, the point-by-point insertion method is used to generate a Delaunay triangular network. The generation process is shown in Figure 3. The specific steps are as follows. Step1: For a known point set, find a rectangle containing the point set as an auxiliary window, and connect any diagonal line to form two triangles. As the initial Delaunay triangular mesh, insert points in the initial Delaunay triangular mesh. Step2: Start from the triangle where it is located, search for the adjacent triangles of the triangle, and perform empty circumscribed circle detection. Step3: Find all the triangles containing points in the circumscribed circle and delete them to form the contained polygonal cavity.  

 ![avatar]( 6870e64d061749d2a244e7b3a6044b51.jpg) 

 Step4: Connect P with each vertex of the Delaunay cavity to form a new Delaunay triangular mesh and delete the auxiliary window. After all the points in the point set are inserted into the triangular mesh, all the triangles containing the auxiliary windows are deleted to complete the generation process of the Delaunay triangular network. The generated Delaunay triangular network is shown in Figure 3.  

##  2. References 

>  [1] LIU Jian, Bai Di. Three-dimensional point cloud registration algorithm based on feature matching [J]. Chinese Journal of Optics, 2018, 38 (12): 240-247. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574419258
  ```  
#  III. Display of results 

 ![avatar]( 35a966e742a042178b44f9aa47c8ac7a.png) 

 Point cloud, generating triangulation  

#  IV. Relevant links 

 [1] 【Python】scipy.spatial.Delaunay中文教程 



--------------------------------------------------------------------------------

#  I. Remarks 

   The operation implemented by this code is relatively simple, find the centroid point of the out-point cloud, subtract the coordinates of the centroid point from each point, and finally save it as point cloud data. It can play a role in hiding the real coordinate information of the point cloud. This step is also one of the small steps in the operations of SVD transformation matrix, principal component analysis covariance matrix, etc. Therefore, it is necessary to write the implementation code. 

##  1. Main functions 

#  Code implementation 

##  1. Method 1 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574444597
  ```  
##  2. Method 2 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574444597
  ```  
#  III. Display of results 

 ![avatar]( ee99c677079c48cf92f3b3f473d4d54b.png) 

#  C++ version 

 C++ version of the code implementation reference: PCL point cloud to centroid 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

 See: pclpy point cloud Euclidean clustering segmentation 

##  2. References 

>  [1] Yang Xu. Filtering and segmentation processing of lidar point cloud data [D]. Harbin Institute of Technology, 2020. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574465352
  ```  
#  III. Display of results 

##  1. Primitive point cloud 

 ![avatar]( 942933a81ef5476b924b9c21efbfbad2.png) 

##  2. Segmentation results 

 ![avatar]( 7fce7b13ea144a0db1fafa1af8e03d12.png) 

#  C++ code 

 PCL European clustering segmentation 

#  Test data 

>  Copy and paste it into the txt text document, and then use the CloudCompare software to convert it to pcd format. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574465352
  ```  


--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the paper 

   Segmentation from point cloud data is essential in many applications, such as remote sensing, mobile robots, or autonomous cars. However, point clouds captured by 3-D distance sensors are often sparse and unstructured, which poses a challenge for efficient segmentation. A fast solution for segmentation of point cloud instances with small computation is missing. To this end, a new Fast Euclidean Clustering (FEC) algorithm is proposed, which applies a point clustering algorithm on the basis of existing clustering algorithms and avoids constantly traversing every point. 

##  2. Implementation process 

 ![avatar]( f11acd12a73b4a85804629075e21ce2b.png) 

   First, zero all the points in the point cloud, initialize the segmentation to 1, and then traverse all the points. When the traversal point is found to be 0, find the nearest associated point. If there is a point that is not 0, find the smallest value, which means there is a connection. If there is no value, assign it, and then traverse the nearest point. If you find other values greater than that, traverse all the points again, and then reset all other values to the value of. As shown in the figure below, the pseudocode process in the paper is very clear, just write the code with reference to the process.   

##  3. References 

>  [1] Cao Y , Wang Y , Xue Y , et al. FEC: Fast Euclidean Clustering for Point Cloud Segmentation[J]. arXiv e-prints, 2022. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574476432
  ```  
#  III. Display of results 

 ![avatar]( 69c859601b2e4de7a19045376d4f4b49.png) 

#  IV. Experimental data 

 Link: https://pan.baidu.com/s/1JdXGgBMRBk6Ynbx6-pfiUw Extraction code: oupg 



--------------------------------------------------------------------------------

Both ICP registration and color point cloud registration are called local registration methods because they rely on coarse alignment for initialization. This tutorial shows another class of registration methods called global registration. This family of algorithms does not require alignment when initializing. They usually produce less tightly aligned results and are used as initializations for local methods. 

##  visualization 

 This helper function visualizes the converted source point cloud together with the target point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
##  Extract geometric features 

 The point cloud is downsampled, the normals are estimated, and the FPFH feature of each point is calculated. The FPFH feature is a 33-dimensional vector that describes the local geometry of a point. Nearest neighbor queries in 33-dimensional space can return points with similar local geometries. See [Rasu2009] for details. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
##  input 

 The following code reads the source and destination point clouds from two files. The pair of point clouds is misaligned after using the identity matrix as the initial matrix. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211110731704.png) 

##  RANSAC 

 Use RANSAC for global registration. In each RANSAC iteration, ransac_n random points are selected from the source point cloud. By querying nearest neighbors in the 33-dimensional FPFH feature space, their corresponding points in the target point cloud can be detected. The pruning step requires the use of a fast pruning algorithm to reject false matches early. Open3D provides the following pruning algorithms: 

 Only matches through pruning steps are used to calculate transformations and validate on the entire point cloud. The core function is registration_ransac_based_on_feature_matching. The most important hyperparameter of this function is ransaconvergence. It defines the maximum number of RANSAC iterations and the maximum number of validations. The larger these two values, the more accurate the result, but at the same time it takes more time. Set the hyperparameters of RANSAC based on the experience provided by [Choi2015]. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211113446441.png) 

>  Attention:

Open3D provides a faster implementation for global registration. See Fast global registration. 

##  local optimization 

 Due to performance concerns, global registration is only performed on a large number of downsampled point clouds. The registration results are not precise enough, so we use Point-to-plane ICP to further optimize the registration results. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211114944536.png) 

##  Fast global registration 

 Due to numerous model recommendations and evaluations, global registration based on RANSAC takes a long time. [Zhou2016] proposes an accelerated method that can quickly optimize line processing weights with little correspondence. Since each iteration does not involve model recommendations and evaluations, the method proposed in [Zhou 2016] can save a lot of computational time. This tutorial compares the running time of RANSAC-based global registration with the [Zhou2016] method. 

###  input 

 We use the globally registered input example above. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211115403430.png) 

###  benchmark 

 In the following code, the global registration algorithm is timed. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211115620918.png) 

###  Fast global registration 

 Using the same input as the benchmark, the following code calls the algorithm implemented in the paper [Zhou2016]. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957443906
  ```  
 ![avatar]( 20210211115941598.png) 

  After proper configuration, the accuracy of fast global registration is even comparable to that of ICP. For more experimental results, please refer to [Zhou2016]. 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

   The point cloud is equally spaced slices along the axis, and the code extracts a 0.04m thick slice every 0.4m along the Z axis. 

##  2. Preview of results 

>  White is the original point cloud, purple is the sliced point cloud. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574461923
  ```  
#  III. Display of results 

 ![avatar]( cea347c156b049ceabe770e63f8b67c1.png) 

#  IV. Relevant links 

 PCL point cloud is equally sliced along the coordinate axis 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

   The quadratic surface equation is as follows: the least squares method is used to fit the local quadratic surface, and the objective function is established as: the joint vertical equation (1) and the equation (2), the partial derivative of the coefficients is obtained, and the partial derivative is equal to zero to obtain the linear equation system, see the equation (3), solve the linear equation system, and obtain the local quadratic fitting surface equation.  

##  2. References 

>  [1] Equation Xi, Sui Beginning of Spring, Zhu Haixiong. LiDAR point cloud thinning algorithm for highway survey design [J]. Bulletin of Surveying and Mapping, 2017 (10): 58-61 + 88. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574468705
  ```  
#  III. Display of results 

 1. Fitting equation 2. Point cloud 3. Point display 4. Display the fitted surface  

#  IV. Excellent blog 

 [1] python最小二乘法 实现 曲面拟合 [2] 数学建模入门-python拟合曲面 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Calculation process 

   The transformation matrix of the two-dimensional mirror transformation is: The transformation matrix of the three-dimensional mirror transformation is: Note: The mirror transformation belongs to the reflection transformation, which requires the reflection plane to pass through the origin, while the reflection transformation is not a strict rigid change, so there is deformation. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574412493
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574412493
  ```  
 ![avatar]( ba3373c2d74a4a4eb7de7dac1b47ea10.png) 

#  IV. Relevant links 

 [1] Open3D 点云变换 [2] python点云处理算法汇总(长期更新版) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

 ![avatar]( 4407c48bc7d748ce9f5bb3d0700114f7.png) 

   Refer to the pointnet2 source code lines 15 to 22, and use Open3D for implementation.  

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574479151
  ```  
#  III. Display of results 

 ![avatar]( 94f3ba11bbe04b21ae1d303132604d04.png) 

   Comparison before and after normalization, this rabbit is not the original data source of Stanford Rabbit. Therefore, it is red before normalization and green after normalization.  



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

   The general equation of the three-dimensional space plane is: assume that the coordinates of the three-dimensional space that is not on the plane are, and the coordinates of the projection point on the plane are. Because the projection point to the current point is perpendicular to the plane, according to the vertical constraint condition, the following conditions are satisfied: Substituting (2) and (3) into (1) can be solved: substituting (4) into (2), (3), we can get: 

   Projection coordinates from three-dimensional point to plane are obtained. 

##  2. References 

>  [1] JIA Dingfan, XIE Xiaoyao, LIU Song. Point cloud feature extraction method based on normal vector and projection plane [J]. Journal of Chongqing University of Science and Technology (Natural Science Edition), 2021, 23 (03): 84-88. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574421523
  ```  
#  III. Display of results 

 ![avatar]( ca60f03f18144df0ab1fa0f25a493340.png) 

 Primitive point cloud, projected point cloud   



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

    Given the center and radius of a sphere in space, the coordinates projected onto the sphere for any point in space 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574495132
  ```  
#  III. Display of results 

##  1. Primitive point cloud 

 ![avatar]( adeffab4f0bb417583cc00dc8a1ef046.png) 

##  2. Point cloud after projection 

 ![avatar]( 30b05bb3a26f4524a374322f1a4ff0a4.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

   There are three ways to express straight line equations: general formula, point-to-point formula, and parametric formula. PCL uniformly adopts the point-to-point formula, the point-to-point equation of a straight line, and the coordinates of the projection point from a point outside the line to the line 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574442326
  ```  
#  III. Display of results 

 ![avatar]( e733db381f824ca6bb10718e10655f83.png) 



--------------------------------------------------------------------------------


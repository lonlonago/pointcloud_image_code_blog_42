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


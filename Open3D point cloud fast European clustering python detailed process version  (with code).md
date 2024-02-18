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


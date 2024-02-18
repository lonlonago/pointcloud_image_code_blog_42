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


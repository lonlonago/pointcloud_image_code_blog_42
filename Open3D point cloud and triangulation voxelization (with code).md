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


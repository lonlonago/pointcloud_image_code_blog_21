#  I. Introduction 

The Matlab version is 2022b. 

>  Poisson surface reconstruction is a triangulation reconstruction algorithm based on implicit functions. This kind of method obtains the approximate surface we want by optimizing the interpolation processing of the point cloud. The specific implementation process is roughly as follows: First calculate the normal vector of each point in the point cloud, assuming that all points are located on the surface S of an unknown model, then the goal of the algorithm is to estimate the indicator function of the model and extract the isosurface, and finally use the MC algorithm to complete the reconstruction process of the surface. Among them, in the indicator function, 1 represents the point inside the surface, 0 represents the outside of the surface, and the layer of the indicator function is 0 everywhere, and the tangent should be equal to the normal vector. As shown in the figure below, it is a demonstration diagram of the 2-dimensional indicator function and Poisson curve. 

![avatar]( 58c3ca8b999049089247673ac5fcfd34.png) 

>  Here is just a brief explanation. The specific process of Poisson surface reconstruction is relatively complicated. For the specific content, please refer to the references at the end of the article for in-depth understanding. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574049721
 ```  
#  III. Achieving results 

![avatar]( 89d3ed34ccc941ae9bf6535c75fe200d.png) 

 ![avatar]( f2bddd9c54904400a92053c97a21b9e7.png) 

#  reference 

>  [1] Matlab Help Documentation [2] CloudCompare & PCL Poisson Surface Reconstruction Algorithm 


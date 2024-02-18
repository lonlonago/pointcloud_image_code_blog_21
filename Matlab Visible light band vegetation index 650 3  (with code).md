#  I. Introduction 

>  Vegetation index is often used in remote sensing images, which can reflect the background influence of plant canopy, such as soil, wet ground, snow, dead leaves, roughness, etc., and these indices are often related to vegetation cover. NDVI, WDVI, etc. are often used in remote sensing images to evaluate the relevant parameters of vegetation or water bodies, and this theory is also applicable to point cloud data. Here we take the visible light band as an example to calculate the visible light band vegetation index of a small area point cloud data. 

The visible light band is mainly composed of three bands of RGB, so our point cloud data must have color information. In the case of ensuring that none of these three bands are 0, the calculation method is as follows: 

#  Implementation code 

>  VegetationIndex.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957403668
 ```  
#  III. Achieving results 

![avatar]( dff1bf2531904d0db7a7228c1a04deb9.png) 

 ![avatar]( 236b8af7d0d140739810fc5dbd7a75f4.png) 

 Of course, if the value is adjusted smaller, the index can also be used to extract buildings within a certain range. 

#  IV. References 

>  [1] TerraSoild software 


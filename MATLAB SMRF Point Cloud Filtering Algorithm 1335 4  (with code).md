#  I. Introduction 

>  This is a simplified version of the progressive morphological point cloud filtering algorithm. The entire algorithm process is as follows: 

![avatar]( 6d3d2506250b461ba4f376095d7136fb.png) 

>  This algorithm may not be as accurate as the progressive morphology method in PCL, but it is much faster than the method in PCL and is suitable for processing large amounts of data. 

#  II. Relevant parameters 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
Specifies the size of the grid element, such as 1m. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
Specifies the maximum radius of the disc-shaped structural element (this refers to the disc-shaped structural element in MATLAB) in the morphological open operation, which defaults to 18. Increasing this value can divide large buildings into non-ground, but at the expense of additional computation. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
The slope threshold is used to identify non-ground mesh elements in the minimum elevation surface map. If the slope of the mesh element is greater than this value, the function classifies it as non-ground. Increasing this value classifies a steep slope as ground. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
Identifies the elevation threshold for a non-grounding point. If the elevation difference between a point and the estimated ground is greater than this value, the function classifies the point as non-ground. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
Set the elevation threshold scaling factor for estimating surface slope. Increase this value to identify ground points on steep slopes. 

#  III. Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026759
 ```  
#  IV. Achieving results 

![avatar]( 49670ad908a94fc99fb04507de9afa59.png) 

#  reference 

>  [1]Matlab帮助文档 [2]An improved simple morphological filter for the terrain classification of airborne LIDAR data 


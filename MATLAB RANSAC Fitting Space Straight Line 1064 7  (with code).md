#  I. Introduction 

>  As discussed in the previous article, a straight line in three dimensions is different from a straight line in two dimensions. It cannot be written in the form of ax + by + cz + d = 0, because this is a plane expression in three-dimensional space. Then a line expression in three-dimensional space is generally a combination of two planes, but this is also relatively complicated. Therefore, here we use the expression of a point-oriented straight line to perform the line fitting process. 

>  1. Determine the model. Due to the point-to-point formula we use here, only two points need to be selected to satisfy the condition. 2. Calculate the error. Calculate how many points in the point set meet the distance threshold set by our implementation (or other conditions). Here we are the number of points. 3. Select the model. Repeat the process of 1-2 to select the model with the most supported points as the optimal solution to the problem. 

#  Implementation code 

>  line.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095740938
 ```  
#  III. Achieving results 

![avatar]( be3f3c45525f4e268144ee7979d76475.png) 

 ![avatar]( 0055d7f5aa334f08a9e1be742e1a44a5.png) 

#  reference 

>  [1] Open3D point cloud least squares method for fitting straight lines in space 


#  I. Introduction 

>  1. Determine the model. Here we are the cylinder, which requires at least two points to calculate the model, and these two points must have the corresponding normal vector. (This is different from the MATLAB built-in function, which requires at least 6 points to fit the cylinder) 2. Calculate the model parameters. Because no corresponding literature was found, we can only refer to the PCL source code here. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957407265
 ```  
>  3. Calculation error. Calculate how many points in the set of points meet the distance threshold set by our implementation (and can also be other conditions).

4. Select the model. Repeat the process of 1-3 to select the model with the most supported points as the optimal solution to the problem. 

#  Implementation code 

>  RANSACFitCylinder.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957407265
 ```  
#  III. Achieving results 

![avatar]( 77cd7c9640ab454ab3317e54e1dc4283.png) 

#  reference 

>  [1] CloudCompare & PCL RANSAC Extraction Cylinder 


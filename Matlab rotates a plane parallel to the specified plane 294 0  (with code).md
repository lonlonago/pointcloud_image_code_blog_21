#  I. Introduction 

>  An interesting feature is implemented here, which rotates one plane to be parallel to the other. 

Since the plane can be represented by a normal vector with a point, essentially the rotation of the plane can be mapped to the rotation of two normal vectors. 

>  There are many ways to represent rotation, such as the more common Euler angle representation, the angular axis representation, and the quaternion representation, etc. Here I use a relatively simple angular axis representation to intuitively calculate the rotation matrix between two normal vectors. The specific formula is shown in the figure below: 

![avatar]( 360855ae9a424c11a8577722e184afc7.png) 

#  Implementation code 

>  rotate.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957407592
 ```  
>  createPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957407592
 ```  
#  III. Achieving results 

![avatar]( 54c03788bef343449acfd47f955d77ed.png) 

 ![avatar]( e21811f96246421193cc63cdb368a7d4.png) 

#  reference 

>  [1]https://zh.wikipedia.org/wiki 


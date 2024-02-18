#  Overview of the principle 

>  The SOR filtering in PCL is also implemented to facilitate later use. Its principle is to filter outliers by querying the statistical judgment of the distance between the point and the neighborhood point set. Assuming that the neighboring point set of a point conforms to the positive distribution, we can calculate the average distance meanD and standard deviation from the point to all its neighbors 

          s 

         \sigma 

     In theory, most of the neighboring points should be in meanD + 

          3 

          s 

         3\sigma 

     In the range of 3 (where we specify k times) 

          s 

         \sigma 

     Therefore, points larger than this threshold can be defined as discrete points and deleted. 

#  Implementation code 

>  SOR.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957406723
 ```  
#  III. Achieving results 

![avatar]( 6a30bbd9b43043fd8af35937eda41972.png) 


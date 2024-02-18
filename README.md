#  I. Introduction 

The function is simple. Sample the point cloud at equal intervals, that is, draw a point every few points. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079748
 ```  
#  III. Achieving results 

![avatar]( d3c556571389468ab16bbe5d490f145a.png) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Matlab provides us with a variety of ways to visualize point clouds, and here we organize them. The specific meaning of each parameter has been written in the comments in the code. 

#  Implementation code 

>  The main functions are: pcshow, showShape, pcplayer, and pcshowpair. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574078230
 ```  
#  III. Achieving results 

![avatar]( eaf35d66509c416aa2a03aa7e5d45c39.png) 

 ![avatar]( a0d38083275348ffba668bfe9ef0848c.png) 

 ![avatar]( 2515ccb47c0f4aafb968604ea80af1ed.png) 

 ![avatar]( c791ff8e545d4f0c9eaba0091f159674.png) 

#  reference 

>  [1] Matlba Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The distance from a point to a line segment is more complex than the distance from a point to a line, because it requires consideration of the constraints of the two endpoints of the line segment, and special treatment is required when the range of these two endpoints is exceeded. 

#  Implementation code 

>  Point2SegFunc.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574029788
 ```  
>  Point2Seg.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574029788
 ```  
#  III. Achieving results 

![avatar]( 3e4364f57fe54133a5be8a3cabb9ebbb.png) 

#  reference 

>  [1]Geometric Tools for Computer Graphics 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  The random function is used to randomly select the points in the point cloud. Since Matlab does not specify a fixed number of sampling points for selection, it is also implemented here. The whole process refers to the source code in Open3D. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574061719
 ```  
#  III. Achieving results 

![avatar]( 760a54b8ffcb4852b65c79ad59fa0b0b.png) 

#  reference 

>  [1] Open3D source code 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, algorithm implementation 

##  1.1 Implementation steps 

>  1. Determine the model. Therefore, our model is spherical, so four points can determine a sphere, and the equation is 

          ( 

          x 

          − 

           c 

           1 

           ) 

           2 

          + 

          ( 

          y 

          − 

           c 

           2 

           ) 

           2 

          + 

          ( 

          z 

          − 

           c 

           3 

           ) 

           2 

          = 

           r 

           2 

         (x-c_1)^2+(y-c_2)^2+(z-c_3)^2=r^2 

     (X − c1) 2 + (y − c2) 2 + (z − c3) 2 = r2. 2. Derive the formula and find  

           c 

           1 

          , 

           c 

           2 

          , 

           c 

           3 

         c_1,c_2,c_3 

     C1, c2, c3. 3. Calculate the error. Calculate how many points in the point set meet the distance threshold (or other conditions) set by our implementation. Here is the number of points. 4. Select the model. Repeat the process of 1-3 to select the model with the most supported points as the optimal solution to the problem. 

>  The derivation process is as follows:  

           ( 

           x 

           − 

            c 

            1 

            ) 

            2 

           + 

           ( 

           y 

           − 

            c 

            2 

            ) 

            2 

           + 

           ( 

           z 

           − 

            c 

            3 

            ) 

            2 

           = 

            r 

            2 

          (x-c_1)^2+(y-c_2)^2+(z-c_3)^2=r^2 

      (X − c1) 2 + (y − c2) 2 + (z − c3) 2 = r2 takes four points, as follows:  

           { 

                ( 

                 x 

                 1 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 1 

                − 

                 c 

                 2 

                 ) 

                 2 

                + 

                ( 

                 z 

                 1 

                − 

                 c 

                 3 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                1 

                ) 

                ( 

                 x 

                 2 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 2 

                − 

                 c 

                 2 

                 ) 

                 2 

                + 

                ( 

                 z 

                 2 

                − 

                 c 

                 3 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                2 

                ) 

                ( 

                 x 

                 3 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 3 

                − 

                 c 

                 2 

                 ) 

                 2 

                + 

                ( 

                 z 

                 3 

                − 

                 c 

                 3 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                3 

                ) 

                ( 

                 x 

                 4 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 4 

                − 

                 c 

                 2 

                 ) 

                 2 

                + 

                ( 

                 z 

                 4 

                − 

                 c 

                 4 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                3 

                ) 

          \begin{cases} (x_1-c_1)^2+(y_1-c_2)^2+(z_1-c_3)^2=r^2, (1) \\ (x_2-c_1)^2+(y_2-c_2)^2+(z_2-c_3)^2=r^2, (2)\\ (x_3-c_1)^2+(y_3-c_2)^2+(z_3-c_3)^2=r^2, (3)\\ (x_4-c_1)^2+(y_4-c_2)^2+(z_4-c_4)^2=r^2, (3)\\ \end{cases} 

      (x1 -c1)2+ (y1 -c2)2+ (z1 -c3)2=r2, (1) (x2 -c1)2+ (y2 -c2)2+ (z2 -c3)2=r2, (2) (x3 -c1)2+ (y3 -c2)2+ (z3 -c3)2=r2, (3) (x4 -c1)2+ (y4 -c2)2+ (z4 -c4)2=r2, (3)  (1) (2), (1) (3), (1) (4) ison, "I'm not sure.  

           { 

                ( 

                 x 

                 1 

                − 

                 x 

                 2 

                ) 

                 c 

                 1 

                + 

                ( 

                 y 

                 1 

                − 

                 y 

                 2 

                ) 

                 c 

                 2 

                + 

                ( 

                 z 

                 1 

                − 

                 z 

                 2 

                ) 

                 c 

                 3 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   2 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   2 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   2 

                   2 

                  ) 

                 2 

                ( 

                 x 

                 1 

                − 

                 x 

                 3 

                ) 

                 c 

                 1 

                + 

                ( 

                 x 

                 1 

                − 

                 y 

                 3 

                ) 

                 c 

                 2 

                + 

                ( 

                 z 

                 1 

                − 

                 z 

                 3 

                ) 

                 c 

                 3 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   3 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   3 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   3 

                   2 

                  ) 

                 2 

                ( 

                 x 

                 1 

                − 

                 x 

                 4 

                ) 

                 c 

                 1 

                + 

                ( 

                 x 

                 1 

                − 

                 y 

                 4 

                ) 

                 c 

                 2 

                + 

                ( 

                 z 

                 1 

                − 

                 z 

                 4 

                ) 

                 c 

                 3 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   4 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   4 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   4 

                   2 

                  ) 

                 2 

          \begin{cases} (x_1-x_2)c_1+(y_1-y_2)c_2+(z_1-z_2)c_3=\frac{(x_1^2-x_2^2)+(y_1^2-y_2^2)+(z_1^2-z_2^2)}{2}\\ (x_1-x_3)c_1+(x_1-y_3)c_2+(z_1-z_3)c_3=\frac{(x_1^2-x_3^2)+(y_1^2-y_3^2)+(z_1^2-z_3^2)}{2}\\ (x_1-x_4)c_1+(x_1-y_4)c_2+(z_1-z_4)c_3=\frac{(x_1^2-x_4^2)+(y_1^2-y_4^2)+(z_1^2-z_4^2)}{2}\\ \end{cases} 

      (x1 − x2) c1 + (y1 − y2) c2 + (z1 − z2) c3 = 2 (x12 − x22) + (y12 − y22) + (z12 − z22) (x1 − x3) c1 + (x1 − y3) c2 + (z1 − z3) c3 = 2 (x12 − x32) + (y12 − z32) (x1 − x4) c1 + (x1 − y2) c2 + (z1 − 4) c2 (x12 − y32) c3 (x42 +) − y42) + (z12 − z42)  x1, y1, x2, y2, x3, y3, x4, y4,   

               ∣ 

                    ( 

                     x 

                     1 

                    − 

                     x 

                     2 

                    ) 

                    ( 

                     y 

                     1 

                    − 

                     y 

                     2 

                    ) 

                    ( 

                     z 

                     1 

                    − 

                     z 

                     2 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     x 

                     3 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     y 

                     3 

                    ) 

                    ( 

                     z 

                     1 

                    − 

                     z 

                     3 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     x 

                     4 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     y 

                     4 

                    ) 

                    ( 

                     z 

                     1 

                    − 

                     z 

                     4 

                    ) 

               ∣ 

               ≠ 

               0 

          \begin{matrix} \begin{vmatrix} (x_1-x_2) & (y_1-y_2) & (z_1-z_2)\\ (x_1-x_3) & (x_1-y_3) & (z_1-z_3)\\ (x_1-x_4) & (x_1-y_4) & (z_1-z_4)\\ \end{vmatrix} & \neq 0 \end{matrix} 

      ∣∣∣∣∣∣​(x1​−x2​)(x1​−x3​)(x1​−x4​)​(y1​−y2​)(x1​−y3​)(x1​−y4​)​(z1​−z2​)(z1​−z3​)(z1​−z4​)​∣∣∣∣∣∣​​​=0​ 假设：  

           { 

                 a 

                 11 

                = 

                 x 

                 1 

                − 

                 x 

                 2 

                 a 

                 12 

                = 

                 y 

                 1 

                − 

                 y 

                 2 

                 a 

                 13 

                = 

                 z 

                 1 

                − 

                 z 

                 2 

                 a 

                 21 

                = 

                 x 

                 1 

                − 

                 x 

                 3 

                 a 

                 22 

                = 

                 x 

                 1 

                − 

                 y 

                 3 

                 a 

                 23 

                = 

                 z 

                 1 

                − 

                 z 

                 3 

                 a 

                 31 

                = 

                 x 

                 1 

                − 

                 x 

                 4 

                 a 

                 32 

                = 

                 x 

                 1 

                − 

                 y 

                 4 

                 a 

                 33 

                = 

                 z 

                 1 

                − 

                 z 

                 4 

                 b 

                 1 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   2 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   2 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   2 

                   2 

                  ) 

                 2 

                 b 

                 2 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   3 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   3 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   3 

                   2 

                  ) 

                 2 

                 b 

                 3 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   4 

                   2 

                  ) 

                  + 

                  ( 

                   y 

                   1 

                   2 

                  − 

                   y 

                   4 

                   2 

                  ) 

                  + 

                  ( 

                   z 

                   1 

                   2 

                  − 

                   z 

                   4 

                   2 

                  ) 

                 2 

          \begin{cases} a_{11}=x_1-x_2\\ a_{12}=y_1-y_2\\ a_{13}=z_1-z_2\\ a_{21}=x_1-x_3\\ a_{22}=x_1-y_3\\ a_{23}=z_1-z_3\\ a_{31}=x_1-x_4\\ a_{32}=x_1-y_4\\ a_{33}=z_1-z_4\\ b_1=\frac{(x_1^2-x_2^2)+(y_1^2-y_2^2)+(z_1^2-z_2^2)}{2}\\ b_2=\frac{(x_1^2-x_3^2)+(y_1^2-y_3^2)+(z_1^2-z_3^2)}{2}\\ b_3=\frac{(x_1^2-x_4^2)+(y_1^2-y_4^2)+(z_1^2-z_4^2)}{2}\\ \end{cases} 

      ⎩⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎧​a11​=x1​−x2​a12​=y1​−y2​a13​=z1​−z2​a21​=x1​−x3​a22​=x1​−y3​a23​=z1​−z3​a31​=x1​−x4​a32​=x1​−y4​a33​=z1​−z4​b1​=2(x12​−x22​)+(y12​−y22​)+(z12​−z22​)​b2​=2(x12​−x32​)+(y12​−y32​)+(z12​−z32​)​b3​=2(x12​−x42​)+(y12​−y42​)+(z12​−z42​)​​ 那么此时的方程就可以写作：  

           A 

           c 

           = 

           b 

           , 

           c 

           = 

            A 

             − 

             1 

           b 

          Ac=b,c=A^{-1}b 

      Ac=b,c=A−1b 

##  1.2 Implementation code 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574060471
 ```  
>  DrawSphere.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574060471
 ```  
#  Realize the effect 

![avatar]( 027f400ec06a48e0855000e5e9f7f439.png) 

![avatar]( 0e28da2e5dcf473e96c17721eb7a674e.png) 



--------------------------------------------------------------------------------

Although I had used the RANSAC algorithm in PCL before, I was still curious about its principle, so I made another note.  

#  I. Introduction 

>  Specific algorithm content can refer to these articles: https://blog.csdn.net/dayuhaitang1/article/details/109427412, here will not be repeated. 

#  Second, algorithm implementation 

##  2.1 Algorithm steps 

The following step is actually a general step for random sampling consistency: 

>  1. Determine the model. For example, this paper wants to fit a circle, so our model is the prototype, so three points can determine a circle, and the equation is 

          ( 

          x 

          − 

           c 

           1 

           ) 

           2 

          + 

          ( 

          y 

          − 

           c 

           2 

           ) 

           2 

          = 

           r 

           2 

         (x-c_1)^2+(y-c_2)^2=r^2 

     (X − c1) 2 + (y − c2) 2 = r2. 2. Derive the formula. In fact, how to find 

           c 

           1 

          , 

           c 

           2 

         c_1,c_2 

     C1, c2. 3. Calculation error. That is, how many points in the calculation point set meet the threshold set by our implementation (of course, other conditions can also be used). Here is the number of points. 4. Select the model. Repeat the process of 1-3 to select the model with the most supported points as the optimal solution to the problem. 

>  Three points determine the formula for a circle:  

           ( 

           x 

           − 

            c 

            1 

            ) 

            2 

           + 

           ( 

           y 

           − 

            c 

            2 

            ) 

            2 

           = 

            r 

            2 

          (x-c_1)^2+(y-c_2)^2=r^2 

      (X − c1) 2 + (y − c2) 2 = r2, then take three points and we have:  

           { 

                ( 

                 x 

                 1 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 1 

                − 

                 c 

                 2 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                1 

                ) 

                ( 

                 x 

                 2 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 2 

                − 

                 c 

                 2 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                2 

                ) 

                ( 

                 x 

                 3 

                − 

                 c 

                 1 

                 ) 

                 2 

                + 

                ( 

                 y 

                 3 

                − 

                 c 

                 2 

                 ) 

                 2 

                = 

                 r 

                 2 

                , 

                ( 

                3 

                ) 

          \begin{cases} (x_1-c_1)^2+(y_1-c_2)^2=r^2, (1) \\ (x_2-c_1)^2+(y_2-c_2)^2=r^2, (2)\\ (x_3-c_1)^2+(y_3-c_2)^2=r^2, (3)\\ \end{cases} 

      (x1 -c1)2+ (y1 -c2)2=r2, (1) (x2 -c1)2+ (y2 -c2)2=r2, (2) (x3 -c1)2+ (y3 -c2)2=r2, (3) (1) (2 (1) (3)国 (1) (3)if:  

           { 

                ( 

                 x 

                 1 

                − 

                 x 

                 2 

                ) 

                 c 

                 1 

                + 

                ( 

                 y 

                 1 

                − 

                 y 

                 2 

                ) 

                 c 

                 2 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   2 

                   2 

                  ) 

                  − 

                  ( 

                   y 

                   2 

                   2 

                  − 

                   y 

                   1 

                   2 

                  ) 

                 2 

                ( 

                 x 

                 1 

                − 

                 x 

                 3 

                ) 

                 c 

                 1 

                + 

                ( 

                 x 

                 1 

                − 

                 y 

                 3 

                ) 

                 c 

                 2 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   3 

                   2 

                  ) 

                  − 

                  ( 

                   y 

                   3 

                   2 

                  − 

                   y 

                   1 

                   2 

                  ) 

                 2 

          \begin{cases} (x_1-x_2)c_1+(y_1-y_2)c_2=\frac{(x_1^2-x_2^2)-(y_2^2-y_1^2)}{2}\\ (x_1-x_3)c_1+(x_1-y_3)c_2=\frac{(x_1^2-x_3^2)-(y_3^2-y_1^2)}{2}\\ \end{cases} 

      { (X1 − x2) c1 + (y1 − y2) c2 = 2 (x12 − x22) − (y22 − y12) (x1 − x3) c1 + (x1 − y3) c2 = 2 (x12 − x32) − (y32 − y12) At this time, x1, y1, x2, y2, x3, y3 are all known numbers, so to ensure a unique solution, the three points cannot be collinear, that is:  

               ∣ 

                    ( 

                     x 

                     1 

                    − 

                     x 

                     2 

                    ) 

                    ( 

                     y 

                     1 

                    − 

                     y 

                     2 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     x 

                     3 

                    ) 

                    ( 

                     x 

                     1 

                    − 

                     y 

                     3 

                    ) 

               ∣ 

               ≠ 

               0 

          \begin{matrix} \begin{vmatrix} (x_1-x_2) & (y_1-y_2)\\ (x_1-x_3) & (x_1-y_3) \\ \end{vmatrix} & \neq 0 \end{matrix} 

      (X1 − x2) (x1 − x3) (y1 − y2) (x1 − y3 ) ∣∣∣∣ = 0 if we assume:  

           { 

                a 

                = 

                 x 

                 1 

                − 

                 x 

                 2 

                b 

                = 

                 y 

                 1 

                − 

                 y 

                 2 

                c 

                = 

                 x 

                 1 

                − 

                 x 

                 3 

                d 

                = 

                 x 

                 1 

                − 

                 y 

                 3 

                e 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   2 

                   2 

                  ) 

                  − 

                  ( 

                   y 

                   2 

                   2 

                  − 

                   y 

                   1 

                   2 

                  ) 

                 2 

                f 

                = 

                  ( 

                   x 

                   1 

                   2 

                  − 

                   x 

                   3 

                   2 

                  ) 

                  − 

                  ( 

                   y 

                   3 

                   2 

                  − 

                   y 

                   1 

                   2 

                  ) 

                 2 

          \begin{cases} a=x_1-x_2\\ b=y_1-y_2\\ c=x_1-x_3\\ d=x_1-y_3\\ e=\frac{(x_1^2-x_2^2)-(y_2^2-y_1^2)}{2}\\ f=\frac{(x_1^2-x_3^2)-(y_3^2-y_1^2)}{2}\\ \end{cases} 

      a=x1 -x2 b=y1 -y2 c=x1 -x3 d=x1 -y3 e=2 (x12 -x22)- (y22 -y12) f=2 (x12 -x32)- (y32 -y12)- (y32 -y12)  - (y32 -y12) - (y32 -y12)- (y32)- (y32)- (y32)- (y3  

           { 

                 c 

                 1 

                = 

                − 

                  d 

                  e 

                  − 

                  b 

                  f 

                  b 

                  c 

                  − 

                  a 

                  d 

                 c 

                 2 

                = 

                − 

                  a 

                  f 

                  − 

                  c 

                  e 

                  b 

                  c 

                  − 

                  a 

                  d 

          \begin{cases} c_1=-\frac{de-bf}{bc-ad}\\ c_2=-\frac{af-ce}{bc-ad}\\ \end{cases} 

      {C1 = − bc − adde − bf c2 = − bc − adaf − ce ok, then solve for the radius of the circle and you're done. 

##  2.2 Code implementation 

>  RANSAC.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574047050
 ```  
>  DrawCircle.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574047050
 ```  
#  III. Achieving results 

![avatar]( 2f4c3001c66d48a9bbacd30932db65fa.png) 

![avatar]( 37e53a6e49014eb3a9d8534244f9eb01.png) 

![avatar]( 142b5528e3004aff81387ceb3b4ffc0e.png) 

#  IV. Summary 

>  RANSAC algorithm is a probabilistic model-based algorithm, its accuracy is closely related to the number of iterations (sampling) and discrimination conditions, we simply use the point to fit the circle curve distance to extract the circle that meets the conditions, of course, you can also add more delicate discrimination conditions according to the needs to fit the model you need, which depends on the follow-up research "~". 

>  Reference: [1] https://blog.csdn.net/dayuhaitang1/article/details/109427412 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

The Matlab version is 2022b. 

>  The rolling ball algorithm (BPA) is a method of surface reconstruction related to alpha shapes. Visually imagine a 3D ball with a given radius, and we throw it on a cloud of points. If it hits any 3 points (and it doesn't cross those 3 points), it creates a triangle. Then, the algorithm starts rotating from the edge of the existing triangle, and every time it hits a point where the 3 balls didn't fall, we create another triangle. The more specific steps are as follows: 

1. Contact the ball with three sampling points that form the initial seed triangle. 2. Keep the ball in contact with these two initial points (the edges of the seed triangle) and rotate the ball until it touches another point. This side and the new point define a new triangle. 3. Rotate the ball using the new triangle edge. That is, using the sides of the new triangle, repeat the rotation and define the new triangle with the contact points in this process. The triangle formed through this process forms the interpolation mesh. 4. Repeat this process until all reachable sides are covered and then start another seed triangle. 5. Finally, repeat the whole process 1-4 with a larger radius to reconstruct the uneven surface. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574072196
 ```  
#  III. Achieving results 

![avatar]( e039e11674784d62aef9cc1cba4a07bc.png) 

 ![avatar]( 1984bea1bd8e4e549b609ca5a0d42d44.png) 

#  reference 

>  [1] Matlab Help Documentation [2] Open3D Surface Reconstruction (Python version) 



--------------------------------------------------------------------------------

#  Overview of the principle 

>  Before using the radius filter in PCL, use MATLAB to implement it. The specific principle is to set a range (a circle with a radius of r) for each point in the input point cloud. If a certain set point value is not reached within this range, the data point will be deleted. Repeat the above process until the last data point to complete the filtering process. 

![avatar]( 7efae70ebc054a19bb436aa77cb8e949.png) 

#  Code implementation 

>  ROR.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957409491
 ```  
>  If a student wants to calculate faster, here is a code for parallel processing: 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957409491
 ```  
#  III. Achieving results 

![avatar]( 68df3ce986e04727b1bb7ef827a08d9b.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  Motion-based recovery architecture (SfM) refers to the process of estimating the three-dimensional structure of a scene from a set of two-dimensional images. SfM algorithms are used in many applications, such as 3D scanning, augmented reality, and visual simultaneous localization and mapping (vSLAM). 

>  SfM can be calculated in many different ways. The way the problem is handled depends on different factors, such as the number and type of cameras used, and whether the images are ordered. If the images were taken with a single calibrated camera, then 3d structure and camera motion can only be restored to scale. Scaling means you can restructure and size the camera motion and still keep the observations. For example, if you hold the camera close to an object or when you zoom in on the object and move the camera away, you are actually seeing the same image. If you want to calculate the actual scale of structure and motion in world units, you will need additional information, such as: 

>  The simplest example is the two-view case: for the simple case of two still cameras or a moving camera structure, one view can be imagined as camera 1 and the other as camera 2. In this case, the algorithm assumes that camera 1 is at the origin and its optical axis is along the z-axis. 

![avatar]( 8248372b926a417999392b015119057c.png) 

>  Then the recovery process in Matlab mainly involves the following steps: 

![avatar]( eaaece4028e64837b574478452fba080.png) 

>  Method functions in Matlab: 

![avatar]( 51fde9cf0a244a678d38de4cef609685.png) 

 ![avatar]( ba567c6ff2194b7383275aa75bc9f6c8.png) 

#  Implementation code 

>  SFM.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574018137
 ```  
#  III. Achieving results 

![avatar]( a39fd7502d2342fd839393cd570b37a0.png) 

 ![avatar]( a25aa8833e3e4d3ea50802d6f9129791.png) 

 ![avatar]( 747967aeec9e44a1a4d7ee4a6c30acf7.png) 

 ![avatar]( 2e4822f5268047f9bc1c73f136ec17dd.png) 

 ![avatar]( 09d182e01c9142c2bd764ed876f1bbf2.png) 

 ![avatar]( 37ebb9a0004349f79ba6d63d8c0e312e.png) 

#  reference 

>  [1]https://ww2.mathworks.cn/help/vision/ug/structure-from-motion.html [2]https://ww2.mathworks.cn/help/vision/ug/structure-from-motion-from-two-views.html 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

The Matlab version is 2022b. 

>  The process is very brief. First, the ISS key points in each point cloud are extracted, and then ICP registration is performed based on these key points. 

#  Implementation code 

>  ISS_ICP.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574035162
 ```  
#  III. Achieving results 

![avatar]( d51454f5f57443069eb143fb368cb3b0.png) 

 ![avatar]( 09b460828fff47709b8c54855821d6f1.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  DEM is a model that describes the undulation of the ground, and it does not include ground features other than the ground, such as vegetation, buildings, and landscapes. Unlike this model, the DSM model is a digital model that includes these things. 

#  Implementation code 

>  DSM.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574058102
 ```  
#  III. Achieving results 

![avatar]( c046fa73b20246fc978cc45d0eaf97db.png) 

 ![avatar]( 9c29bde8d9a849e4b59a849779ec862b.png) 

#  reference 

>  [1] Using point cloud data to create a digital elevation model (DEM) [2] C #+ AE raster surface analysis 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  In general, a rectangle consists of four vertices 

           P 

           0 

          , 

           P 

           1 

          , 

           P 

           2 

          , 

           P 

           3 

         P_0,P_1,P_2,P_3 

     P0, P1, P2, P3, in order to use the formula to represent a rectangle, here we assume 

          P 

          = 

           P 

           0 

         P=P_0 

     P = P0, and defines 

           e 

           0 

          = 

           P 

           1 

          − 

          P 

          、 

           e 

           1 

          = 

           P 

           3 

          − 

          P 

         e_0=P_1-P、e_1 = P_3-P 

     E0 = P1 − P, e1 = P3 − P, then a rectangle can be defined as 

          R 

          ( 

          s 

          , 

          t 

          ) 

          = 

          P 

          + 

          s 

          ∗ 

           e 

           0 

          + 

          t 

          ∗ 

           e 

           1 

         R(s,t) = P+s*e_0+t*e_1 

     R (s,t)=P+se0 +te1 , 

          ( 

          s 

          , 

          t 

          ) 

          ∈ 

          [ 

          0 

          , 

          1 

           ] 

           2 

         (s,t)\in[0,1]^2 

     (S, t) ¾ [0, 1] 2. As shown in the following figure: 

![avatar]( b8f3fca144ac4ffd9db5f08aa4cda5a0.png) 

          given point 

          Q 

          AND rectangle 

          R 

          We request from 

          Q 

          to 

           Q 

           ′ 

          The distance, that is 

          R 

          with 

          Q 

          The nearest point, as shown in the figure 

         Given a point Q and a rectangle R, we require the distance from Q to Q ', which is the closest point between R and Q, as shown in the figure 

     Given a point Q and a rectangle R, we require the distance from Q to Q′, which is the closest point between R and Q, as shown in the figure. 

![avatar]( daa1879a34694251897dc1da4b198cca.png) 

 Then we can easily think that if Q is inside R, then Q 'is the nearest point; however, if Q is outside R, then the nearest point is either the vertex of R or the point on the edge of R. The vectors e0 and e1 are orthogonal, and if expanded outside [0,1], we can see that the plane is divided into 9 regions, as shown below. 

![avatar]( dd8495f33d3a409db33483844fe1fef0.png) 

>  Suppose the projection point of Q falls into area 0, then 

here 

          s 

          = 

          ( 

          Q 

          − 

          P 

          ) 

          ∗ 

           e 

           0 

          , 

          t 

          = 

          ( 

          Q 

          − 

          P 

          ) 

          ∗ 

           e 

           1 

          。 

         s=(Q-P)*e_0,t=(Q-P)*e_1。 

     S = (Q − P) * e0, t = (Q − P) * e1. Based on this, the distance from any point in space to the rectangle can be determined by code. 

#  Implementation code 

>  Point2Rect.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026325
 ```  
>  Point2RectFunc.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026325
 ```  
#  III. Achieving results 

![avatar]( 4e60d3dcd26047b9917b5c10ea0e8dd5.png) 

 ![avatar]( 3e5bd811bc194f449d07030447fe8642.png) 

#  reference 

>  [1]Geometric Tools for Computer Graphics 



--------------------------------------------------------------------------------

# 

C++ version

#  First, the basic configuration 

#  II. Visualization 

#  Point cloud clustering 

#  IV. Point cloud sampling 

#  Point cloud surface reconstruction 

#  Point cloud segmentation 

#  Point cloud filtering 

#  Eight, point cloud characteristics 

#  Nine, point cloud registration 

#  Point cloud preprocessing 

#  Eleven. KD trees and octree 

#  Point cloud projection 

#  Forestry 

#  XIV. Meshlab plug-in development 

#  Data reading and writing 

#  other 

# 

Python version

#  First, the basic configuration 

#  II. Visualization 

#  Point cloud clustering 

#  IV. Point cloud sampling 

#  Point cloud surface reconstruction 

#  Point cloud segmentation 

#  Point cloud filtering 

#  Eight, point cloud characteristics 

#  Nine, point cloud registration 

#  Point cloud preprocessing 

#  Eleven. KD trees and octree 

#  Point cloud projection 

#  Forestry 

#  RGBD depth image 

#  Point cloud rotation 

#  other 

#  data download 



--------------------------------------------------------------------------------


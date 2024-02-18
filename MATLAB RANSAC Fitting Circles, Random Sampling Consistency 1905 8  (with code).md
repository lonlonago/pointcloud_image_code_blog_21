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


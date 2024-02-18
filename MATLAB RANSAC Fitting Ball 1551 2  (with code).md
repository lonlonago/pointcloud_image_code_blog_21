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


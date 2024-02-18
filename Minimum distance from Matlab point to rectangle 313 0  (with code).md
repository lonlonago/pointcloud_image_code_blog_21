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


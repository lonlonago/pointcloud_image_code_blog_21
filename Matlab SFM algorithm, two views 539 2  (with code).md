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


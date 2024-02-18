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


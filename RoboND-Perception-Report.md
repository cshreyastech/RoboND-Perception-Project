## Project: Preception
Goal of this project is to identify the object correctly using perception techniques.

---
[//]: # (Image References)

[ConfusionMatix1]: ./images/ConfusionMatix1.JPG
[ObjectRecognision1]: ./images/ObjectRecognision1.JPG

[ConfusionMatix2]: ./images/ConfusionMatix2.JPG
[ObjectRecognision2]: ./images/ObjectRecognision2.JPG

[ConfusionMatix3]: ./images/ConfusionMatix3.JPG
[ObjectRecognision3]: ./images/ObjectRecognision3.JPG

**Steps to complete the project:**
Breaking up of the exercise was very helpful in solving this exercise. My main challenge was in adjusting the values for the filters. It took me some time understanding the overall flow.
#### Exercise 1
1. Ros information was converted into pcl data
2. Noise was filtered out using mean in Standard Deviation from pcl data
3. Voxex Grid downsalpling was calculated and sent through z and y passthrough filter
4. Coordinates of the table coordinates were calculated and objects and table were segregated using passthrough filter
5. RANSAC plane segment was created to adjust the distance of filter

#### Exercise 2
6. Inlayers and outlayers were found with this and send to Euclidean Clustering
7. Point cloud for each object for found with this information
8. Formed the k-d tree for each cluster and rgb of each segmented object for found

#### Exercise 3

9. PCL was converted to ROS for the new color cloud and published
10. Color Histogram features each cloud element was calculated. This was used to predict and identify the object

#### pcl_callback()
11. Object list was iterated to form a list of centroid values corresponding to x, y and z axis
12. These value were compared with the known values of the objects of interest 
13. Objects under "red" group was assigned to picked up by left arm and "green" group by right arm

#### Settings used for SVM training set
Iterations: 500
Bins (Color & Normals): 64
Converted to HST

#### Output
All objects were recognized correctly in 3 environments

Training Set 1
![alt text][ConfusionMatix1]
![alt text][ObjectRecognision1]
-----------------

Training Set 2
![alt text][ConfusionMatix2]
![alt text][ObjectRecognision2]
-----------------

Training Set 3
![alt text][ConfusionMatix3]
![alt text][ObjectRecognision3]

#### 7. Conclusion
All the objects were identified successfully in all seen. It was a very good leaning on the object recognition, but I still have few grey areas in my understanding.
# This is a dataset for pointcloud grasping.
[HDGCN](https://github.com/baiyuxas/dataset-for-HDGCN)

This is our model for point cloud analysis.

[The download link for the dataset is here](https://github.com/baiyuxas/dataset-for-HDGCN)

The data includes 10 categories of objects from the YCB dataset. A total of 10000 scenes, including 8000 as training set and 2000 as test set.
picture

# Details of Our Own Dataset
We use the model in YCB dataset and complete the generation of our dataset in bullet. We simulate the state of an object falling on the table. The initial position and rotation of an object are random. After falling to the table, we record the 6-Dof pose of the object. Then we take a random point on the surface of the object. According to the normal line of the point, a virtual gripper will be generated. The angle of the gripper relative to the Z axis of the normal line is a random value. Then we close the gripper and release it. If the pose change under the Euclidean distance is greater than the threshold value, it is considered that the grasp fails. For a successful grasp shall wrap lots of points in the middle, when the number of points in the internal space of the gripper is less than a certain number, we also think that the grasp fails. For an object with random pose, several virtual grippers are sampled on its surface, and the point cloud between the grippers will be recorded. The physical center of the point cloud gripper is taken as the coordinate system of internal point cloud. The advantage of this method is that we can keep scale and position of point cloud in the same coordinate system and easier to transport to other scenes. The generation diagram of single data is shown in the following Fig.
![The production process of a single data sample.][1]
[1]:https://github.com/baiyuxas/dataset-for-HDGCN/blob/main/Figure_1.png

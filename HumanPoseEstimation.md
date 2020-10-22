# Human Pose Estimation (HPE)

## Project description

Human pose estimation is defined as the problem of localizing and identifying anatomical key-points of the human body and it is considered a fundamental and challenging task in computer vision. Poses can serve as base features in other vision problems like activity recognition, virtual and augmented reality, human re-identification or in human-computer interaction. This task can be very useful for solving the problem of recognizing human actions using a skeleton-based approach. That is why we chose to develop a module capable of extracting human skeleton coordinates from RGB images. 

![image](https://i.ibb.co/p43TH47/human-pose-estimation.png)

## Research challenges

There are many challenges which need to be taken into account when inferring human pose. First, the number of people in the image is unknown and usually varies. Tackling this gives the option of either iteratively processing each person instance in the image or to attempt to obtain all human poses simultaneously. Moreover, the image may contain people who are in contact (e.g. shaking hands, carrying one another) making it difficult to assign the correct correspondence between person and key-point or body part. Occlusion, be it of actual key-points or not, also affects accuracy quite drastically.

![image](https://i.ibb.co/CtDKdj1/pose-estimation1.png)

## OpenPose

Cao *et al.* [1] have proposed an approach which aims to detect the 2D pose of multiple people in a single image. In their processing pipeline, the system takes an image as input and produces 2D locations of anatomical key-points of each person in the image. In the first stage the network predicts a set of 2D confidence maps of body part locations for each body part. At the same time it also produces a set of 2D vector fields which indicate part affinities. These values actually characterize the degree to which pairs of parts in the image are actually related. Using these confidence maps and the affinity fields they determine the correct part associations based on a greedy inference method which yields the 2D key-points for each person in the image. One of the advantages of their method is that by using part affinity fields they manage to increase the confidence with which different key-points get assigned to the correct corresponding person. Another advantage is that the architecture manages to simultaneously treat all the key-points from all the persons in the image. This allows for real-time performance as opposed to other previous methods which relied on first identifying each person, either by bounding-box or through segmentation, and only then analyzing the pose.

![image](https://i.ibb.co/zV8wYQh/openpose-model.png)

## Objectives

- Analysis of existing approaches for HPE problem;
- Identify a technique that can decide how joints can be grouped;
- Development of a model (starting from the architecture proposed for OpenPose [1]) capable of predicting human posture and training it on the Coco dataset (initially using single-person images);
- Extending the proposed method to be able to predict human posture for multi-person images;
- Testing the proposed method on the COCO dataset and comparing the results with those reported in the literature.

## References

[1] Cao, Z., Hidalgo, G., Simon, T., Wei, S. E., & Sheikh, Y. (2018). **OpenPose: realtime multi-person 2D pose estimation using Part Affinity Fields**. arXiv preprint arXiv:1812.08008.

- Sun, K., Xiao, B., Liu, D., & Wang, J. (2019). **Deep high-resolution representation learning for human pose estimation**. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 5693-5703).
- Pavllo, D., Feichtenhofer, C., Grangier, D., & Auli, M. (2019). **3d human pose estimation in video with temporal convolutions and semi-supervised training**. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (pp. 7753-7762).

# Human action recognition (HAR)

## Project description

The problem of recognizing people's actions is a very complex problem, with a high degree of difficulty that has become one of the most important research topics in the field of Computer Vision. Another aspect that makes the problem important is related to the great practical applicability that this problem has. Recently, more and more large datasets have appeared to facilitate the solution of this problem. An action can be seen as a series of human body movements. Thus, there have been several ways in which these movements, that define a human action, can be recorded: as a video clip (a set of RGB images),  in the form of the evolution of the coordinates of some articulation points that make up the human skeleton, by recording a set of depth maps or other combinations.

## Research challenges
An important thing that needs to be clarified before presenting the difficulties and challenges of the problem, is related to the difference between action and activity. There are no unanimously accepted definitions, but we consider that the differences between these two concepts are those presented in **Figure 1**, extracted from the definitions provided by Aggarwal *et al.* [1]. In addition to the 4 categories proposed by them, we introduced another category: activity. 

![image](https://i.ibb.co/8rd5B07/schema1.png)

**Figure 1**: Characteristics of the main types of human activities

The main challenge that arises for the problem of recognising human actions is related to the development of a module capable of running in real time. Over time, many approaches have been proposed to this problem, but most of the time, they have only been tested on certain benchmarks. It is very difficult to implement a model that is able to generalize and function in any conditions. For example, methods based on RGB images may become dependent on the environment in which the training set samples were collected. Skeleton-based approaches depend very much on the correctness of the skeletons.

This problem depends on many factors, and each of them can be decisive in determining the final result. Some of these factors are actually related to the action to be classified (e.g. duration of the action, speed with which the action is performed, height of the person performing the action, brightness, the quality of the data collected), and others occur when we want to integrate such a module in a system that runs in real time (e.g. detecting the moment when the action starts, detecting the moment when the action ends, checking whether or not an action of interest has happened, the inference time).
## Approaches

### Skeleton-based Human Action Recognition

From a structural point of view, the human body is composed of five parts: two arms, two legs and one trunk. Thus, we can consider human action as being interactions of different parts of the body. Because when a human performs an action the points in each part move together, the combination of their 3D trajectories forms patterns that can differentiate actions from each other.

![image](https://i.ibb.co/NskQhrT/Webp-net-resizeimage-1.png)

#### Objectives

- Analyzing the solutions that obtain the best results
- Establishing the operations that should be applied in the preprocessing stage
- Proposing and testing architectures based on RNNs [3] / TCNs [2] / GCNs [4]


### Human action recognition using RGB data

Video classification is a very important research topic for Computer Vision and the problem of HAR can be seen as a problem of classifying videos when the way of representing data is based on RGB images. The main challenges that arise when we want to develop a solution to the problem of video classification are the following:

- There are both spatial and temporal content to be considered.
- Do we need to process each and every frame to make assumptions about the content of a video?
- The training time for a classifier working with videos will be high because we need a very large volume of data.
- Datasets are more limited, due to the difficulty to collect, annotate and store videos.
- Video classification is not a simple task.


#### Objectives

- Choosing a data set to be used as a benchmark
- Analysis of the main types of models proposed for this problem [5]
- Development, training and testing of models capable of recognizing human actions using RGB images
- Establishing properties for each type of architecture
- Integration with a system containing an RGB camera to achieve real-time recognition of human actions

## Datasets

Over time, many datasets have been proposed for this problem. Some of the most important datasets are presented in the table below.
![image](https://i.ibb.co/9csVNkL/table1.png)


## References
[1]  Jake K Aggarwal and Michael S Ryoo. **Human activity analysis:  A review**. *ACM Computing Surveys (CSUR)*, 43(3):1–43, 2011.

[2] Lea, C., Flynn, M. D., Vidal, R., Reiter, A., and Hager, G. D. (2017). **Temporal convolutional networks for action segmentation and detection**.*In proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*, pages 156–165

[3] Du, Y., Wang, W., and Wang, L. (2015). **Hierarchical recurrent neural network for skeleton based action recognition**. *In Proceedings of the IEEE conference on computer vision and pattern recognition*, pages 1110–1118.

[4] Papadopoulos, K., Ghorbel, E., Aouada, D., and Ottersten, B.(2019). **Vertex feature encoding and hierarchical temporal modeling in a spatial-temporal graph convolutional network for action recognition**. *arXiv preprint* arXiv :1912.09745.

[5] Carreira, J., & Zisserman, A. (2017). **Quo vadis, action recognition? a new model and the kinetics dataset**. *In proceedings of the IEEE Conference on Computer Vision and Pattern Recognition* (pp. 6299-6308).

- Mihai Trascau, Mihai Nan, Adina Magda Florea: **Spatio-Temporal Features in Action Recognition Using 3D Skeletal Joints**. *Sensors 19*(2): 423 (2019)
- Mihai Nan, Alexandra Stefania Ghita, Alexandru-Florin Gavril, Mihai Trascau, Alexandru Sorici, Bogdan Cramariuc, Adina Magda Florea: **Human Action Recognition for Social Robots**. *CSCS 2019*: 675-681

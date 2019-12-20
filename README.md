# Attendance-AI

| System | Python |
| :---: | :---: |
| Linux | 3.5, 3.6, 3.7 |
| macOS | 3.6, 3.7 |
| Windows | 3.5, 3.6, 3.7 |

I set the face classfication model as below

### Face detection(MTCNN) - Face Feature Extraction(Inception ResNet) - Face classifier(KNN)

When image(or video) is putted, "MTCNN" model output detected bounding box and simple face features by image. But, this feature is not enough to classfy face by simple classifier (like KNN)

So, we use "Inception ResNet" for extracting more high-level features. After that, we use "knn" for classfy using output of Inception ResNet.

The reason why we used simple classfier (like knn) is that when we check attendace, a little of face data is enough for training. If students should take a picture their face data too many times for training, they would hate this attendace tool. 

when we used Attendance AI for check attendance, we just used 5 pictures of each person for training

* For privacy, we did not upload our student's pictures. Instead, we uploaded 5 pictures of each member of BTS for training.

* I used Inception Resnet (V1) models implemented by 'timsler' (it is pretrained on VGGFace2 and CASIA-Webface) He also implemented MTCNN for face detection prior to inference

# Attendance AI.ipynb

jupyter notebook code for automatically check the attendance

## Quick start

1. Either install using pip:
    ```bash
    pip install facenet-pytorch
    ```
    or clone this repo, removing the '-' to allow python imports:
    ```bash
    git clone https://github.com/timesler/facenet-pytorch.git facenet_pytorch
    ```
    or use a docker container (see [timesler/jupyter-dl-gpu](https://github.com/timesler/docker-jupyter-dl-gpu)):
    ```bash
    docker run -it --rm timesler/jupyter-dl-gpu pip install facenet-pytorch && ipython

1. Excute "Attendance.ipynb" file


## Reference

1. Tim Esler's facenet repo: 1. David Sandberg's facenet repo: [https://github.com/timesler/facenet-pytorch](https://github.com/timesler/facenet-pytorch)

1. F. Schroff, D. Kalenichenko, J. Philbin. _FaceNet: A Unified Embedding for Face Recognition and Clustering_, arXiv:1503.03832, 2015. [PDF](https://arxiv.org/pdf/1503.03832)

1. Q. Cao, L. Shen, W. Xie, O. M. Parkhi, A. Zisserman. _VGGFace2: A dataset for recognising face across pose and age_, International Conference on Automatic Face and Gesture Recognition, 2018. [PDF](http://www.robots.ox.ac.uk/~vgg/publications/2018/Cao18/cao18.pdf)

1. D. Yi, Z. Lei, S. Liao and S. Z. Li. _CASIAWebface: Learning Face Representation from Scratch_, arXiv:1411.7923, 2014. [PDF](https://arxiv.org/pdf/1411.7923)

1. K. Zhang, Z. Zhang, Z. Li and Y. Qiao. _Joint Face Detection and Alignment Using Multitask Cascaded Convolutional Networks_, IEEE Signal Processing Letters, 2016. [PDF](https://kpzhang93.github.io/MTCNN_face_detection_alignment/paper/spl.pdf)

# Selected Topics in Visual Recognition using Deep Learning, Spring 2025: Homework 3
Course instructor: 林彥宇<br>
<br>
StudentID: 313540002<br>
Name: Leontieva Mariia, 馬莉亞<br>

### Introduction

In this assignment, we aim to solve digit recognition problem using a Faster R-CNN network, using the [dataset](https://drive.google.com/file/d/1B0qWNzQZQmfQP7x7o4FDdgb9GvPDoFzI/view) that contains 209 images for Training and Validation and 101 images for Test.<br>
<br>
For each training sample, we are given a folder with image.tif and a .tif file for each cell class present in the image; each .tif file contains a mask filled with 0 for background, and integer numbers corresponding to the object index. Below is an example of a training sample: the file on the left is image.tif and the file on the right is class4.tif, meaning all “class 4” cell instances are contained in this mask.<br>
<br>
![sample_GT](https://github.com/user-attachments/assets/d3ca9059-f614-4e49-a32c-1a1bfa5137e6)
<br>
To solve this problem, I chose a Mask R-CNN model with a Resnet-50 backbone and pre-trained weights. The total number of parameters in this model is 43938541 (<200M as required for this assignment).<br>
<br>
I also used data augmentation, increasing the provided dataset 3 times, by using vertical flip and horizontal flip.<br>
<br>
![imrotation](https://github.com/user-attachments/assets/4afbdbd0-f69f-435f-9cc9-f781fef1784e)
<br>

## Results
The best results were yielded by using SGD with LR=1e-5. Training and validation curves of this model over 45 epochs can be seen below.<br>
<br>
![image](https://github.com/user-attachments/assets/c380dc0f-057e-4324-abf0-5dc3da944d0d)
<br>

## Performance
Performance was evaluated using [CodaBench competition](https://www.codabench.org/competitions/7325/?secret_key=68db3785-cb67-4dc0-b1d9-629b9d06e852).<br>
According to the results of experiments, the best mask_threshold for prediction during the test stage is 0.5.

![image](https://github.com/user-attachments/assets/c84e04c7-a13c-4bf5-93e8-2a776bf6d392)

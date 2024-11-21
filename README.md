# Object-Detection using faster r-cnn
Team Information

-**[Devansh Patel]** - [Team Leader]

-**[Vishesh Shahu]** - [Team member]

-**[Akshay Gupta]** - [Team member]

-**[Sumit Patil]** - [Team member]

-**[Pradeep Sahu]** - [Team member]

Mentor

-**[Anirvinya Gururajan]** - [Mentor's Role/Title]

# Project Overview
[This project aims to perform object detection using the faster rcnn model.]
Introduction:
Object detection: Given an image, recognize and locate objects in it. Application areas range from self-driving cars to monitoring security cameras and robotics. Faster R-CNN is the newest state-of-the-art model from the variants that improve on the previous R-CNN approach by introducing the region proposal process inside the network to increase the speed and accuracy of detection. A two-stage framework contributed by the RPN and a Fast R-CNN classifier makes Faster R-CNN an efficient tool for object detection across the scales and contexts. Most of the analysis contained in this report depends on a very challenging benchmark: the MNIST dataset, more than 200,000 images and 80 object categories that match real-world complexities like occlusion and cluttered backgrounds. In this study, testing would identify the computational problems that are present for Faster R-CNN as well as the possible optimizations available.

Objective:
The primary objective of this project is to:
1.	Adapt the MNIST dataset for object detection tasks by combining multiple images.
2.	Implement and train Faster R-CNN to detect individual digits within each combined image.
3.	Evaluate the model using metrics such as accuracy, precision and recall analysis to understand its detection capability on this dataset.

Methodology:
Dataset Preparation
Several digit images are arranged in rows into a single, bigger image to adapt the MNIST dataset for object detection:
1.	Data loading and transformation: Pictures are scaled to 256x256 pixels and transformed to three-channel grayscale.
2.	Image Stacking and Bounding Boxes: Four randomly selected MNIST digits are used in each row of photographs to create a composite image, with bounding boxes established around each digit.
Custom Dataset Class
The combined photos and their matching bounding boxes are handled by an unique PyTorch Dataset class called MNIST data. During training, this class allows Faster R-CNN to process images and return target labels with bounding boxes as well as input tensors.
Model Selection and Training
1.	Faster R-CNN with ResNet-50 Backbone: We employ a ResNet-50 feature extractor when combined with the pretrained Faster R-CNN model. The model learns generic features faster thanks to the previously trained weights.
2.	Optimization: Stochastic Gradient Descent (SGD) is used to train the model, using a learning rate of 0.0001, momentum of 0.9, and weight decay of 0.0005.
3.	Training Loop: The training loop includes a forward pass, loss calculation, and backward pass to optimize the model. Losses are tracked for each epoch, and precision, recall, and accuracy are calculated to evaluate performance.
Metrics for Evaluation
To understand the model’s effectiveness on this dataset, several metrics are tracked:
1.	Precision: Measures the accuracy of the model’s positive predictions.
2.	Recall: Measures the coverage of actual positives.
3.	Accuracy: Tracks overall prediction correctness.
Model Testing and Visualization
For testing, predictions are visualized with both ground truth and detected bounding boxes. This qualitative analysis showcases Faster R-CNN’s performance in terms of accurately predicting digit locations within the combined images.

Results:
The model’s performance is evaluated using metrics tracked across all epochs:
1.	Loss Curve: The loss curve provides insight into model convergence. Lower loss across epochs indicates the model's improving accuracy.
2.	Precision, Recall, and Accuracy: High precision and recall values suggest effective digit localization, while accuracy confirms correct predictions.

Conclusion:
The Faster R-CNN model shows high efficiency when applied to object detection on MNIST with felicitous finding a very good balance between accuracy and efficiency together with its integrated methodology regarding the region proposals and classification. The prizes notwithstanding achieved, presumably even for medium-sized objects as well as large objects, but ideally improved detection of small objects and further inference speed would make it more adapted for real-time applications. Future work will try to combine this Faster R-CNN architecture with feature enhancement techniques or other architectures for an even better performance with small objects and as an efficient processing.

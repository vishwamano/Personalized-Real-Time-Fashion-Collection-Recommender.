# Personalized-Real-Time-Fashion-Collection-Recommender.
Building a Personalized Real-Time Fashion Collection Recommender

1.Convert images to embeddings
2.Conduct Transfer Learning from ResNet
3.Use Fastai hooks to retrieve image embeddings from step 2
4.Use Approximate Nearest Neighbors and embeddings centroid detection to obtain most similar images based on the embeddings from step 3.

We will be using a subset of DeepFashion data open-sourced by Liu Z. et al., The Chinese University of Hong Kong. Our data consists of 280K fashion images across 46 categories. You can download the data from their [website](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html).


[Model] Theory: How Does Transfer Learning Works?
For most real-world deployment, we do not train a CNN from scratch. Organizations like Microsoft Research has released state-of-the-art, large scale, pre-trained deep CNN (DCNN) models over the years, and we should leverage on their work by training on top of their baseline models. This is known as transfer learning.
Concretely, we take a large pre-trained DCNN like [ResNet50](https://arxiv.org/abs/1512.03385) (He K., et al.), freezes most of the layers, and train on the last few layers. The intuition is that for most of the DCNN, the knowledge gained by the filters is transferable components such as detection of edges, patterns, gradients, colors, etc. Thus, we fine-tune the last few layers to our problem, and we can have a working solution. You can explore the concept of transfer learning under further readings section.




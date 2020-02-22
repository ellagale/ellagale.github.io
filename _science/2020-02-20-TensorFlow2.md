---
title: "Upgrading to TensorFlow 2"
excerpt: ""
---

So, TensorFlow2 came out recently, and in the post-xmas hangover when most people were giving up meat and alcohol, I decided to instead upgrade my neural networks from keras calling TensorFlow to TensorFlow2 (which now contains keras in it). This wasn't just the search for the newest new thing, for my ClusterFlow algorithm (more later) I needed lots of pre-training models to play with and lots of different types of data to try out. TensorFlow2 has something called tensorflow hub with a nice set of pre-trained models which you can easily download and use, most usefully, using the exact same code to call different models. For example, the model classes all expose a function called 'decode' to quickly an easily decode the output 'probabilities' into a list of the 5 most likely categories, with human readabe labels and probabilities. So far, so good...

Then, there is something called tensorflow_datasets which is a nice repository of datasets that people test their neural networks on, and usefully it includes the tf_flowers dataset and so on. If it works, the dataset is just downloaded to a ~/tensorflow_datasets/ directory for TensorFlow2 to use.  

First problem: tensorflow_datasets is not part of TensorFlow2, and nowhere in any of the tutorials that I found (although, admittedly, the tutorials and documentation is being updated currently) did I find a reference to the fact that you have to download and install it separately. 

Second problem: ImageNet2012 is not an auto-downloading dataset, so you have to log on and download it yourself, not a huge problem. But, where do you put it? Some documentation suggests ~/tensorflow_datasets/manual/IM2012 or similar, or ~/tensorflow_datasets/manual/IM2012v5/ or something (I am writing this away from the machine where I solved this problem) and a lot of mucking around is necessary to figure out where the dataset should be placed and there is absolutely no official documentation on this. You would think that, as ImageNet is such an important database, there would be a tutorial walkthrough on this. 

Beyond that, switching from keras to tf.keras was quite easy, but the muck around with tensorflow_datasets did make it hard for me to say that the switch to TF2 is a good idea at the moment. 

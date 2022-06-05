I implemented a deep convolutional neural network in tf.Keras in order to classify cell images based on the presence of malaria. Malaria-infected cells have visible discoloration in the form of darker colored blobs that are present in the cell body. This project is a follow-up to a UCSD course final I was unsatisfied with. My mistake was using K-means, an unsupervised clustering method, as well as performing singular value decomposition and PCA with Numpy operations. K-means is an inappopriate model for this use case because each observation in the data set is very highly dimensional and has three color channels. The dataset containing images is of shape (27,568 x (32 x 32 x 3)) after downsizing, which is quite computationally expensive to work with. 

However, supervised learning methods are much more effective at classifying these particular images. The discolored blobs that distinguish malaria infected cells are located randomly throughout the cell body. Thus, unsupervised methods tend to focus on the variance caused by other features, such as the image border or background. By using a CNN, I will be able to extract the relevant features by looking at convolutional windows throughout the image. This way, the algorithm will associate the discolored malaria blotches with the training label regardless of their position on the cell body.  

The dataset used can be found here: https://www.tensorflow.org/datasets/catalog/malaria.

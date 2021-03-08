# Image Clustering using Autoencoders

The project attempts to perform image clustering on CIFAR-10 dataset. CIFAR-10 dataset contains 60000 images (50000 train and 10000 test) classified into 10 categories - airplane ,automobile ,bird ,cat ,deer ,dog ,frog ,horse, ship or truck.

Image clustering is attempted by using latent space representations of the images from the autoencoder. 3 kinds of autoencoders have been implemented :

1. Convolutional Autoencoder(Conv-AE) - The typical autoencoder with distinct encoder and decoder blocks with a dense "bottleneck" in the between.

![](https://blog.keras.io/img/ae/autoencoder_schema.jpg)
  
2. U-Net - The architecture is similar to that of Convolutional Autoencoder with the addition of skip connections between the encoder and decoder layers.

![](https://www.dimartinot.com/img/notebooks/moon_test/models/unet.png)

3. Variational Autoencoder - This model attempts to create latent space distributions rather than a single point value. It provides a probabilistic approach for describing an observation in latent space.Instead of directly mapping the input data points into latent variables the input data points get mapped to a multivariate normal distribution. This is done by introducing Kullback–Leibler divergence in the loss function.The model has 2 layers containing mean and variance of the distributions.Following those two layers,random sampling is performed.

![](https://www.jeremyjordan.me/content/images/2018/03/Screen-Shot-2018-03-18-at-12.24.19-AM.png)

In order to incorporate randomness with backpropagation, a "reparameterization trick" is done. This allows us to learn mean and variance of the distributions while performing random sampling.

![](https://i.stack.imgur.com/d38DB.png)

For clustering, K-means has been implemented.The results of K-means is not really satisfactory. The images are more or less evenly distributed with no real majority in the cluster(>50% of the cluster size).There are a few classes that have not been represented.Perhaps a more robust clustering algorithm for images might be needed.There is a major scope for improvement.


NOTE: If you are unable to open the notebooks on GitHub, use [nbviewer](https://nbviewer.jupyter.org/) to view them. Copy paste the link of the notebook in the field provided by the website. 

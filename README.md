# Generative-Models
GANs and generative Autoencoders implemented in PyTorch

Repository with generative models implemented in PyTorch.
It's an ongoing project, check back for more models in the near future.
So far there are:
- Wasserstein Adversarial Autoencoder with Residual Blocks
- Deep Convolutional GAN

Run main.py to start the training. 

All parameters are to be found in config.py. You need to specify a foler path to your dataset.
A functionality of loading a few benchmark datasets will be added soon.

Wasserstein Adversarial Autoencoder implementation details:
1. input data scaled [-1, 1] with tanh used instead of sigmoid
2. learning rate scheduler
3. adversarial training stabilisation:
  - noise added to discriminator inputs
  - real label lower than 1 and fake label greater than 0
  - weights initialization
4. Wasserstein improvements
  - Wasserstein loss
  - using labels of 1 for real and -1 for fake
  - weights clipping on the critic (discriminator)
  - no sigmoid activation in the final layer of the critic (discriminator)
  - train the critic multiple times for each update of the generator

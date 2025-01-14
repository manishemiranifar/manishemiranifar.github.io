---
published: true
---
I've heard about a kind of Neural network that can generate data from a specific dataset. I've been curious that how they are work?, so I've read about them and saw they have interesting architecture.

A generative Adversarial Network(GAN) is a Neural network model that generates sample-like dataset features from random input(noise vector).

GANs have two base part:

1 - Generator network

2 - Discriminator network

|![_config.yml]({{ site.baseurl }}/images/GANs/GAN figure.png)|
|:--:| 
| Figure 1 : GAN Architecture |


Note that: Generator and Discriminator are based on Neural networks

Training task is based on [Backpropagation algorithm](https://en.wikipedia.org/wiki/Backpropagation) and the loss from the Discriminator network(cost function)

The Generator network wants to generate data that the Discriminator network can not realize that it's fake data(Maximize Discriminator's loss), the Discriminator network wants to increase its accuracy(minimize its loss) and identifies  real data from fake data

# Implementation
For implementation, you can also see my [github page](https://github.com/manishemirani/Simple_GAN)

## Output of code

|![_config.yml]({{ site.baseurl }}/images/GANs/step1000.JPG)|
|:--:| 
| Figure 2 : Iteration 1,000 |
| 1000 D loss: 0.042404 , acc: 100.00, G loss: 4.099966 |





|![_config.yml]({{ site.baseurl }}/images/GANs/step3000.JPG)|
|:--:| 
| Figure 3 : Iteration 3,000 |
| 3000 D loss: 0.126480 , acc: 94.92, Gloss: 5.473635 |





|![_config.yml]({{ site.baseurl }}/images/GANs/step10000.JPG)|
|:--:| 
| Figure 4 : Iteration 10,000 |
| 10000 D loss: 0.335380 , acc: 85.94, G loss: 3.404595 |

As we expected, the loss from the discriminator is increasing with every iteration.

The best performance is when the data generated by the generator has no different from real data and the discriminator couldn't identify fake data from real data, or at best  it can identify fake data from real data with an accuracy of 50%

We can also improve our GAN network with [DCGANs](https://manishemirani.github.io/Deep-Convolutional-GANs/)(Deep Convolutional Generative Adversarial Network), which is using Convolution layers in the generator and discriminator for training.

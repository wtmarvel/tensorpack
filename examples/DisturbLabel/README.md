
## DisturbLabel

I ran into the paper [DisturbLabel: Regularizing CNN on the Loss Layer](https://arxiv.org/abs/1605.00055) on CVPR16,
which basically said that noisy data gives you better performance.
As many, I didn't believe the method and the results at first.

This is a simple mnist training script with DisturbLabel. It uses the architecture in the paper and
hyperparameters in my original [mnist example](examples/mnist-convnet.py). The results surprised me:

![mnist](mnist.png)

Experiements are repeated 15 times for p=0, 10 times for p=0.02 & 0.05, and 5 times for other values
of p. All experiements run for 100 epochs, with lr decay, which are enough for them to converge.

I suppose the disturb method works as a random noise to prevent SGD from getting stuck.
It doesn't work for harder problems such as SVHN (details to follow). And I don't believe
it will work for ImageNet.
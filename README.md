## Custom-Batch-Size-Policy-for-Deep-Learning-Models

A MiniGoogLeNet model has been trained for 50 epochs with increasing batch size from 32 in a factor of 2 at each step in an epoch. The model has been trained using CIFAR10 dataset[1].

# Approach

To train an epoch, a total of 17 steps were taken with each step having batch size of: 32,32,32,64,64,128,256,512,512,1024,2048,2048,4096,8192,8192,16384,16384

This has been done because there are a total of 60000 images in CIFAR10. If we add all the batch sizes in an epoch, we get 60000. 

Another major problem that faced is processing of large batches. Often, training large batches requires high memory capacity. To overcome this, Gradient Accumulation is performed. The gradients are collected and added together in a number of forward passes. Finally, updating the gradients is being done by dividing the added gradients with the number of forward passes taken to collet and add the gradients.

# Observations

The main observations were: better generalization performance compared to a fixed batch size approach, and this method achieves a training accuracy of 87.89% in 50 epochs.

# References

[1] Krizhevsky, A., Nair, V., & Hinton, G. (2010). Cifar-10 (canadian institute for advanced research). URL http://www. cs. toronto. edu/kriz/cifar. html, 5(4), 1.

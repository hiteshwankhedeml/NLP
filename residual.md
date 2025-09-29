# Residual

* Also called as skip connection
* Used in NN
* The Add and Norm will be having more info as we are passing input directly to it

1. **Addressing the vanishing gradient problem:**

* As the number of layers increase, the gradients can be very small
* Residual connections create a short paths for gradients to flow directly through the network, gradient remains sufficiently large

2. **It improves gradient flow**

* Convergence will be faster

3. **Enables training of Deeper Network**

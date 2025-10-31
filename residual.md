# 🟢 Residual

* <mark style="color:purple;background-color:purple;">**Also called as skip connection**</mark>
* Used in NN
* The Add and Norm will be having more info as we are passing input directly to it

1. **Addressing the vanishing gradient problem:**

* As the number of layers increase, the gradients can be very small
* <mark style="color:purple;background-color:purple;">**Residual connections create a short paths for gradients to flow directly through the network, gradient remains sufficiently large**</mark>

2. **It improves gradient flow**

* Convergence will be faster

3. **Enables training of Deeper Network**

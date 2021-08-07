# uar_new_results

# MNIST inpainting:
* We report here some examples of inpainting MNIST digits, where the measurement has a square 8x8 block of missing pixels in the middle and is additionally corrupted by Gaussian noise with variance equal to 0.2. The UAR does a reasonable job of reconstructing the underlying true digits. The UAR generator and regularizer aretrained on the 60000 training images and then employed on the remaining 10000 test images for inpainting. The training batch-size is 128 and the models are trained for 25 epochs. The regularization penalty is taken to be 0.2 for this experiment. The generator is an unrolled proximal gradient network with 20 layers, which also goes on to show that theUAR scheme is independent of the particular choice of the optimization algorithm that one unrolls toconstruct the generator. The refinement was computed by running 50 iterations of the variational problemstarting from the end-to-end reconstruction as the initial estimate. We noted that the refinement led to onlyminor improvements in the MSE. The average PSNR (dB) and SSIM scores over the test images are asfollows: (i) measurement: 12.21 dB, 0.59; (ii) UAR (end-to-end): 22.11 dB, SSIM 0.95; and (iii) UAR (refined): 22.16 dB, 0.95.

![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex0_ver1.png)  <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex13_ver1.png) <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex15_ver1.png) <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex20_ver1.png) 

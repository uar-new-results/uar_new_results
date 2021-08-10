# uar_new_results

# MNIST inpainting:
* We report here some examples of inpainting MNIST digits, where the measurement has a square 8x8 block of missing pixels in the middle and is additionally corrupted by Gaussian noise with variance equal to 0.2. The UAR does a reasonable job of reconstructing the underlying true digits. The UAR generator and regularizer are trained on the 60000 training images and then employed on the remaining 10000 test images for inpainting. The training batch-size is 128 and the models are trained for 25 epochs. The regularization penalty is taken to be 0.2 for this experiment. The generator is an unrolled proximal gradient network with 20 layers, which also goes on to show that the UAR scheme is independent of the particular choice of the optimization algorithm that one unrolls to construct the generator. The refinement was computed by running 50 iterations of the variational problem starting from the end-to-end reconstruction as the initial estimate. We noted that the refinement led to only minor improvements in the MSE. The average PSNR (dB) and SSIM scores over the test images are as follows: (i) measurement: 12.21 dB, 0.59; (ii) UAR (end-to-end): 22.11 dB, SSIM 0.95; and (iii) UAR (refined): 22.16 dB, 0.95.

![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex10_ver1.png)  <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex13_ver1.png) <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex15_ver1.png) <br />
![Alt text](/MNIST_inpainting/uar_inpaint_mnist_ex20_ver1.png) 

# Denoising on STL-10:
* For this experiment as well, we noted that the refinement gave little to no further improvement on the initial end-to-end reconstruction. The average PSNR (dB) and SSIM over the 8000 test images are as follows: (i) noisy measurement: 19.99 dB, 0.91; (ii) UAR (end-to-end and refined) 25.23 dB, 0.97.

![Alt text](/STL10_images/uar_denoise_stl10_ex1_ver1.png)  <br />
![Alt text](/STL10_images/uar_denoise_stl10_ex2_ver1.png)  <br />
![Alt text](/STL10_images/uar_denoise_stl10_ex4_ver1.png)  <br />
![Alt text](/STL10_images/uar_denoise_stl10_ex6_ver1.png)  <br />
![Alt text](/STL10_images/uar_denoise_stl10_ex10_ver1.png)  <br />
![Alt text](/STL10_images/uar_denoise_stl10_ex12_ver1.png) 

# Remarks:
* These experiments demonstrate that the proposed framework is applicable to inverse problems in general and is not restricted to CT reconstruction. Nevertheless, the training and network hyper-parameters are to be carefully engineered to extract the state-of-the-art performance from UAR for a specific inverse problem of interest. In both of these experiments, we chose to unroll the proximal gradient-descent algorithm (instead of PDHG that was chosen for the CT experiments), which go on to show that the UAR framework is not specific to the choice of the algorithm that one unfolds to construct the generator. 

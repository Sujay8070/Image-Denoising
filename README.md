# Image-Denoising
https://ieeexplore.ieee.org/document/9392554

Research project with a proof of concept for Image Restoration of motion-blurred images in Real-time using data augmentation and specific architecture of Deep Autoencoder network with CNN layers. 
(Studied effects of regularization &amp; Hyperparams optimization)

IDE/ Frameworks/ Libraries used: [Google Colab, TensorFlow, Keras, Scikit-learn, and OpenCV among others.


Industrial operations today are being smoothed by monitoring the entire process using latest Image Processing (IP) techniques, especially the bottlenecks in the process. The challenges that need to be addressed in order to commercialize and optimize these solutions are equally growing, particularly in image monitoring of the machining and assembly lines in production plants as well as mechanical workshops. One such hindrance in monitoring the jobs on a Lathe machine or a Computer Numerical Control (CNC) machine is the motion blur noise introduced in the images due to the real-time on field vibrations within the setup. In this paper, this problem is addressed with Image denoising in real time frames. Many practical solutions have been addressing the problem of Image denoising or Image reconstruction using different Computer Vision (CV) techniques in the last two decades. Herein, we propose Image restoration of such blurred image using a specific architecture of Deep Autoencoder network with Convolutional Neural layers so as to obtain a fully constructed image without any prior knowledge of the corresponding clean image. For this we have used an averagely deep encoder-decoder neural network to minimize the typical motion blurring noise that gets introduced in the input image captured by the camera setup on the production lines. This particular technique eliminates the need to identify the type of noise, its intensity or any other statistical characteristics. The results evidently show that the reconstructed images are visually convincing, with large improvements retaining the blur image details




Model- Architecture:

![image](https://user-images.githubusercontent.com/65066352/119274280-65009380-bc0f-11eb-9aa0-b392fa54e873.png)






Data augmentation:

![image](https://user-images.githubusercontent.com/65066352/119274133-c411d880-bc0e-11eb-8c03-751f7930e89b.png)







Training data sample:


![image](https://user-images.githubusercontent.com/65066352/119274234-2c60ba00-bc0f-11eb-85e2-fd171ed34718.png)







Test samples:

![denoised_8](https://user-images.githubusercontent.com/65066352/124307618-6014f500-db68-11eb-9b2b-3da4dfcb25d7.PNG)


![denoised_7](https://user-images.githubusercontent.com/65066352/124307568-4bd0f800-db68-11eb-95e0-5d53adca2f11.PNG)


The results evidently show that the denoised images using model-predicted pixel values with MSE loss minimization, are visually convincing, with large improvements locating the lost or blur image details. Thus, the vagueness of original real-time blurred image is not eliminated entirely, but is surely reduced in order to obtain few more image specifics. While this model has been proposed through numerous trial and error processes, there should be an improved way of tuning the model structure and hyper parameters so as to obtain a higher Signal to Noise Ratio(SNR) for future images. Deriving a method to design suitable model complexity for each problem is needed. The future scope of this article extends towards achieving greater accuracy with research focused on minimum loss of image details while abstraction in convoluting the image arrays and retaining these details during deconvolutional layers, towards the other half of the model.






Loss curves:


![image](https://user-images.githubusercontent.com/65066352/119274341-b01aa680-bc0f-11eb-9b95-d631d027970d.png)


With possible applications in automotive domain, where indefinite motion blur and vibration noise is encountered, this particular model can find its use on platforms with lesser memory and reasonable GPU specifications (like smartphones and ???GoPro??? action-cameras), unlike most deep neural networks which require very high-performance GPUs to train on. Furthermore, with optimization of prediction code functionality the image restoration in real time can be accelerated. Probably up to even >10 denoised frames per second, in a real time setup.

While the practical maneuvers can be advanced using better hardware as well as software versions (using well accepted pre-defined packages for data augmentation), the theoretical approach can also be modified and optimized with the use of DCT for the input image data set in our model. Most of the signal information is concentrated in a few low-frequency components of the DCT which aids in reducing the spatial and spectral redundancy between the neighboring pixels. Also, the high frequency component in a DCT transform of our sample input image (motion blurred due to vibration), will be the pixel values that are spontaneously changed due to the noise. The main challenge in introducing this step would be that of retaining the original pixels while performing the Inverse-Discrete Cosine Transform (IDCT), in the second half of our model. This being the major area of work for thefurther improvement of this article, it would prove to bereducing computing cost as well as training time for this very model bolstering the entire model to be more suitable for fieldapplication in real-time.

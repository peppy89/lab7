# lab7
**1. Setup: Load an image and add Gaussian noise**

  - Loads the built-in image cameraman.tif.
  
  - Converts it to grayscale double format (im2double).
  
  - Adds Gaussian noise with standard deviation noiseSigma = 0.04 using imnoise.
  
  - Shows the original and noisy images side by side in a figure.
    
    ![Screenshot_1](https://github.com/user-attachments/assets/84cf53d8-d60f-4cfd-b897-3b377284e47d)


**2. Traditional Filter (Adaptive Wiener Filter)**

  - Uses wiener2 (adaptive Wiener filter) with a 5×5 window.
  
  - You give it the noise variance (noiseSigma^2) so it can better adapt.
  
  - It smooths flat regions while trying to keep edges.
  
  - The filtered result is shown in the 3rd subplot.

    ![Screenshot_2](https://github.com/user-attachments/assets/8057f902-cae0-4edf-89ee-abf3bfcf698f)


**3. AI Filter (Pre-trained DnCNN)**

  - Loads a pre-trained deep learning denoising network: denoisingNetwork('DnCNN').
  
  - Uses denoiseImage to remove noise from noisyImage using this CNN.
  
  - The AI-filtered result is shown in the 4th subplot.

    ![Screenshot_3](https://github.com/user-attachments/assets/916d7f59-12ee-46a3-85db-cc7f6448b0a0)


**4. Quantitative Evaluation (PSNR and SSIM)**

  - Computes PSNR and SSIM between:
  
    * Original vs noisy,
    
    * Original vs Wiener-filtered,
    
    * Original vs AI-filtered.
  
  - Prints all metrics to the command window so you can numerically compare quality.
  
    * Higher PSNR and SSIM → better reconstruction.
   
    ![Screenshot_4](https://github.com/user-attachments/assets/c2075a81-f21f-444e-9cb7-1d1e5995593e)


**5. Visual Observation (Comment)**

  - Explains the expected outcome:
  
    * Wiener filter = decent smoothing, some detail loss.
  
    * DnCNN AI filter = usually higher PSNR/SSIM and better preserved textures and edges compared to the traditional method.

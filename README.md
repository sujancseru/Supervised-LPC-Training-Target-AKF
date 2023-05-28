# On supervised LPC estimation training targets for augmented Kalman filter-based speech enhancement

Supervised LPC Training Target is Deep Learning Framework to find the best LPC training target as well as Deep Learning Method in [[3]](https://www.sciencedirect.com/science/article/abs/pii/S0167639322000875) 
to optimize LPC Estimates of Augmented Kalman Filter for Speech Enhancement in Real-Life Condition. It is an extended work of previous [DeepLPC](https://ieeexplore.ieee.org/document/9411829) 
and [DeepLPC-MHANet](https://ieeexplore.ieee.org/document/9422809). 

# Introduction:
The accuracy of LPC estimates depend on the choice of LPC training target. In this work, we simulate the following four supervised training targets for deep learning model for accurate LPC estimation:
1. Line Spectrum Frequency (LSF)
2. LPC Power Spectra
3. Magnitude Spectrum
4. Log Power Spectrum  

Although [DeepLPC](https://ieeexplore.ieee.org/document/9411829) and [DeepLPC-MHANet](https://ieeexplore.ieee.org/document/9422809) addresses accurate LPC estimates in noisy conditions, however, there requires a comprehensive study on supervised LPC training target for investigating state-of-the-art deep learning models for more accurate LPC parameter estimates in noisy conditions. The supervised LPC estimation framework for Augmented Kalman Filter-based Speech Enhancement is shown in Fig. 1.

# Key Contributions: 

1. Develop a supervised LPC estimation framework for LPC estimation. 
2. Including four training targets, we also consider deep learning models:
    a. ResNet-TCN 
    b. Multi-Head Self Attention Network (MHANet)
  
4. The framework learns a mapping from the noisy speech LPC power spectra to the clean speech and noise LPC power spectra from where the corresponding LPC parameters are computed. 
5. By producing less biased clean speech and noise LPC estimates, it enables the AKF to produce enhanced speech at a higher quality and intelligibility in real-life noise conditions [3](https://www.sciencedirect.com/science/article/abs/pii/S0167639322000875).

![image](https://github.com/sujancseru/Supervised-LPC-Training-Target-AKF/assets/130210435/52b59c65-3366-48f0-a244-9b84b8f47384)

# Implementation: 
1. ResNet-TCN as used in [DeepLPC](https://ieeexplore.ieee.org/document/9411829) 
2. MHANet as used in [DeepLPC-MHANet](https://ieeexplore.ieee.org/document/9422809).
3. To facilated the convergency of the gradient optimization algorith, it is necessary to generate normalized training target. It was shwon in [[1]](https://ieeexplore.ieee.org/document/9411829) that the log LPC power spectra of clean speech and noise signal can be fitten with Gaussian Distribution. Therefore, the Gaussian CDF has been used to normalize the log LPC power spectra as shown in Fig. 2-3.

![image](https://github.com/sujancseru/Supervised-LPC-Training-Target-AKF/assets/130210435/afddcffb-d8cb-4bb1-8141-2ab0ea08b48d)
![image](https://github.com/sujancseru/Supervised-LPC-Training-Target-AKF/assets/130210435/3622cbe7-8cfb-4bad-acd8-8308a21a7ad0)

**Training Set 1: 2500 randomly selected clean speech recordings were mixed with 2500 randomly selected noise recordings from the training set (Section 4.2) with
SNR levels: −10 dB to +20 dB in 1 dB increments, giving 2500 noisy speech signals. For each frequency bin, 𝑚, the sample mean and variances, (𝜇𝑠, 𝜎𝑠2)
and (𝜇𝑣, 𝜎𝑣2) were computed from 2500 concatenated clean speech and scaled noise recordings, respectively.

[1] [S. K. Roy, A. Nicolson, and K. K. Paliwal, "DeepLPC: A Deep Learning Approach to Augmented Kalman Filter-Based Single-Channel Speech Enhancement," in IEEE Access, vol. 9, pp. 64524-64538, 2021, doi: 10.1109/ACCESS.2021.3075209.](https://ieeexplore.ieee.org/document/9411829)

[2] [S. K. Roy, A. Nicolson, and K. K. Paliwal, "DeepLPC-MHANet: Multi-Head Self-Attention for Augmented Kalman Filter-based Speech Enhancement," in IEEE Access, vol. 9, pp. 70516-70530, 2021, doi: 10.1109/ACCESS.2021.3077281.](https://ieeexplore.ieee.org/document/9422809)

[3] [1.	S. K. Roy, A. Nicolson, and K. K. Paliwal, "On Supervised LPC Estimation Training Targets for Augmented Kalman Filter-based Speech Enhancement," in Speech Communication, vol. 142, pp. 49-60, doi: https://doi.org/10.1016/j.specom.2022.06.004.](https://www.sciencedirect.com/science/article/abs/pii/S0167639322000875)



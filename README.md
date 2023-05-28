# Supervised-LPC-Training-Target-AKF
# On supervised LPC estimation training targets for augmented Kalman filter-based speech enhancement

Supervised LPC Training Target is Deep Learning Framework to find the best LPC training target as well as Deep Learning Method in [[2]](https://ieeexplore.ieee.org/document/9422809) 
to optimize LPC Estimates of Augmented Kalman Filter for Speech Enhancement in Real-Life Condition. It is an extended work of previous [DeepLPC](https://ieeexplore.ieee.org/document/9411829) 
and [DeepLPC-MHANet](https://ieeexplore.ieee.org/document/9422809). 

# Introduction:
1. The accuracy of LPC estimates depend on the choice of LPC training target. In this work, we simulate four supervised training targets:
2. 1. Line Spectrum Frequency (LSF)
3. 2. LPC Power Spectra
4. 3. Magnitude Spectrum 
5. 4. Log Power Spectrum  
6. for deep learning model for accurate LPC estimation.
7. 
8. Although [DeepLPC](https://ieeexplore.ieee.org/document/9411829) addresses accurate LPC estimates in noisy conditions, however, there is room for investigating state-of-the-art deep learning models for more accurate LPC parameter estimates in noisy conditions. 
9. The accurate estimates of LPC are used in designining Augmented Kalman Filter for Speech Enhancement as shown in Fig. 1.

# Key Contributions: 

1. Develop a new deep learning framework, namely DeepLPC-MHANet within the Multi-Head Self Attention Network (MHANet). 
2. DeepLPC-MHANet learns a mapping from the noisy speech LPC power spectra to the clean speech and noise LPC power spectra from where the corresponding LPC parameters are computed. 
3. By producing less biased clean speech and noise LPC estimates, DeepLPC enables the AKF to produce enhanced speech at a higher quality and intelligibility in real-life noise conditions than [DeepLPC] (https://ieeexplore.ieee.org/document/9411829).
![Fig1](https://github.com/sujancseru/DeepLPC-MHANet/assets/130210435/703a40ea-768f-4270-8233-85bc3cc52d38)

# Implementation: 
1. DeepLPC-MHANet utilize MHANet as used in [Deep Xi MHANet](https://github.com/anicolson/DeepXi).
2. In DeepLPC-MHANet, MHANet learns a mapping from the noisy speech LPC power spectra to the clean speech and noise LPC power spectra from where the corresponding LPC parameters are computed.
3. To facilated the convergency of the gradient optimization algorith, it is necessary to generate normalized training target. It was shwon in [[1]](https://ieeexplore.ieee.org/document/9411829) that the log LPC power spectra of clean speech and noise signal can be fitten with Gaussian Distribution. Therefore, the Gaussian CDF has been used to normalize the log LPC power spectra. 



[1] [S. K. Roy, A. Nicolson, and K. K. Paliwal, "DeepLPC: A Deep Learning Approach to Augmented Kalman Filter-Based Single-Channel Speech Enhancement," in IEEE Access, vol. 9, pp. 64524-64538, 2021, doi: 10.1109/ACCESS.2021.3075209.](https://ieeexplore.ieee.org/document/9411829)

[2] [S. K. Roy, A. Nicolson, and K. K. Paliwal, "DeepLPC-MHANet: Multi-Head Self-Attention for Augmented Kalman Filter-based Speech Enhancement," in IEEE Access, vol. 9, pp. 70516-70530, 2021, doi: 10.1109/ACCESS.2021.3077281.](https://ieeexplore.ieee.org/document/9422809)



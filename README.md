# Discrete-time Kalman filter implementation methods
 
This repository contains MATLAB functions for various Kalman filter (KF) implementation methods. They are given in a posteriori form, i.e., no data are assumed to be known at the initial step and, hence, the time update comes first. 

# References
Each code (implementation method) includes the exact reference where the particular algorithm was published. 
If you use these codes in your research, please, cite the corresponding articles mentioned in the codes.  

# Remark
The codes have been presented here for their instructional value only. They have been tested with care but are not guaranteed to be free of error and, hence, they should not be relied on as the sole basis to solve problems. 

# Steps to reproduce
- `Test_KFs` is the script that performs Monte Carlo runs for solving filtering problem by various KF implementations.
- `Test_LLF` is the script for calculating the negative log LF by various filtering algorithms. 
- `Illustrate_XP` is the script that illustrates the obtained estimates and the diagonal entries of the error covariance matrix (over time). You can find its call at the end of the script above, which is commented. Just delete this comment sign.
- `Illustrate_LLF` is the script that illustrates the negative log LF calculated by various filtering algorithms. 
- `Simulate_Measurements` stands for simulating the state-space model and generating the measurements for the filtering methods.

When the state is estimated, the resulted errors should be the same for all implementation methods because they are mathematically equivalent to each other. Their numerical properties differ, but the ill-conditioned test examples are not given here. 

# List of the KF implementation methods

Conventional algorithms:
 -  `@Riccati_KF_standard` is the Conventional implementation by Kalman (1960)
 -  `@Riccati_KF_Joseph`   is the Conventional Joseph stabilized implementation by Bucy & Joseph (1968)
 -  `@Riccati_KF_Swerling` is the Conventional implementation based on Swerling's formula (1959)
 -  `@Riccati_KF_seq`      is the Sequential Kalman Filter (component-wise measurement update)

Square-root algorithms by using Cholesky factorization:
 -  `Riccati_KF_SRCF_QL`   is the Square-Root Covariance Filter with lower triangular factors by Park & Kailath (1995), <a href="http://doi.org/10.1109/9.384225">DOI</a> 
 -  `Riccati_KF_SRCF_QR`   is the Square-Root Covariance Filter with upper triangular factorsby Park & Kailath (1995), <a href="http://doi.org/10.1109/9.384225">DOI</a> 
 -  `Riccati_KF_SRCF_QR_seq` is the Sequential Square-Root Covariance Filter with upper triangular factors by Kulikova (2009), <a href="http://dx.doi.org/10.1134/S0005117909050129">DOI</a>  
 -  `Riccati_KF_eSRCF_QL`  is the Extended Square-Root Covariance Filter with lower triangular factors by Park & Kailath (1995), <a href="http://doi.org/10.1109/9.384225">DOI</a>  
 -  `Riccati_KF_eSRCF_QR`  is the Extended Square-Root Covariance Filter with upper triangular factors by Park & Kailath (1995), <a href="http://doi.org/10.1109/9.384225">DOI</a> 

Square-root algorithms by using singular value decomposition:
 -  `Riccati_KF_SVDSR`     is the SVD-vased Filter by L. Wang et.al. (1992), <a href="http://doi.org/10.1109/CDC.1992.371522">DOI</a>
 -  `Riccati_KF_SVD`       is the SVD-based Covariance Filter by Kulikova & Tsyganova (2017), <a href="http://doi.org/10.1049/iet-cta.2016.1282">DOI</a>
 -  `Riccati_KF_SVDe`      is the "economy size" SVD-based Covariance Filter by Kulikova et.al. (2021), <a href="10.1016/j.cam.2019.112487">DOI</a>

*************************************************
*   Solved By: Bhupati Bhupen Singh Mohanta  	*
*   Roll no : 117CS0233			    	*
*   Dt- 28/08/2020				*
*************************************************

Steps involved:
******************
NOTE: Run "Assignment_2_117CS0233.ipynb" file
 
1. Read R-band, G-band, B-band and I-band images.

2. Create a (512*512) feature vector

3. Calculate mean of each feature.

4. Subtract each feature mean from their corresponding feature values.
   Note. It is done to transfer the origin, so that all data points will be now centered around origin.

5. Calculate (4*4) covariance matrix.

6. Calculate eigen values and eigen vectors for the above covariance matrix.

7. Now, re-arrange the feature columns according to the descending order of eigen values.
   Accordingly re-arrange the eigen-vectors too.
   Since, eigen values are already in descending order there is no need for rearrangement.
------------------------------------------------------------------------------------------------------------

Note. The following steps are done in modular fashion at a time using function (for each image)

8. Apply linear transformation on the feature vector obtained in step 4.
   i.e. multiplying the feature vector with considered eigen vector.

9. matrix obtained from step 8 are origin centric. To convert them to their original axes system add them with their corresponding mean.
   
10. From step 9 we shall have 4 princial component images.
    (e.g. "1_transformed.jpg")
    Apply Histogram-Equalization on these transformed images to see equalized images.
    (e.g. "1_eqalized.jpg")

11. Verify if(sum(eigen-values) == sum(diagonal elements in covariance matrix)):
		then the Eigen values for the corresponding covariance matrix is correct. 

*************************************************************************************************************************

OBSERVATION:
*************

Eigen value of feature 2 (i.e. img 2) is 24.8% of  Eigen value of feature 1 (i.e. img 2) 
Eigen value of feature 3 (i.e. img 3) is 03.1% of  Eigen value of feature 1 (i.e. img 2) 
Eigen value of feature 4 (i.e. img 4) is 01.3% of  Eigen value of feature 1 (i.e. img 2) 

So, feature 3 and 4 adds more noise to our feature vector.
    As it can be seen in their corresponding "1_transformed.jpg" or "1_eqalized.jpg".

Note. Histogram-Equalization normalizes the feature values/pixel values distribution.
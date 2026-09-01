# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# ECE 2112 - Experiment 2: Numerical Python (NumPy)
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

##### Name: Tan, Stalwart Reign J.
##### Section: 2ECE-D

## _____________________________________________________________________________________________________
#### <p align="justify"> This experiment focuses on the application of Numerical Python, also known as NumPy, for specific performances, such as numerical computations, mathematical operations, and manipulation of arrays in Python. This will also demonstrate how to properly code numerical data without using for or while loops, instead 'Boolean' and 'NumPy arrays' will be utilized in this experiment. </p>
## _____________________________________________________________________________________________________

#
## A. Reproducible Normalization Problem
#### <p align="justify"> In this problem, a 5×5 array (X) is composed of random integers from 10 to 100, and it is asked to get the average (.mean()) and standard deviation (.std()) of X. To achieve a mean of approximately 0 and standard deviation of approximately 1 without using loop, we have to normalize the array using (X - np.mean(X)) / np.std(X)). The normalized array (X_normalized) is a new set of 5×5 integer array that came from the original random integer values in array (X). </p>

    import numpy as np
  
    np.random.seed(2112)
    X = np.random.randint(10, 101, size=(5, 5))
    X                                             #5x5 array (X)

##### Note:

(np.random.seed(2112)) allows us to create a reproducible random 5×5 integer array (X), while (np.random.randint(10, 101, size=(5, 5))) generates the random integers inside the array. 


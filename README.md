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
        
        #Result:
            array([[48, 11, 15, 67, 21],
                  [11, 41, 13, 66, 24],
                  [71, 79, 53, 67, 70],
                  [77, 35, 91, 19, 96],
                  [35, 54, 37, 41, 17]])

##### Note:

(np.random.seed(2112)) allows us to create a reproducible random 5×5 integer array (X), while (np.random.randint(10, 101, size=(5, 5))) generates the random integers inside the array. 

    Average = np.mean(X)
    Average

        #Result:
            np.float64(46.36)
            
    Std = np.std(X)
    Std                     #Standard deviation

        #Result:
            np.float64(25.864075471588002)

.mean( ) and .std( ) are used to calculate the average (mean) and the standard deviation.

    X_normalized = (X - np.mean(X)) / np.std(X)
    X_normalized                                 #Normalized array

        #Result:
            array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
                   [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
                   [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
                   [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
                   [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])

X_normalized is the normalized array. The list of values on this array are the result of applying the mean and the standard deviation to the original values (X).

    np.mean(X_normalized)  #Average of X_normalized

        #Result:
            np.float64(0.0)

    np.std(X_normalized)  #Standard deviation of X_normalized

        #Result:
            np.float64(0.9999999999999999)

##### Note:

Display X, X normalized, its mean, and its standard deviation.

    print (X)                       #X
    print (Average)                 #Mean of X
    print (Std)                     #Standard deviation of X
    print (X_normalized)            #X normalized
    print (np.mean(X_normalized))   #Mean of X normalized
    print (np.std(X_normalized))    #Standard deviation of X normalized

        #Result:
            [[48 11 15 67 21]
             [11 41 13 66 24]
             [71 79 53 67 70]
             [77 35 91 19 96]
             [35 54 37 41 17]]
            46.36
            25.864075471588002
            [[ 0.06340841 -1.36714726 -1.2124926   0.79801809 -0.98051059]
             [-1.36714726 -0.20723725 -1.28981993  0.75935442 -0.86451959]
             [ 0.95267275  1.26198209  0.25672675  0.79801809  0.91400909]
             [ 1.18465476 -0.43921926  1.72594609 -1.05783793  1.91926443]
             [-0.43921926  0.29539042 -0.36189192 -0.20723725 -1.13516526]]
            0.0
            0.9999999999999999

    np.save("X_normalized.npy", X_normalized)
##### Note:
np.save() allows us to save a NumPy array as a .npy file.

#
## B. Cubes Divisible by 4 Problem

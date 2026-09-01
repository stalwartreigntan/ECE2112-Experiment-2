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
#### <p align="justify"> The use of NumPy in this problem is to create a 10×10 array named C. The values of this array consists of first 100 positive integers. To create array C, we use (np.arange(1, 101)) to generate the values inside the array, and use (C.reshape (10, 10)) to form a 10 rows × 10 columns of the values after we define the numbers. </p>


    import numpy as np

    numbers = np.arange(1, 101)
    numbers

        #Result:
            array([  1,   2,   3,   4,   5,   6,   7,   8,   9,  10,  11,  12,  13,
                    14,  15,  16,  17,  18,  19,  20,  21,  22,  23,  24,  25,  26,
                    27,  28,  29,  30,  31,  32,  33,  34,  35,  36,  37,  38,  39,
                    40,  41,  42,  43,  44,  45,  46,  47,  48,  49,  50,  51,  52,
                    53,  54,  55,  56,  57,  58,  59,  60,  61,  62,  63,  64,  65,
                    66,  67,  68,  69,  70,  71,  72,  73,  74,  75,  76,  77,  78,
                    79,  80,  81,  82,  83,  84,  85,  86,  87,  88,  89,  90,  91,
                    92,  93,  94,  95,  96,  97,  98,  99, 100])

The values inside the array are the first 100 positive integers.


    C = numbers**3
    C

        #Result:
            array([      1,       8,      27,      64,     125,     216,     343,
                       512,     729,    1000,    1331,    1728,    2197,    2744,
                      3375,    4096,    4913,    5832,    6859,    8000,    9261,
                     10648,   12167,   13824,   15625,   17576,   19683,   21952,
                     24389,   27000,   29791,   32768,   35937,   39304,   42875,
                     46656,   50653,   54872,   59319,   64000,   68921,   74088,
                     79507,   85184,   91125,   97336,  103823,  110592,  117649,
                    125000,  132651,  140608,  148877,  157464,  166375,  175616,
                    185193,  195112,  205379,  216000,  226981,  238328,  250047,
                    262144,  274625,  287496,  300763,  314432,  328509,  343000,
                    357911,  373248,  389017,  405224,  421875,  438976,  456533,
                    474552,  493039,  512000,  531441,  551368,  571787,  592704,
                    614125,  636056,  658503,  681472,  704969,  729000,  753571,
                    778688,  804357,  830584,  857375,  884736,  912673,  941192,
                    970299, 1000000])

Array C must begin with 1^3 and ends with 100^3, Therefore; (C = numbers**3) simply cubes each number inside the array, which results to a list of cubed values.

    C = C.reshape (10, 10)
    C                         #10 rows, 10 columns

        #Result:
            array([[      1,       8,      27,      64,     125,     216,     343,    512,     729,    1000],
                   [   1331,    1728,    2197,    2744,    3375,    4096,    4913,    5832,    6859,    8000],
                   [   9261,   10648,   12167,   13824,   15625,   17576,   19683,    21952,   24389,   27000],
                   [  29791,   32768,   35937,   39304,   42875,   46656,   50653,    54872,   59319,   64000],
                   [  68921,   74088,   79507,   85184,   91125,   97336,  103823,    110592,  117649,  125000],
                   [ 132651,  140608,  148877,  157464,  166375,  175616,  185193,    195112,  205379,  216000],
                   [ 226981,  238328,  250047,  262144,  274625,  287496,  300763,    314432,  328509,  343000],
                   [ 357911,  373248,  389017,  405224,  421875,  438976,  456533,    474552,  493039,  512000],
                   [ 531441,  551368,  571787,  592704,  614125,  636056,  658503,    681472,  704969,  729000],
                   [ 753571,  778688,  804357,  830584,  857375,  884736,  912673,    941192,  970299, 1000000]])


<p align="justify"> To obtain every cubed value divisible by 4, we use the Boolean condition (C[C % 4 == 0]). To understand this Boolean condition, (C % 4) tells the program to divide each value inside array C by 4, while ( == 0 ) gives the values that are divisible by 4 without a remainder, or with a remainder of 0. </p>

    div_by_4 = C[C % 4 == 0]
    div_by_4

        #Result:
            array([      8,      64,     216,     512,    1000,    1728,    2744,
                      4096,    5832,    8000,   10648,   13824,   17576,   21952,
                     27000,   32768,   39304,   46656,   54872,   64000,   74088,
                     85184,   97336,  110592,  125000,  140608,  157464,  175616,
                    195112,  216000,  238328,  262144,  287496,  314432,  343000,
                    373248,  405224,  438976,  474552,  512000,  551368,  592704,
                    636056,  681472,  729000,  778688,  830584,  884736,  941192,
                    1000000])

##### Note:

Display the shape of C, the array div by 4, and the number of selected elements.

    print (C.shape)        #Shape of C
    print (div_by_4)       #Array div by 4
    print (div_by_4.size)  #Number of selected elements

        #Result:
            (10, 10)
            [      8      64     216     512    1000    1728    2744    4096    5832
                8000   10648   13824   17576   21952   27000   32768   39304   46656
               54872   64000   74088   85184   97336  110592  125000  140608  157464
              175616  195112  216000  238328  262144  287496  314432  343000  373248
              405224  438976  474552  512000  551368  592704  636056  681472  729000
              778688  830584  884736  941192 1000000]
            50

To save the NumPy array as .npy file:
    
    np.save("div_by_4.npy", div_by_4)


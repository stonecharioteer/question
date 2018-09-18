# A Question

## About the Dataset

The file, data.dat, is an *ascii* file with acceleration information, provided in sets like below. 



```
0                                                                                                            SUBCASE 1              
      FREQUENCY =  0.000000E+00
                                       C O M P L E X   A C C E L E R A T I O N   V E C T O R
                                                         (MAGNITUDE/PHASE)
 
      POINT ID.   TYPE          T1             T2             T3             R1             R2             R3
0          101      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          102      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          103      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          104      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          105      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          106      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          107      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          108      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
0          109      G      0.0            0.0            0.0            0.0            0.0            0.0
                             0.0            0.0            0.0            0.0            0.0            0.0
1                                                                          FEBRUARY   5, 2018  MSC Nastran  7/ 3/15   PAGE    94
                                                                                                                                    
```

For each point ID, there corresponds two rows. The first row is the magnitude, the second row is the phase. Note that both these rows correspond to the same point id.

T1, T2, T3, R1, R2 and R3 correspond to spatial and rotational information about the vectors.



## Problem Statement

For brevity, *ignore* the rest of the information in the file and parse the following.

- [ ] FREQUENCY
- [ ] POINT ID and the corresponding T and R columns (both magnitude and phase)

Create a commandline application, called `parse_vectors.py`, which will parse this information and write to a csv file with the following columns:

```
  [ 
  "point_id", "frequency",
  "t1_magnitude", "t1_phase", "t2_magnitude", "t2_phase", "t3_magnitude", "t3_phase", 
  "r1_magnitude", "r1_phase", "r2_magnitude", "r2_phase", "r3_magnitude", "r3_phase"
  ] 
```

Your application should output the following help statement.

```
      python parse_vectors.py -h
      Tool to parse the vectors from a given data file.
      
      usage: parse_vectors.py [-h] [--i] [--o] [--p_ids]
      
      positional arguments:
            i           Input dat file.
            o           Output csv file.
      optional arguments
            -h, --help  show this help message and exit.
            --p_ids     Only read data for the given point ids.
```

## Instructions

1. Write a function `parse_vectors` that performs the core functionality of the 
1. Use the `argparse` library to create the commandline tool, not `sys.argv`.
1. Do not use any third-party libraries to parse this file. Rely on the simplest logic.
1. When in doubt, remember [the Zen of Python.](https://www.python.org/dev/peps/pep-0020/)
1. Use the folder structure recommended for python applications [here](https://realpython.com/python-application-layouts/).
1. Write unit-tests for your code. Assert that the number of points in the csv file is equal to the number of points in the original data file after using your core function.
1. Fork this repo and put your answer there.
1. Take no longer than 2 days to solve this problem.

## Scoring Methodology

Your response will be scored one point on each of the following

1. **Code originality.** You can Google for answers, but asking on StackOverflow, Reddit, Quora or other online forums for straight up answers is a no. Also copying answers from other forks is a no.
2. **Code readability.** Follow the rules outlined in PEP20.
3. **Tests.** Your tests must pass other datasets we will use. The given data is to be assumed representative of the other datasets.
4. **Commit History.** Your answers, naturally, must be on Github, or Gitlab, if you so prefer. You will be scored for the commit messages, so commit often, and make sure your commits have meaning.
5. **Algorithm Readability.** Algorithms matter. A simple algorithm, when done well, is beautiful and shows that you think coherently. We love list comprehensions too, but trying to recreate The Inception in list comprehensions is just inviting trouble.
6. **Documentation** Comments matter. But they should be readable, and follow the recommended conventions.

## Automatic Failures

You will automatically fail this test if your code

1. Is plagiarised from other forks.
2. Has **anything** related to the data or positions of the data hardcoded into it. If you have to make assumptions, parametrize them.
3. Has global variables and/or global scope.

## Bonus Points

One bonus point each for:

1. **Algorithm Simplicity**
2. **Docstrings**, readable, sphinx-compliant, docstrings.
3. **Sphinx-based documentation**.
4. **pip-installable cli**.


## Note

Remember, it is okay to learn how to solve this question while solving it. Google is your friend.

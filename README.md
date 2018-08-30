# A Question

The file, data.dat, is an ascii file with acceleration information, provided in sets like below. 


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

For brevity, ignore the rest of the information in the file and parse the following.

- [ ] FREQUENCY
- [ ] POINT ID and the corresponding T and R columns (both magnitude and phase)

And write this information to a csv file with the following columns:

```
  [ 
  "point_id",
  "t1_magnitude", "t1_phase", "t2_magnitude", "t2_phase", "t3_magnitude", "t3_phase", 
  "r1_magnitude", "r1_phase", "r2_magnitude", "r2_phase", "r3_magnitude", "r3_phase"
  ] 
```

Feel free to fork this repo and provide the solution.

That is all.

Do not use any third-party libraries to parse this file. Rely on the simplest logic.

When in doubt, remember [the Zen of Python.](https://www.python.org/dev/peps/pep-0020/)

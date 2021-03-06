# <ins>Problem: Cuckoo Hashing</ins>

Implement a Cuckoo hash table in which two separate tables are maintained. Each table should have a fixed size of 13. Use the hash function
*h1(x) = x mod 13* for the first table, and *h2(x) = 11 – (x mod 11)* for the second table.

Your program should read an input file, *input.txt*, consisting of one input per line, insert the input to the table in order, and print out the final
content of the hash table in the provided format. Your implementation should utilize the provided *CuckooHashTable.h* file as is, without any edits.
Note that the hash tables are implemented as a 2x13 matrix (vector of vectors), and that a print method declaration is provided, for you to implement.

Inserting an element that already exists in the table should have no effect. Your program should be able to detect if an insert results in an infinite
loop in the hash, and exit with the following error message: “Error: Insert causes infinite loop”.

    Sample input.txt file content: 
      1
      4
      6
      27
      123
      14
      17
      195
      
     Sample output for the above input: 
     Table 1:
        195 
        14 
        -
        - 
        17 
        - 
        123 
        -
        -
        -
        -
        -
        -
        
      Table 2: 
        -
        -
        -
        -
        -
        6 
        27 
        4 
        -
        - 
        1
        -
        -


### <ins>Expected Outputs:</ins>

    Test case 0:

    Table 1:
    195
    14
    -
    -
    17
    -
    123
    -
    -
    -
    -
    -
    -
    Table 2:
    -
    -
    -
    -
    -
    6
    27
    4
    -
    -
    1
    -
    -

    Test case 1: Inserting an already inserted value

    Table 1:
    195
    14
    -
    -
    17
    -
    123
    -
    -
    -
    -
    -
    -
    Table 2:
    -
    -
    -
    -
    -
    6
    27
    4
    -
    -
    1
    -
    -

    Test case 2: Inputs which require moving values from the 2nd table back to the 1st

    Table 1:
    195
    14
    -
    -
    30
    -
    6
    -
    -
    -
    -
    -
    -
    Table 2:
    -
    -
    -
    -
    -
    17
    27
    4
    -
    123
    1
    -
    -

    Test case 3: Insert results in infinite loop

    Infinite loop detected when 212 is inserted

    Test case 4: Fill tables

    Table 1:
    13
    1
    210
    3
    4
    265
    6
    397
    8
    9
    270
    245
    311
    Table 2:
    -
    10
    306
    195
    205
    17
    27
    15
    14
    123
    12
    220
    -

# Lab Report 2

## Code Change 1 

We made the following code change to account for the infinite loop that arises when the markdown file has extra lines that do not contain links. 
![image](https://user-images.githubusercontent.com/103202818/164816486-d654dcd5-82ed-4ba0-b976-fa8bf8fc4d25.png)

This is the 
[test file](https://jadechng.github.io/markdown-parser/test-file.md) we used.\
In the test file, added extra sentences and lines at the back evoke an infinite loop.


This is the symptom of the *failure-inducing input* for the original version of the code that was failing: 
![image_error](https://user-images.githubusercontent.com/103202818/164817580-39d9c43c-7ab7-4edf-acc1-416510dd8bad.png)

As you can see, it throws a OutOfMemoryError exception. This occurs as the original code would continue searching the test file for the next "[" until it runs out of memory, hence causing an infinite loop. 

To solve this, we have added an if statment to break the while loop if the following lines do not contain "[" . 


## Code Change 2
![image]()

## Code Change 3
![image]()
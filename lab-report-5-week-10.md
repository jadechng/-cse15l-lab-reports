# Lab Report 5

In this lab report, I chose two tests form the 652 tests provided in lab 9 to discuss the differences in results with my code and the code provided

***

## Test 1
For test 1 would be discussing the test file, `201.md`. [link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md) \
I found the tests with the different results using `vimdiff` on the results of running a bash for loop. 

The results of my code is on the left and the reults of the code provided is on the right:

![image](https://user-images.githubusercontent.com/103202818/171518055-1d9ea298-ca4f-40e2-8876-3a64769eab6a.png)

As you can see, by code's output is `[]` while the provided code is `[baz]`. According the the [CommonMark](https://spec.commonmark.org/dingus/) demo site, the result should have been `[(baz)]`. Hence, neither implementation is correct.

![image](https://user-images.githubusercontent.com/103202818/171519130-12ad97ab-e2f8-42c1-92dd-a3c7dfd59db1.png)

Since both implementations are wrong, I will discuss the bug in my own code.\
The bug in my own code is that it does not consider reference links using `:`. 

![image](https://user-images.githubusercontent.com/103202818/171519501-0d1615fe-0fc9-49dd-b208-10c59c24ac64.png)

Hence, to consider the refernce links, after the line highlighted, I could insert an if condition to consider the case that  a `:` occurs after the `]` indicating that it is a reference link and to look for the next open bracket `[`.

*** 
## Test 2
For test 2 would be discussing the test file, `490.md`. [link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/490.md) \
Like test 1, I found the tests with the different results using `vimdiff` on the results of running a bash for loop. 

The results of my code is on the left and the reults of the code provided is on the right:

![image](https://user-images.githubusercontent.com/103202818/171520260-4f80f699-e59b-496d-a7c9-1c3107e0b1d7.png)

As you can see, by code's output is `[<foo\ bar>]` while the provided code is `[]`. According the the [CommonMark](https://spec.commonmark.org/dingus/) demo site, the result should have been `[]`. Hence, the implmentation of the code provided is correct while mine is wrong

![image](https://user-images.githubusercontent.com/103202818/171520814-3d0147d9-94ad-44c2-85a7-f9134fcec63c.png)

The bug in my own code is that it does not consider the case in which there is a line break in the link.

![image](https://user-images.githubusercontent.com/103202818/171521295-8a249454-5b2d-4d04-a0cc-dba3f7495f38.png)

Hence, to consider line breaks, in the if-condition highlighted above, I would create a nested if-condition to iterate through the link where if a line break is found it'll break the while loop. 

***

[link](index.md) back to index page.







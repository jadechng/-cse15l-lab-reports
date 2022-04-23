# Lab Report 2

## Code Change 1 

We made the following code change to account for the infinite loop that arises when the markdown file has extra lines that do not contain links. 
![image](https://user-images.githubusercontent.com/103202818/164816486-d654dcd5-82ed-4ba0-b976-fa8bf8fc4d25.png)

This is the 
[test file](https://jadechng.github.io/markdown-parser/test-file.md) we used.\
In the test file, we added extra sentences and lines at the back evoke an infinite loop.


This is the symptom of the *failure-inducing input* for the original version of the code: 
![image_error](https://user-images.githubusercontent.com/103202818/164817580-39d9c43c-7ab7-4edf-acc1-416510dd8bad.png)

As you can see, it throws a OutOfMemoryError exception. This occurs as the original code would continue searching the test file for the next `[` until it runs out of memory, hence causing an infinite loop. 

To solve this, we have added an if statment to break the while loop by checking if the following lines do not contain `[`. 


## Code Change 2

We made the following code change to account for the StringIndexOutOfBoundsException that occurs when a file totally does not contain a link: 
![image](https://user-images.githubusercontent.com/103202818/164838654-3dfa70de-fcbb-4a0b-a10f-d99b64062534.png)

This is the [test file](https://jadechng.github.io/markdown-parser/failfile.md) we used that does not contain a link. 

This is the symptom of the *failure-inducing input* for the original version of the code: 
![image_error](https://user-images.githubusercontent.com/103202818/164838745-d5cfc8ca-7c2e-472c-86d5-4c232d6c9e50.png)

As you can see, it throws a StringIndexOutOfBoundsException as the program is unable to find the first open bracket `[` . Hence, to account for this error, in the while loop, we have added an if statment to consider the event that there is no open braket `[` in the file, which would cause the while loop to break, returning an empty ArrayList. 

## Code Change 3

We made the following code changes to ensure that MarkdownParse only adds valid links into the ArrayList. The code ensures not to add links when the `[]` and `()` are very far apart in the file, as well as not to add image links

![image](https://user-images.githubusercontent.com/103202818/164883094-9e032933-cbf5-4cac-b53d-a260609d6c3a.png)

This is the 
[test file](https://jadechng.github.io/markdown-parser/failedfile2.md) we used. In this test file, we inluded a invalid link when the `[]` and `()` are very far apart as well as image link. 

This is the symptom of the *failure-inducing input* for the original version of the code: 
![image](https://user-images.githubusercontent.com/103202818/164883424-e9579210-fa30-4470-8d0e-122685b3d0ac.png)

As you can see, the original code has added the invalid link and the image link into the array which should not have happened. Hence, to account for this bug, we added an if statement to check if the hyperlink is indeed next to the url, making it a valid link, as well as a second nested if statment to check if the `!` is not next to the openBracket `[`. 

***
[link](index.md) back to index page. 

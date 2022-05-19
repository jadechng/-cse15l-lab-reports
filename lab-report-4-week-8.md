# Lab Report 4

In this Lab Report, I tested my implementation of mardown-parse and the implementation I reviewed in week 7 on the snippets provided. Here are the links to the respective reporsitories:
* [link](https://github.com/jadechng/markdown-parser) to my repository
* [link](https://github.com/yuxinguo13/markdown-parser.git) to repository I reviewed

## Snippet 1
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```
For the first snippet, the expected code output should be: 
[`google.com,google.com,ucsd.edu]

### My implementation
Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169406856-a9828ab9-fbbf-4daa-9690-194c7785119b.png)

My implementation's output: 
![image](https://user-images.githubusercontent.com/103202818/169407530-3515f204-1ba2-4bb4-b4e5-586294565c5a.png)
As you can see, my implementation did not pass as it did not consider "ucsd.com" as a link and considered "url.com".

### Implementation I reviewed

Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169418755-f67828c0-01d6-4ec8-be68-713176d7d398.png)

Implementation I reviewed in week 7 output: 
![image](https://user-images.githubusercontent.com/103202818/169409420-1d3c7b10-1e49-41e4-a5ed-12f5d5c47881.png)
As you can see, it did not pass as it considered "url.com" as a valid link and did not consider the others. 

* for my program, I beleive that a large code change would be needed to make my programme work as I would need to add multiple if conditions to consider the cases of backticks and open-brackets. One if condition could be if the backticks occur before the open-brackets and the other if it occurs after, and then looking for the next back tick in the file.

***

## Snippet 2
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```
For the second snippet, the expected code output should be: 
```[a.com,a.com(()),example.com]```

### My implementation

Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169410107-4198f5d3-239a-48fc-8f05-aa18393b8adc.png)

My implementation's output: 
![image](https://user-images.githubusercontent.com/103202818/169410308-8323b456-627d-4438-8b11-b2c782c341a2.png)
As you can see, my implementation did not pass as it seems that my code would iterate through the link up to the first `)`.

### Implementation I reviewed

Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169418849-c6a69402-fa8c-4d96-9598-d3c2fe614927.png)

Implementation I reviewed in week 7 output: 
![image](https://user-images.githubusercontent.com/103202818/169410707-60d98b56-7150-4e33-a233-d1880b593431.png)
As you can see, it did not pass as it resulted in an infinite loop. 

* For my program, I beleive that a small code change would be needed to fix this issue. An if condition that I would include would be to consider the case that if there is more then one open-braket/parantheses and to look for its matching closed-bracket/parantheses.
***

## Snippet 3
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/

)

And then there's more text
```

### My implementation
For the third snippet, the expected code output should be: 
```[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]```

Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169411664-d07c2178-476b-4528-ab1a-1f016717568b.png)

My implementation's output: 
![image](https://user-images.githubusercontent.com/103202818/169412425-5c3850d2-8498-4f3f-a13c-70156e70c4ef.png)
As you can see, my implementation did not pass as it seems that it does not consider line breaks for invalid links. 

### Implementation I reviewed
Screenshot of code in `MarkdownParseTest.java` to test: 
![image](https://user-images.githubusercontent.com/103202818/169418968-96500cd8-e1c5-4292-bb9a-dfd6302894fa.png)

Implementation I reviewed in week 7: 
![image](https://user-images.githubusercontent.com/103202818/169413222-3b70212c-edd6-4901-a5dd-ce4e93b27f3b.png)
As you can see, it did not pass as it resulted in an StringIndexOutOfBoundsException. 

* for my program, I believe that only a small code change would be suffcient to fix this issue as I would only need to consider the case that there is a line break in the link text. Morevover,  I beleive the fixed code from the above snippet would be able to fix the issue of the link not containing a closing parentheses

***

[link](index.md) back to index page.


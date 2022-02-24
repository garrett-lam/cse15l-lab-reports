# Lab Report 4

Link to [my markdown-parse repository](https://github.com/garrett-lam/markdown-parse)

Link to [group I reviewed repository](https://github.com/JessalynWang/markdown-parse)

### According to VS Code preview,

There are 3 valid links in Snippet 1: **`google.com**, **google.com**, and **ucsd.edu**.
![snippet1](snippet1.png)

There are 3 valid links in Snippet 2: **a.com**, **a.com(())**, and **example.com**.
![snippet2](snippet2.png)

There is 1 valid link in Snippet 3: **https://ucsd-cse15l-w22.github.io/**
![snippet3](snippet3.png)

Based on VS Code preview, I created these tests to run in my own markdown-parse repository and in the other group's markdown-parse repository I reviewed. (6 test cases were created total, 3 in each repository)
![testsnippet1](testsnippet1.png)
![testsnippet2](testsnippet2.png)
![testsnippet3](testsnippet3.png)
* I used `contents` to store the contents of the each snippet's markdown file by calling the `readString` method
* `expect` was used to store the expected output if `MarkdownParse.java` worked properly. In other words, the valid links based on VS Code preview
* JUnit's `assertEquals` method allows me to compare check if `expect` equals to `contents`.

## JUnit test output from my markdownparse implementation
![mygroup](mygroup.png)
* From the output, my implementation of markdownparse failed all three test cases 

## JUnit test output for other group's markdownparse implementation
![othergroup](othergroup.png)
* From the output, the other group's implementation of markdownparse also failed all three test cases 

## Follow Up Code Change Questions
* For snippet 1, there might be a small code change that would make the program work for all backtick related cases. From the VS Code preview, it seems like only backticks that occur before the brackets lead to an invalid link. Therefore, similarly to how we fixed the program for images by checking for `!` characters. We could do the same for the backticks.

* For snippet 2, I do not think there is a small code change that would make the program work for all cases that have nested parentheses, brackets, and escaped brackets. To have all these cases to work for the program would require many variables and data structures to keep track of what is going on in the code. An idea would to potentially use one Stack to keep track of brackets, another Stack to keep track of parentheses, and then a loop and if statements for the escaped brackets


* For snippet 3, I do not believe there is a small code change that would make the program work for all cases that have newlines in the brackets and parentheses. For these cases, we could check for the `\n` character after each variable: `nextOpenBracket`, `nextCloseBracket`,`openParen`, `closeParen` then having a counter until the next reaching the next variable. This may require 4 loops and multiple if statements that would go over 10 lines.
# Lab Report 2

## Code Change 1
The reason for adding this line of code is because of this: [Failure Inducing Input 1](https://github.com/garrett-lam/markdown-parse/commit/30dd4293655185b8c192a5d6a092b6849e9aa693)

![code change 1](codechangeone.png)

Running the code `javac MarkdownParse.java` followed by `java MarkdownParse failure-inducing-input1.md` outputs this:

![fail1output](fail1output.png)

* I added this line of code because the `indexOf()` method returns -1 if the argument, in this case `[` or `]` or `(`or `)` is not found in the markdown file
* This line of code allows for breaking out of the while loop which avoids the StringIndexOutOfBoundException
* The output after the code is added is `[]`

---

## Code Change 2
The reason for coding this if statement is because of this: [Failure Inducing Input 2](https://github.com/garrett-lam/markdown-parse/commit/993ca3cffa6ad9b1c22fc1bf26b953107ab9489b)


![code change 2](codechangetwo.png)

Running the updated code `javac MarkdownParse.java` followed by `java MarkdownParse failure-inducing-input2.md` outputs this:

![fail2output](fail2output.png)

* I added this line of code as it will prevent the code from adding the image file into the output. 
* This is because in markdown files, images must start with an exclamation mark next to the first open brackets
* Moreover, by adding `openParen == nextCloseBracket + 1` into the code, it allows for links that have text to be in between the close brackets and open parenthesis to be outputted.

---
## Code Change 3

![code change 3](codechangethree.png)



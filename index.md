## Welcome to GitHub Pages
# TESTING_TUTORIAL

## Visual Studio Code on Windows
### Installation
1.	Download the Visual Studio Code installer for Windows.
2.	Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe). This will only take a minute.
3.	By default, VS Code is installed under C:\users\{username}\AppData\Local\Programs\Microsoft VS Code.


## Node
Install node from this link
[[https://nodejs.org/en/]]


## JavaScript and Node.js
The first sample code is a basic code that adds two numbers together to get the sum. This just shows how to use JavaScript for unit testing. Now we need to setup our JavaScript and our Node.js Server. First let’s create a JavaScript file. Let’s call it index.js.

[[[Code Diagram](https://drive.google.com/file/d/1cDKXEPX3oHwcC_9KLTbyGBriKEndWNpQ/view?usp=sharing)]]


we are going to create a folder called Test_Tutorial then create a file called index.js inside the Server folder. This will have the code for the server to run. After creating the file, we need to run this command in the command line or terminal in the Server folder   (if you are using VScode go to the top left side which is the view tab and when it scrolls down you can click on terminal to get the terminal environment)

`npm init`

You will be asked a series of questions about the project. All the default responses would be fine. After that we are going to install some packages (dependencies ) that we are going to use.
Type the command below to install the required packages which are ***express, jest, puppeteer***

`npm install –save express`

`npm install --save-dev jest`

`npm i puppeteer`


(After npm init a package.json file is created with all dependencies. When you open it you find scripts then you can change what command test is assigned to …… Just assign it to jest as below) {
  `"scripts": {
    "test": "jest"
  }
}  `
To setup our server we need to type some code inside the index.js file which is the source file. It is written all in JavaScript. We need to require the packages and setup the server:


``` 
const express = require('express');

function plus(a, b) {
  return a + b;
}
module.exports = plus;
 ```

This is a code that adds two numbers `a` and `b` returning their `sum a+b`.  The function can then be exported using `module.exports = plus` so it can be accessed from other files on the server
After that we need to write a test file to confirm if the function for the code is run is right. The file would be named index.test.js like so:

```
const plus = require('./index');

test('adds 1 + 2 to equal 3', plusTest);

function plusTest() {
  expect(plus(1, 2)).toBe(3);
  
}
```

There is a function called **plus** that receives two numbers and returns those two sums added together. Looking at the syntax, we have a function plus that requires the source file index.js which is the same directory, **expect** and **tobe** are functions that are part of jest. plus is my function test function is part of jest. The code could be written in a more elegant way however for simplicity its best left like this
We then run the command in the terminal

`npm test`


```
PASS  ./index.test.js
  √ adds 1 + 2 to equal 3 (5ms)
Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        3.615s
Ran all test suites. 
```


As seen above this means the test case passed. HOPE you find this useful. ***There are more samples ahead though.****




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


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/holarmyde/testtutorial.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

# How to run a simple test using JEST - very similar to mocha
>> MAKE SURE YOU CHECK index.md FIRST before going through this file. I try to repeat some stuff from the index.md file just incase you did not read it.

  * Downloads
  * setup 
  * start writing codes

## For this tutorial, you will need to have the following things downloaded
  1. any code editor
  2. Since we are using JavaScript outside the browser, then you need node.js [here](https://nodejs.org/en/download/package-manager/)
  3. You need npm; the good thing is npm is with node, so when you download Node.js, you get npm installed on your computer.
  4. To check you have node and npm, open your terminal and enter the following
  ```javascript
  node -v
  npm -v
  ```
  5. Initialize your directory by entering the following on the terminal
  >> npm init

  5. press ENTER for everything it asks you

  6. Now use npm to install the three following packages used in the tutorial
  >> npm install --save jest assert puppeteer

  7. Check you package.json file and it should look something similar to 
  ```JSON
{
  "name": "test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "jest"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "assert": "^2.0.0",
    "jest": "^24.8.0",
    "puppeteer": "^1.16.0"
  }
}
  ```

  ### Quick and simple explanation of the packages
    * Jest - this is the engine to essential runs the test; Jest is mostly used with react and react native apps. You can also use mocha, which is very similar to Jest.
    * puppeteer - this is used to run a virtual browser called 'chromium', which is essentially what you run your test cases on.
    * assert - this is used to test for conditions
```javascript
  // the below should return true
assert(6===4+2)
```

  # Let us start coding!!!!
  1. But first, create a directory(folder), you can call it whatever you want to call it
  2. Inside the folder, create your first file - "[whatever name you want here].test.js"
  3. Make sure you attached the ".test.js" to the name of your file.
  4. Now, let's start coding!!!!
```JavaScript
// file name: basic.test.js
// bring in the following packages
const assert = require('assert'),
  puppeteer = require('puppeteer');

// global definition
let browser, page;

//before each test cases, we want to run a simple command
beforeEach(async()=>{
  browser = await puppeteer.launch({
    headless: false
  });
  page = await browser.newPage();
  await page.goto("https://www.whizping.com/");
});
// the above code will always RUN before any test cases we will do!!!
/*
  Line 70-72 basically starts up Chromium; you can confirm this only if you see a virtual chromium browser open up.
  Line 73: opens a new BLANK page on the virtual browser whereupon to run the test on.
  Line 74: this is the first page the virtual browser goes to visit upon launching, which in this case
   is my software application I built.
*/

// the below code will close the chromium browser after each test cases.
afterEach(async()=>{
  await browser.close();
});

// up to this point, we have NOT wrote any test cases yet

/* -------Testing the home page url------*/
test("test home page url", async()=>{
  const url = await page.url();
  assert(url==="https://www.whizping.com/");
});

//LINE 92-94: fetches the url page LINE 74; it then confirms that the url matches in line 94.

/* -------Testing the logo of whizping.com gives you home page upon clicking it------*/
test("clicking logo gets homepage",async()=>{
  await page.click("a.logoCSS");
  const url = await page.url();
  assert(url==="https://www.whizping.com/")
});
// LINE 101: using class selector to identify the Logo

/* -------Testing that clicking the contact icon will give you the contact page------*/
test("clicking contact us button",async()=>{
  await page.click("a#contactus");
  const url = await page.url();
  assert(url==="https://www.whizping.com/customerSupport")
});

/*-----Going to a youtube video and reloading it for 1.9 seconds, hence increasing views----*/
test("youtube video test", async()=>{
  const url = await page.url();
  await page.waitFor(1900);
  assert(url==="https://www.youtube.com/watch?v=703y9d4ROf8&app=desktop");
});


/* -------Testing that if you click login button, it will bring on google oauth flow------*/
test("test oauth flow",async()=>{
  await page.click("a#signinwithgoogle");
  const url = await page.url();
  expect(url).toMatch(/accounts\.google\.com/);
});

```
## MORE TO COME ON HOW TO ACTUALLY TEST AUTHENTICATION. I WILL NEED TO CREATE A FAKE USER TO SHOW THIS DEMO.


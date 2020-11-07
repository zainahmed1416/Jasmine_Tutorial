


# Jasmine Tutorial


# Introduction

Jasmine is a testing framework for Javascript that runs for Node.js or standalone in a browser. It is quite robust and flexible, compatible with all javascript-enabled frameworks. It aims to be non-intrusive on your IDE/application while having an easy to read and understand syntax. It is influenced by many other JavaScript unit testing frameworks.


# Why Use Jasmine

Jasmine is a simple and lightweight way to test anything with Javascript due to its minimally intrusive design and rich set of test matchers and even support for custom ones. Overall, it strives to make testing Javascript a very simple experience.


# Installation

_Jasmine for Node.js_

Add Jasmine to your package.json


```
npm install --save-dev jasmine
```


Initialize Jasmine in your project


```
npx jasmine init
```


Set jasmine as your test script in your package.json


```
"scripts": { "test": "jasmine" }
```


Run your tests


```
npm test
```


_Jasmine can also be installed as a standalone._

_Visit [this link](https://jasmine.github.io/pages/getting_started.html) to learn more about other installations._


# Setup


## Initialize a Project

Initialize a project for Jasmine by creating a spec directory and configuration json for you.


```
jasmine init
```


Note that if you installed Jasmine locally use npx jasmine instead of jasmine in any of these examples, like so:


```
npx jasmine init
```


Generate example spec and source files


```
jasmine examples
```


At this point you should be able to[ write your first suite](https://jasmine.github.io/tutorials/your_first_suite.html)<span style="text-decoration:underline;">.</span>


## Configuration

Customize spec/support/jasmine.json to enumerate the source files and spec files you would like the Jasmine runner to include. You may use dir glob strings.

Paths starting with ! are excluded, for example !**/*nospec.js.

spec_dir is used as a prefix for all spec_files and helpers. Helpers are executed before specs. For an example of some helpers see the[ react tutorial](https://jasmine.github.io/tutorials/react_with_npm)


```
{
  // Spec directory path relative to the current working dir when jasmine is executed.
  "spec_dir": "spec",

  // Array of filepaths (and globs) relative to spec_dir to include and exclude
  "spec_files": [
    "**/*[sS]pec.js",
    "!**/*nospec.js"
  ],

  // Array of filepaths (and globs) relative to spec_dir to include before jasmine specs
  "helpers": [
    "helpers/**/*.js"
  ],

  // Stop execution of a spec after the first expectation failure in it
  "stopSpecOnExpectationFailure": false,

  // Run specs in semi-random order
  "random": false
}
```


_Visit [this link ](https://jasmine.github.io/setup/nodejs.html)for more information on setting up Jasmine for Node.js_


# Use

Description

Jasmine starts by describing tests and features, for this we use the `describe()` method. We first describe out units, then within our units we describe functions to be tested. When describing the function’s behavior, we use the `it()` method. This method describes function behavior and what it is expected to output. Within the `it`For example, testing the `GET` function of some server would look like this. 

	`var request = require("request");`


```
	var base_url = "http://localhost:3000/"

	describe("Some HTTP server", function() {
		describe('GET /', function() {
			it("returns status code 200", function() {
				request.get(base_url, function(error, response, body){
					expect(response.statusCode).toBe(200);
				});
			});
		});
	});
```



# Code Walkthrough

Let us describe one Javascript test suite with Jasmine and how we would run it.


```
Touch spec/HelloWorldSpec.js
```


Jasmine specs typically describe a specific block of code or a specific function. So, the unit that makes up a Jasmine spec is the `describe` block. The describe block is the first step in writing a Jasmine test suite.


```
describe("Hello World Server", function() {

});
```


So, the first argument in the block is a text description of the tested feature, and the other is the function call that would execute the expectations for the test. 

The first thing we want to test on our server is whether it is returning the HTTP status OK (status code 200) when we send a GET request towards its root path.

Let’s describe this behaviour with the following Jasmine description:


```
describe("Hello World Server", function() {
  describe("GET /", function() {

  });
});
```


Now, let’s write our first expectation. We will use Jasmine’s it block to set up and test the status code that our server returned: 


```
describe("Hello World Server", function() {
  describe("GET /", function() {
    it("returns status code 200", function() {

    });
  });
});
```


Next`,`we will use the request package to send a GET request toward our web server. We can load the package with the required keyword in Node.js, and to execute a request, we need to pass it a URL and a function that it will invoke once the request is returned.


```
var request = require("request");

var base_url = "http://localhost:3000/"

describe("Hello World Server", function() {
  describe("GET /", function() {
    it("returns status code 200", function() {
      request.get(base_url, function(error, response, body) {

      });
    });
  });
});
```


Finally, we can now write our first expectation. Jasmine implements expectations with the expect() function that tests if a tested object _matches_ some of the expected conditions. For example, the following expect will match the value of the response.status to the number 200, with the .toBe matcher. Of course, there are so many more [matchers](https://jasmine.github.io/2.0/introduction.html#section-Included_Matchers).


# Further Reading

[https://jasmine.github.io/pages/getting_started.html](https://jasmine.github.io/pages/getting_started.html)

[https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-jasmine](https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-jasmine)

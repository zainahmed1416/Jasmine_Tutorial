<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 0.651 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Mon Nov 02 2020 16:44:32 GMT-0800 (PST)
* Source doc: Jasmine Tutorial

WARNING:
You have 6 H1 headings. You may want to use the "H1 -> H2" option to demote all headings by one level.

----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 0.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p>
<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>



# Jasmine Tutorial


# Introduction

Jasmine is a testing framework for Javascript that runs for Node.js or standalone in a browser. It is quite robust and flexible, compatible with all javascript-enabled frameworks. It aims to be non-intrusive on your IDE/application while having an easy to read and understand syntax. It is influenced by many other JavaScript unit testing frameworks.


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


# Code Walkthrough


# Further Reading

[https://jasmine.github.io/pages/getting_started.html](https://jasmine.github.io/pages/getting_started.html)

[https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-jasmine](https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-jasmine)

# Blog Post

By Jean Paul Ruiz :smiley_cat: <jpruiz114@gmail.com>

Live links:

Not indicating the language and the post id will load the post 1 and will detect the language from the browser:

:link: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/

Not indicating the language but indicating the id will load the given post with the browser language:

:link: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/1

:link: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/2

:link: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/3

Not indicating the post id but the language will load the post 1 with the given language:

:us: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/en/

:es: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/es/

Indicating the language and the post id will load the given post with the given language:

:us: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/en/1

:us: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/en/2

:us: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/en/3

:es: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/es/1

:es: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/es/2

:es: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/es/3

A post that doesn't exist will give a default message. For example:

:link: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/1234

:us: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/en/1234

:es: http://jeanpaulruizvallejo.com/frontend-test/BlogPost/es/1234

If a non supported language is provided, english will be used as default.

The multi language feature here can be seen in the error message for a non existing post and in the anchor titles.

The comment button has an active click handlers but isn't doing much.

The follow button and the like button, both of them have click handlers and a class toggle is made to show active state.

## Dependency Handling

* [Bower](http://bower.io/) for the frontend libraries

### Some considerations for Bower

To install Bower, if you don't have it
`tasks\bower\install.sh`

#### Instructions with Bower

To list the project frontend dependencies
`tasks\bower\list-dependencies.sh`

To install the frontend dependencies
`tasks\bower\update-dependencies.sh`

With the .bowerrc file we setup the folder where you want to hold the frontend dependencies.

* The folder **components** had to be added to the repo so the deployment on the server side could have the dependencies.

## Build & Validation Automation with Grunt

:bulb: Install the command line interface for Grunt
`npm install -g grunt-cli`

:bulb: Install the latest version of Grunt in your project folder
`npm install grunt --save-dev`

:bulb: Install the **grunt-contrib-sass** package
`npm install grunt-contrib-sass --save-dev`

:bulb: Install the **grunt-jsonlint** package
`npm install grunt-jsonlint --save-dev`

:bulb: Install the **grunt-jsvalidate** package
`npm install grunt-jsvalidate --save-dev`

:bulb: Install the **grunt-remove-logging** package
`npm install grunt-remove-logging --save-dev`

:bulb: Install the **load-grunt-tasks** package
`npm install load-grunt-tasks --save-dev`

* Notice that the **node_modules** folder was excluded from the repository in the **.gitignore** file.

## Karma and Mocha Testing

### Karma

http://karma-runner.github.io/

:octocat: https://github.com/karma-runner/karma

Karma is a test runner. Karma uses your test framework to run tests in several environments of your choice.

"On the AngularJS team, we rely on testing and we always seek better tools to make our life easier. That's why we created Karma - a test runner that fits all our needs."

### Mocha

http://mochajs.org/

:octocat: https://github.com/mochajs/mocha

Mocha is our framework of choice that takes care of running our test suites.

### Chai

http://chaijs.com/

:octocat: https://github.com/chaijs/chai

Chai adds syntactic sugar to your assertions, some utility functions, as well as a plugin interface for any necessary tweaks you might want to build.

It is framework agnostic, so you don’t need to use it with Mocha specifically.

Inside the **example.test.js** file, you can see an example:

`expect(true).to.be.false;`

Instead of saying something like assert.equal(2 - 1, 1), you can write your assertions like, expect(2 - 1).to.equal(1).

http://chaijs.com/guide/styles/#should
http://chaijs.com/guide/styles/#expect
http://chaijs.com/guide/styles/#assert

### Sinon

Sinon is another essential part of our toolbox that provides spies, stubs, mocks, and a few additional useful functions for testing:

#### Spies

Spies are functions that record how many times they have been called and with what arguments.

These are especially useful when testing callbacks.

#### Stubs

Stubs are like spies but with pre-programmed behavior.

Unlike wrapping a function with a spy, when you wrap a function with a stub, that original function is not called.

This can be useful for faking AJAX requests where you might not want the actual request to go out.

Some valid use cases for stubs are altering flow control or testing a branch of your function that throws an error.

#### Mocks

Mocks are similar to stubs because they inherit the spy API and discard the original function implementation.

In addition to pre-programmed behavior there are expectations – you will tell the mock to what to expect and verify, usually before any of the test code is written.

### Dependencies

#### Command Line Interface

:bulb: Install the command line interface for Karma
`npm install -g karma-cli`

#### Packages

:bulb: Install the **chai** package
`npm install chai --save-dev`

:bulb: Install the **grunt-karma** package
`npm install grunt-karma --save-dev`

:bulb: Install the **karma** package
`npm install karma --save-dev`

:bulb: Install the **karma-chai** package
`npm install karma-chai --save-dev`

:bulb: Install the **karma-firefox-launcher** package
`npm install karma-firefox-launcher --save-dev`

:bulb: Install the **karma-mocha** package
`npm install karma-mocha --save-dev`

:bulb: Install the **karma-phantomjs-launcher** package
`npm install karma-phantomjs-launcher --save-dev`

:bulb: Install the **karma-sinon** package
`npm install karma-sinon --save-dev`

:bulb: Install the **karma-verbose-reporter** package
`npm install karma-verbose-reporter --save-dev`

:bulb: Install the **mocha** package
`npm install mocha --save-dev`

:bulb: Install the **phantomjs** package
`npm install phantomjs --save-dev`

:bulb: Install the **sinon** package
`npm install sinon --save-dev`

To check that Karma is installed:

`karma --version`

To init Karma:

`karma init`

That should create the karma.conf.js Setup the config file. Then write a test.

To run Karma:

`karma start`

**Some useful links**

https://sean.is/writing/client-side-testing-with-mocha-and-karma/

http://karma-runner.github.io/0.13/config/browsers.html

* Notice that the **node_modules** folder was excluded from the repository in the **.gitignore** file.

## Multi language support

In order to support multiple languages, in this case english and spanish, the i18n library was used.

http://i18next.com/

:octocat: https://github.com/i18next/i18next

## Styles Considerations

For the styles [SMACSS](https://smacss.com/book/type-layout) guideline is used.

BEM could have been used but SMACSS has proven (In my case) to facilitate modularity and re - usability.

## Languages Considerations

navigator.language value should be found in the ISO 639-1:

https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes

## Automation

In order to save time, a shell script named **push-and-deploy.sh** was created.

This script calls **Grunt** and pushes the changes to the GitHub repo.

The repo was setup so after every push to the master branch, a web hook is called that performs an automatic deployment on the server side.

**Grunt**, as listed above, uses several tasks to automate:

* Validating the json files.
* Validating the JavaScript files.
* Removing the logging from JavaScript (console.log() calls that developers use).
* Compiling the sass files into css files.

Inside the **tasks** folder other shell scripts can be found.

There are several shell scripts for:

* Bower
* git
* Karma

The shell scripts for **Bower** allow to:

* Install Bower
* List the current dependencies
* Install & update dependencies

The shell scripts for **git** allow to:

* Push the current changes to the repo with a custom or generic comment.

The shell scripts for **Karma** allow to:

* Run the unit tests of the module.

## Accessibility Evaluation

### Color Blindness Simulation

Tool used

http://www.vischeck.com/vischeck/

Image processor

http://www.vischeck.com/vischeck/vischeckImage.php

#### Scenarios Covered

* Deuteranope (a form of red/green color deficit)
* Protanope (another form of red/green color deficit)
* Tritanope (a blue/yellow deficit - very rare)

#### Color Blind Simulation for Post

**Original image**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis/original-image.jpg)

**Deuteranope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis/deuteranope-simulation.jpg)

**Protanope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis/protanope-simulation.jpg)

**Tritanope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis/tritanope-simulation.jpg)

#### Color Blind Simulation for Post with Active Buttons

**Original image**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis-active-buttons/original-image.jpg)

**Deuteranope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis-active-buttons/deuteranope-simulation.jpg)

**Protanope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis-active-buttons/protanope-simulation.jpg)

**Tritanope**

![Original image](https://github.com/jpruiz114/widgets/blob/master/BlogPost/assets/images/shots/color-blindness-analysis-active-buttons/tritanope-simulation.jpg)

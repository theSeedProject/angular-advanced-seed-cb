angular-advanced-seed-yo
========================

# Description
An angular seed for medium to large web applications.
The base was generated using the yeoman angular generator.

The purpose of this seed is to make it easy to start of angular projects in a proper workflow.


# Distributing the workflow
In case you want to use this workflow or distibute it to colleagues follow the following steps.

## Prerequisits
These are dependencies of which you probably already have most installed.

1. Node, Git and Ruby installed
2. $ npm install -g grunt-cli && npm install -g bower
3. $ (gem install sass) && gem install compass

## Kickstart your project
When you have successfully installed the prerequisits.

1. (optionally fork first) Clone repo && cd into folder
2. $ npm install && bower install
3. grunt serve
4. start coding


# Initial Setup
To setup this repo I went through the following steps

## Prerequisits
Before you start make sure your username does not contain accented latin characters.

1. Node installed
2. Git installed
3. $ npm install -g grunt-cli
4. $ npm install -g yo
5. $ npm install -g bower
6. Ruby installed
7. $ gem install sass 
  If any problems with a certificate download the gem via http.
  Set the source to try on http if https fails by the following command
  - $ gem sources --add http://rubygems.org 
8. $ gem install compass

## Installation
1. $ npm install -g generator-angular
2. $ mkdir \<folderName\> && cd $_
3. $ yo angular \<appName\>
  - Sass? Y
  - Twitter Bootstrap? n
  - Choose Angular modules
4. $ bower install bootstrap-css-only --save
5. $ bower install font-awesome --save

## Verifing installation
1. Check or folders are created
2. Check or basic grunt commands run
  - $ grunt 
  - $ grunt test
3. Run the grunt server ( $ grunt serve )

## Installing further components and modules
1. $ bower install font-awesome --save 
2. [x] Installing angular bootstrap
  - $ bower install angular-bootstrap --save
  - if you have any problems just go to http://angular-ui.github.io/bootstrap/ and download it from there
3. $ npm install grunt-remove-logging --save-dev 
  --save-dev saves it as a development dependency
  

## Speeding up Compass compilation
Compass is a great library but the compilation it does within grunt is very slow. With the original setup it took about 4.7 seconds before livereload was triggered by the browser after compiling sass to css. After going through the following steps the reload triggers in under 20ms.

1. Create a concurrent task to do the watch see Gruntfile.js at the concurrent.watch task. Be sure to set enable logging as in the example
2. Update Compass.watch to set option 'watch' to true. This enables the native Compass watch function
3. Add the concurrent.server to the serve task.

## Further Adjustments
To make this repo fit as a seed for medium to large scale apps I decided to make more changes. If you just want to get started with Yeoman and Angular your journey ends here. I you want to use this seed project as is you can follow the instructions in the 'Distributing Workflow' section. I have implemented the following changes:

1. [x] Restructured the app after the component-grouped paradigm
2. [ ] Updating all the grunt tasks to work again
  - [x] setting up new structure
  - [x] watching for file changes 
  - [x] compiling sass
  - [x] unit tests
  - [x] copy templates to distribution folder
  - [x] cleaning up old files and paths
  - [x] css does not get minified and copied from the 
  - [x] fixing javascript minification
  - [x] filerev css files
  - [x] minify all views
  - [x] distribution
  - [ ] Task cdn-ify stopped working.
  - [x] test if the project can be served from the dist folder
3. [x] Switched to ui-router:
  - $ bower uninstall angular-router --save
  - $ bower install ui-router --save
  - rewrote the router code


# Future
1. research or templates could be concatenated as well as now each template is an http request

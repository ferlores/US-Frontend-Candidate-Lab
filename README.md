## CP+B Candidate Lab

Hello and thank you for taking the time to work on this lab!

This lab is an opportunity for us to have a conversation about practices, conventions, and workflow.
It will also help us better understand you as a developer.
Please use this as a way to communicate through your craft.


# Setup

1. Fork this repo and clone to your computer
2. Setup the project in your preferred IDE
3. View index.html in the browser (/www)
4. Open the psd file in /psd (/psd)


# Development

* Improve semantic structure and content of the HTML
* Incorporate missing design elements (per psd)
* Create an RSVP message onClick of 'Yes' or 'No':
  ** Provide feedback to the user with confirmation of their choice
  ** Design, behavior, and messaging are up to you
  ** Plug-ins, libraries, and frameworks are permitted
* Modify anything and everything you think should be different/improved. Document the reasoning for your changes in the Notes section.


# Workflow

Please make atomic commits (commit often) as you progress.
Be sure to provide useful commit messages to illustrate milestones and workflow.
Submit a pull request when you are finished and satisfied with your work.

# Notes

Use this area to communicate any thought processes, ideas, or challenges you encountered.

## Improve semantic structure and content of the HTML + CSS
* Decided not to add support for rounded borders for < IE9 because it is only required for the buttons
* Added favicon apple-icon-touch from polaroid web site

## Incorporate missing design elements (per psd)
* Added the two missing pics. Exported as png to get the transparency for responsive (different width)
* Added box-shadow for the invitation

##Responsive Design
* Use of media-queries to re-arrange UI elements for mobile devices

##FrontEnd Architecture
* The site has been designed around the concept of progressive enhancement.
* If a user doesn't have JavaScript enabled then she can still use it.
* The RSVP message is either generated on the backend if JavaScript has been disabled or on the frontend if JavaScript is enabled.
* We chose Backbone.js in order to have a basic separation of concerns in the JavaScript code. The user interaction with the RSVP form is handled by a Backbone view called RsvpView. A Backbone model, named RsvpModel, has been implemented to communicate frontend and backend. A Backbone router creates both instances.
* Both scripts reside in its own module, which is a directory in the filesystem. This is the baseline organization we use when working with big applications that need to be modular in order to be maintainable. More complex application require more infrastructure code in order to deal with concerns such as: views life-cycle, application bootstraping, widgets reusability, widgets or views inter-communication, etc
* RequireJS, and its AMD format, is used to declare modules and dependencies among them. As a consequence, JavaScript objects do not pollute the global namespacing, development is modular, and by using RequireJS's optmizer we are able to generate a script bundle.
* ToDo: creation of unit test for backbone views, and models.

##NodeJS Backend
* The backend is a simple 60-liner script that uses Express and Handlebars. This express application exposes two endpoint: the default "/" one, and a second one named "/rsvp". The first endpoint serves the initial rsvp page. The second endpoint is used by the frontend to process the rsvp response. Two kinds of response can be generated by the endpoint. If the user has JavaScript disabled, then the form action will send a request with a x-www-form-urlencoded header, in this case we use Handlebars to generate the response. If JavaScript is enabled then the AJAX call generates an "application/json" request, which is then answered with the same content-type.
* A modular approach shall be used for production-ready sites. The implemented express application is just for demo purposes.

##Build System
* Grunt has been used to automate the build system. Two build profiles has been defined: build:dev, and build:prod. The main difference reside in build:dev not concatenating, minifying JavaScript files, and not optimizing image files. JavaScript files are concatenated by RequireJS, and minified by Uglify. Image files are optimized by imagemin, which in turn uses ImageOptim to optimize png, and jpegtran among other optimization. In addition, there are two linters to enforce code quality and adherence to standards: jshint to check JavaScript scripts, and csslint to check CSS files.



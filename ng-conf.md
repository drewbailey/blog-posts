## Up and running with Angular 2 and the Angular-CLI

There has been a lot of talk about Angular 2 and all the new features and tooling it brings. Whether you are interested in playing around with the new framework to see what its all about or are getting ready to use it for your next production application, setting up something new is never a task I look forward to. Luckily, the [Angular-CLI](https://cli.angular.io/) makes it a breeze to get up and running with the latest and greatest angular has to offer.

The Angular-CLI is a command line interface that is based off of the ember-cli project. It provides extremely useful commands to help you rapidly build new angular applications and can even deploy your application for you using github pages or firebase. In this post I will walk you through some of the features the tool has to offer, and then we will create and deploy a simple application to github pages. Mike Brocchi did a really great talk at ng-conf 2016 which you can find [here](https://youtu.be/wHZe6gGI5RY).

### Install the CLI
Getting started with the angular-cli is easy, to install just enter the following command.

```bash
npm install -g angular-cli
```
Next, simply call `ng new` plus a name for your application and the cli will automatically scaffold you a new angular 2 project!
```bash
ng new my-app
```

At this point in time you would generally have to configure something like Grunt or Gulp to build your app. Thanks to the angular-cli you can now just run `ng build` and everything is taken care of for you!


~~~~~~~~~ TODO ~~~~~~~~~~~
```
ng build
ng test
ng e2e
ng serve
ng deploy - to github pages
```
ng generate component my-comp
ng generate directrive|pipe|service|route|class
https://cli.angular.io/reference.pdf

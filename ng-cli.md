## The Rise of Javascript CLIs

You are a developer who wants to evaluate a Javascript framework. Your time is important to you so the last thing you want to do is get stuck setting up your project directory and build configuration. All you care about is the code and features the framework provides you, so why waste time worrying about configuration and and what packages to include for your project? 

Thankfully, many popular frameworks such as [Ember.js](http://emberjs.com/), [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) all provide ways to quickly start building applications, no configuration required. It's important to note there are also plenty of code generator tools out there, namely [Yeoman](http://yeoman.io/) but many new developers are unaware or unsure of how to start using third party tools which is why its great to see Angular and React follow Ember's footsteps in implementing CLIs by the same team that implented the frameworks themselves. In this post we'll look at some of the time saving features provided by Angular and React to help developers quickly get apps up and running.

## The Case for CLIs

As of writing this (August 2016) The first section of the [Angular Quickstart](https://angular.io/docs/ts/latest/quickstart.html) is all about setup. To a seasoned developer most of this can be easily glossed over but to a new comer it can easily be quite daunting, the guide asks readers to create a project folder, add a package.json and a few other configuration files and install your dependencies. Let's look at the first file we are asked to create, `package.json`.

```json
// Taken from https://angular.io/docs/ts/latest/quickstart.html
{
  "name": "angular2-quickstart",
  "version": "1.0.0",
  "scripts": {
    "start": "tsc && concurrently \"npm run tsc:w\" \"npm run lite\" ",
    "lite": "lite-server",
    "postinstall": "typings install",
    "tsc": "tsc",
    "tsc:w": "tsc -w",
    "typings": "typings"
  },
  "license": "ISC",
  "dependencies": {
    "@angular/common": "2.0.0-rc.5",
    "@angular/compiler": "2.0.0-rc.5",
    "@angular/compiler-cli": "0.5.0",
    "@angular/core": "2.0.0-rc.5",
    "@angular/forms": "0.3.0",
    "@angular/http": "2.0.0-rc.5",
    "@angular/platform-browser": "2.0.0-rc.5",
    "@angular/platform-browser-dynamic": "2.0.0-rc.5",
    "@angular/router": "3.0.0-rc.1",
    "@angular/upgrade": "2.0.0-rc.5",
    "core-js": "^2.4.0",
    "reflect-metadata": "^0.1.3",
    "rxjs": "5.0.0-beta.6",
    "systemjs": "0.19.27",
    "zone.js": "^0.6.12",
    "angular2-in-memory-web-api": "0.0.17",
    "bootstrap": "^3.3.6"
  },
  "devDependencies": {
    "concurrently": "^2.2.0",
    "lite-server": "^2.2.2",
    "typescript": "^1.8.10",
    "typings":"^1.3.2"
  }
}
```

It's not hard to imagine how confused the reader might get looking into what `"tsc && concurrently \"npm run tsc:w\" \"npm run lite\" "` is trying to do, and the guide isn't trying to get readers to look into it, they just want you to copy and paste the file. So what is gained by a new comer for this inital set up? Have they learned anything about Angular? Maybe they understand some of the dependencies or the need to transpile TypeScript into Javascript but not much about the framework itself is gained.

What if instead the user could just run `npm install -g angular-cli` and then `ng new hello-world`? Thanks to the Angular-Cli, the inital set up and configuration of an angular application has abstracted away the inital complexity of setting up and configuring a project and made it a breeze for someone to get started with Angular. In my mind a fantasic trend for Javascript frameworks. Many other languages/frameworks like Rails have been using generators for ages, and shifting users to follow convention over configuration is an awesome trend to get developers developing instead of worrying about configuration until they really need.


React implented their own CLI tool with their newly release [Create React App](https://github.com/facebookincubator/create-react-app).

![React Landing Page](/images/react-app-2.gif?width)



## Version 2 Proposed edits
- The rise of Popular Javascript frameworks moving towards convention over configuration
- Many JS frameworks out there, a lot of tutorials have initial focus on setting up build processes, this can tend to scare off new users who really just want to learn the framework and start coding.
- Beginnings - Ember CLI (non js projects like rails generators)
- The Rise of Angular 2 and React, NG-CONF angular 2 announces ng-cli tool to build, run, and deploy Angular 2 applications with 0 configuration needed.
- The newly annouced create-react-app follows a very similar approach.
- Benefits of using cli tools that guide users to follow convention over configuration, start building things instead of spending a bunch of time setting up your application and build process.
- 


I also highly reccomend looking at Mike Brocchi's talk from ng-conf 2016 which you can find [here](https://youtu.be/wHZe6gGI5RY). Now lets dive in.


### Deploy our Application
So far we have seen how the Angular-CLI can create and run our application locally, but what if we want to deploy it? The Angular-CLI provides us a way to quickly allow others to see our application by using [github pages](https://pages.github.com/). To deploy our application we just need to simply run a single command, `ng github-pages:deploy` and our app will be live on github! Below is the output and instructions provided by the tool.

```bash
Built project successfully. Stored in "dist/".

In order to deploy this project via GitHub Pages, we must first create a repository for it.
It's safer to use a token than to use a password, so you will need to create one.

Go to the following page and click 'Generate new token'.
https://github.com/settings/tokens

Choose 'public_repo' as scope and then click 'Generate token'.

? Please enter GitHub token you just created (used only once to create the repo): [token]
? and your GitHub user name: drewbailey
Deployed! Visit https://drewbailey.github.io/my-todo-app/
Github pages might take a few minutes to show the deployed site.
```

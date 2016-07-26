## The Rise of Javascript CLIs

You are a developer who wants to evaluate a Javascript framework to see if it is going to work for your project. Your time is important to you so the last thing you want to do is try to decide which build tools to use or which packages to include in your project. That's not what is immediately important to you, the actual code itself and the features the framework provides you is what you care about, so why waste time configuring your project?

As of writing this (July 2016) The first section of the [Angular Quickstart](https://angular.io/docs/ts/latest/quickstart.html) is all about setup. It asks readers to create a project folder (easy enough), add a package definition on configuration files and install packages. Let's look at the first file we are asked to create, `package.json`.

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
    "@angular/common": "2.0.0-rc.4",
    "@angular/compiler": "2.0.0-rc.4",
    "@angular/core": "2.0.0-rc.4",
    "@angular/forms": "0.2.0",
    "@angular/http": "2.0.0-rc.4",
    "@angular/platform-browser": "2.0.0-rc.4",
    "@angular/platform-browser-dynamic": "2.0.0-rc.4",
    "@angular/router": "3.0.0-beta.1",
    "@angular/router-deprecated": "2.0.0-rc.2",
    "@angular/upgrade": "2.0.0-rc.4",
    "systemjs": "0.19.27",
    "core-js": "^2.4.0",
    "reflect-metadata": "^0.1.3",
    "rxjs": "5.0.0-beta.6",
    "zone.js": "^0.6.12",
    "angular2-in-memory-web-api": "0.0.14",
    "bootstrap": "^3.3.6"
  },
  "devDependencies": {
    "concurrently": "^2.0.0",
    "lite-server": "^2.2.0",
    "typescript": "^1.8.10",
    "typings":"^1.0.4"
  }
}

```

If I am new to Javascript or coming from a project where I simply including JQuery into my HTML this can look very intimidating. What did I just blindly copy? What does this have to do with Angular and why do I also need a `tsconfig.json, typings.json and systemjs.config.js` file? Sure these are probably things I will become familiar with over time, but is it absolutely necessary to deal with them right now? 

These are questions I found myself asking the internet and it turns out the answer is no! Both Angular and React have recently implemented ways to quickly get up and running with their frameworks as painlessly as possible. For the rest of this article I'm going to show just how easy it is to get up and running with an Angular application as well as a React application using their CLI tools to help up scaffold a new application.

## Angular
The [Angular-CLI](https://cli.angular.io/) was announced just in time for this years NG-Conf back in May. Mike Brocchi had a great talk about the new project at this years NG-Conf which you can find [here](https://youtu.be/wHZe6gGI5RY). Now lets dive in and build a new Angular applicaiton.

### Install the CLI
Getting started with the angular-cli is easy, to install just run the following command.

```bash
npm install -g angular-cli
```

Next, simply call `ng new` plus a name for your application and the cli will automatically scaffold you a new angular 2 project and install all of your dependencies!
```bash
ng new my-todo-app
```
Angular just created a lot of files for us, most of which we can ignore for now but the `src` directory is the only thing we will be looking at.
```
my-todo-app/src
├── app
│   ├── app.component.css
│   ├── app.component.html
│   ├── app.component.spec.ts
│   ├── app.component.ts
│   ├── environment.ts
│   ├── index.ts
│   └── shared
│       └── index.ts
├── favicon.ico
├── index.html
├── main.ts
├── system-config.ts
├── tsconfig.json
└── typings.d.ts
```

Lets take a look at `app.component.ts`. Granted not much is going on here but let's try running our project and see what happens

```ts
import { Component } from '@angular/core';

@Component({
  moduleId: module.id,
  selector: 'app-root',
  templateUrl: 'app.component.html',
  styleUrls: ['app.component.css']
})
export class AppComponent {
  title = 'app works!';
}
```

We have our base application, now what? Lets run it and see what happens. running `ng serve` will build and run your application locally. You should see something similar to the following output.

![ng serve screenshot](/images/blog-post-todo-02.jpg)

And if we open our browser to http://localhost:4200/ we see the following, our application is up and running with minimal effort!

![app running locally](/images/blog-post-todo-01.jpg)

It's pretty easy to see how this tool can save us time and help users not get scared off by configuration and this is only the tip of the iceburg for all the functionality that the tool provides us, but before we get too far into that lets take a look at Reacts new tool and see how quickly we can get up and running.


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

## Up and running with Angular 2 and the Angular-CLI

There has been a lot of talk about Angular 2 and all the new features and tooling it brings. Whether you are interested in playing around with the new framework to see what its all about or are getting ready to use it for your next production application, setting up something new is never a task I look forward to, until now. 

The Angular team understands getting into a new framework is hard, thats one of the reasons why they decided to create the [Angular-CLI](https://cli.angular.io/). The Angular Command Line Interface makes it a breeze to get up and running with the latest and greatest angular has to offer, it even lets you deploy your application to github pages! In the rest of this post we will go over a lot of the features the Angular-CLI has to offer and deploy or application to github.

I also highly reccomend looking at Mike Brocchi's talk from ng-conf 2016 which you can find [here](https://youtu.be/wHZe6gGI5RY). Now lets dive in.

### Install the CLI
Getting started with the angular-cli is easy, to install just enter the following command.

```bash
npm install -g angular-cli
```
Next, simply call `ng new` plus a name for your application and the cli will automatically scaffold you a new angular 2 project!
```bash
ng new my-todo-app
```

We have our base application, now what? Lets run it and see what happens. running `ng serve` will build and run your application locally. You should see something similar to the following output.

![ng serve screenshot](/images/blog-post-todo-02.jpg)

You will notice it says `Livereload server on http://localhost:49154`, This is because ng is running BrowserSync for us to watch for file changes. This means that we don't need to restart our server whenever we make changes to our app.

And if we open our browser to http://localhost:4200/ we see the following, our application is up and running with minimal effort!

![app running locally](/images/blog-post-todo-01.jpg)


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

That is it! The app is now deployed on github. It is easy to see how great this tool can be for quickly building prototypes and having them deployed somewhere for others to view. Now that we have a grasp on the creation and deployment aspects of the cli, lets look at a few other commands it provides and make our app a little more useful.

### Generators
We can generate a new component by invoking `ng g component` (generate is synonmyous with `g`). Angular has decided to use a specific naming convention in Angular 2. Components will have name.component.ts so when naming your components using the cli don't include component or else you will end up with my-component.component.ts.

![component generation](/images/blog-post-todo-04.jpg)


~~~~~~~~~ TODO ~~~~~~~~~~~
### Other commands
Below are some of the available commands Angular-CLI has to offer, the project is still currently in beta and I'm sure new features will be rolling out so make sure to keep an eye on the [repo](https://github.com/angular/angular-cli).
```
ng build
ng test - runs unit tests, using karma
ng e2e - runs end-to-end tests using protractor.
ng serve
ng deploy - to github pages
ng completion - outputs shell script to add to your .bashrc or .zshrc for autocompletion when using ng commands
ng init - creates a new angular folder in the current directory
ng doc [keyword] - opens browser tab to documentation page of keyword
ng lint - runs the codelyzer linter against your project
```
[reference pdf](https://cli.angular.io/reference.pdf)

ng generate component my-comp
ng generate directrive|pipe|service|route|class


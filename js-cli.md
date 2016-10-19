## React vs Angular vs Vue, A look at modern javascript framework CLIs

The rapid growth of javascript over the past few years has lead to a large variety of build tools and configuration options to get a simple application off the ground and running. This has been a [complaint](https://hackernoon.com/how-it-feels-to-learn-javascript-in-2016-d3a717dd577f) the JS community has been [suffering](https://medium.com/@ericclemmons/javascript-fatigue-48d4011b6fc4) for some time, which some refer to as JavaScript fatigue. Thankfully many popular frameworks are listening. 

Projects such as [Angular](https://cli.angular.io/) and [React](https://github.com/facebookincubator/create-react-app) and [Vue](https://github.com/vuejs/vue-cli) all provide command line interfaces (CLIs) to quickly start building applications, no configuration required. In this post we'll look at some of the time saving features provided by these tools to help developers quickly get apps up and running.

## Creating Your Application
Creating an application in Angular, React or Vue is a breeze thanks to their cli. In this section we will take a quick look at how easy it is to scaffold a new application each framework.

### Angular
```js
npm install -g angular-cli
ng new my-app
cd my-app
ng serve
** NG Live Development Server is running on http://localhost:4200. **
```
![Angular Landing Page](images/blog-post-todo-01.jpg)

### React
```js
npm install -g create-react-app
create-react-app my-app
cd my-app
npm start
```

### Vue
```js
npm install -g vue-cli

```

## Angular and React CLIs at a glance

As of writing this (October 2016) The first section of the [Angular Quickstart](https://angular.io/docs/ts/latest/quickstart.html) is all about setup. To a seasoned developer most of this can be easily glossed over and copy and pasted, but to a new comer it can easily be daunting, the guide asks readers to create a project folder, add a package.json and a few other configuration files and install your dependencies. Let's look at the first file we are asked to create, `package.json`.

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

What if instead the user could just run `npm install -g angular-cli` then `ng new hello-world` and then finally `ng serve` and have an application up and running in a matter of no time. Thanks to the [Angular-Cli](https://cli.angular.io/), the inital set up and configuration of an angular application has abstracted away the inital complexity of setting up and configuring a project and made it a breeze for someone to get started with Angular.

React has recently released their own cli tool called [Create React App](https://github.com/facebookincubator/create-react-app). The React cli follows in a similar path to get up and running with the same simple simplicity of running `npm install -g create-react-app` followed by `create-react-app hello-world` and that is it! React even gets the user excited about its framework by including a nice splash page when the application is first run locally by running `npm start`

![React Landing Page](/images/react-app-2.gif?width)

In my mind this is a fantasic trend for Javascript frameworks. Many other languages/frameworks like Rails have been using generators for ages, and shifting users to follow convention over configuration is a great way to get developers developing instead of worrying about configuration until they really need it.

If you are interested in learning more about the Angular-CLI Ihighly reccomend looking at Mike Brocchi's talk from ng-conf 2016 which you can find [here](https://youtu.be/wHZe6gGI5RY). The [github repo](https://github.com/angular/angular-cli) for the project also has a lot of good information, be sure to start star it so you can watch it evolve has the framework matures!

Additional info for the Create React App can be found on their [github page](https://github.com/facebookincubator/create-react-app). The [blog post](https://facebook.github.io/react/blog/2016/07/22/create-apps-with-no-configuration.html) which introduced the cli also has some good background explainging the need for a simiplier way to introduce users into javascript frameworks.


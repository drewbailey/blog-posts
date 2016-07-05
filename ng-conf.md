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
ng new my-todo-app
```

We have our base application, now what? Lets run it and see what happens. running `ng serve` will build and run your application locally. You should see something similar to the following output.
![ng serve screenshot](/images/blog-post-todo-02.jpg)

And if we open our browser to http://localhost:4200/ we see the following, our application is up and running with minimal effort!
![app running locally](/images/blog-post-todo-01.jpg)


### Deploy our Application
So far we have seen how the Angular-CLI can create and run our application locally, but what if we want to deploy it? The Angular-CLI provides us a way to quickly allow others to see our application by using [github pages](https://pages.github.com/). To deploy our application we just need to simply run

```bash
ng github-pages:deploy

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
And that is it! The app is now deployed on github. It is easy to see how great this tool can be for quickly building prototypes and having them deployed somewhere for others to view. Now that we have a grasp on the fundamentals of the cli, lets look at a few other commands it provides and make our app a little more useful.


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

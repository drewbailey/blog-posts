## Up and running with Angular 2 and the Angular-CLI

There has been a lot of talk about Angular 2 and all the new features it brings. Whether you are interested in playing around with the new framework to see what its all about or are getting ready to use it for your next application, setting up something new is never something people look forward to. Luckily, the [angular-cli](https://cli.angular.io/) makes it a breeze to get up and running with the latest and greatest angular has to offer.


- Brief intro to Angular 2, maybe some type script
- Tooling
- Scaffolding thanks to angular-cli

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

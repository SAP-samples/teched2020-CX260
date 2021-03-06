# Exercise 1 - Setup Spartacus

In this exercise, you will setup Spartacus on your local system.

**TLTR:** The exercise can be done with a few quick commands. If you're comfortable with Angular development, you can pass this exercise using the following commands and you'd be up and running within a minute.

```
ng new sample-storefront --routing=false --style=scss
cd sample-storefront
ng add @spartacus/schematics@next \
  --baseUrl=https://spartacus-demo.eastus.cloudapp.azure.com:8443 \
  --baseSite=electronics-spa
```

If you like to better understand these commands, you can go through the sub exercises below.

---

**NOTE on Angular 11**

Spartacus 3.0 supports Angular 10. However, Angular 11 was lately released, and so far there are no known issues with Spartacus 3.0 on Angular 11. To be on the safe side, you should use angular 10.

---

## Exercise 1.1 Confirm prerequisites

If you went through the [prerequisites](../../prerequisites.md) already you can skip this exercise and start exercise 1.2.

Ensure that you have the prerequisites in place by the validating the following commands in a terminal:

- Run `node --version` to confirm the Node.js version on your local system. The version should be between `10.14.1` and `13`. Later version might work, but are not actively tested.
- Run `ng --version` to confirm the Angular CLI version. Spartacus 3.x supports Angular 10.

## Exercise 1.2 Create Angular application

Spartacus is distributed as a set of npm packages, that you can add to an angular application. Creating an Angular application is easily done with the [Angular CLI](https://cli.angular.io/). You can run the following command in a terminal to generate a new Angular application

```shell
ng new sample-storefront --routing=false --style=scss
```

This creates a new Angular application, called "sample-storefront", without routing and using the SCSS style syntax.

You can run the newly created application by executing `ng serve` in the terminal. You should run this inside the newly created application folder, so you probably need to run `cd sample-storefront` upfront.
The dev server starts by default on port 4200; You can open the application, using: http://localhost:4200.

---

**Note**: The newly generated application initializes a git repo, which allows you to track changes while you're building out the exercises in this workshop. It is recommended to commit your changes after each exercise, so that you can roll back easily as well as clearly see what you've done.

---

## Exercise 1.3 Install Spartacus

Once you have generated you Angular application, you can add Spartacus to it. You could add dependencies using `yarn add`, however the amount of direct and indirect packages can be cumbersome to add. Therefor Spartacus provides an _installer_ process that simplifies the installation. The installer is based on [Angular schematics](https://angular.io/guide/schematics) and can be added by the `ng add` command.

To simplify the default configuration of spartacus even more, we're adding few more parameters.

```shell
ng add @spartacus/schematics@next \
  --baseUrl=https://spartacus-demo.eastus.cloudapp.azure.com:8443 \
  --baseSite=electronics-spa
```

**Note**: the backslash is only used to make the command better readable. It will be ignored when you paste it in you terminal.

This command will do the following:

- Adds Spartacus direct and indirect dependencies to the `package.json` file.
- Install the dependencies.
- Configures Spartacus application by providing a configuration in the `app.module`.

You might want to commit your changes to the local git repo so that you keep track of the changes going forward. You don't need to publish your commits, but having a local commit history is going to be very helpful while you work yourself through the material.

## Exercise 1.4 Run Spartacus

You can run your local Spartacus application, using the following command:

```shell
ng serve
```

This command will run the angular dev server.

Once the application is started, you can launch it in the browser: [http//:localhost:4200](http//:localhost:4200).

Moreover, you can start developing your application without restarting the server. The changes will be _hot deployed_ and your browser will auto refresh so that you can quickly evaluate the changes.

---

**NOTE**

If you happen to see a blank page, you probably need to accept the _insecure_ backend (https://spartacus-demo.eastus.cloudapp.azure.com:8443/occ/v2). The backend that we offer in this exercise doesn't come with a SSL certificate, which is why the browser will block this request. The easiest to do is to open [a random request](https://spartacus-demo.eastus.cloudapp.azure.com:8443/occ/v2/basesites) in another browser tab, and accept the insecure communication. After this you can refresh the Spartacus application in the browser.

---

## Summary

You've now installed Spartacus locally. If you run the storefront in [http//:localhost:4200](http//:localhost:4200) you should see the _electronics_ storefront content.

Continue to [Exercise 2 - Implement Product Comparison Selection](../exercise-2/README.md)

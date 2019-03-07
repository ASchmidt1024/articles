# Angular Evaluation

Why take [Angular][1] for the next project? To determine your choice you should evaluate some aspects of this popular javascript framework. The goal of this article is to show how you can evaluate the use of Angular to give you the right arguments, without getting into technical deep details.

We don't look at [React][5] or [Vue][6], the two other main players in this section. Instead of a comparison between the tools (e.g. [Angular or React][29]), we take a look at the differences between frameworks and libraries in general. And to save you some time, let me sum up something for you: Angular is still as good as React or as Vue, but the right choice depends on a wide range of factors which make it more or less suitable for the clients enviroment.

## Where to start?

The main argument for Angular is its place in [Ionic][14]. Ionic is used for mobile development to build cross platform hybrid apps. One codebase, any platform, e.g. for iOS and Android or progressive web apps. Past releases of Ionic were tightly coupled to Angular. Version 4 of the framework was re-engineered to work as a standalone Web Component library. So if it comes to this framework (Ionic) Angular, because of his history, is currently the best choice.

Furthermore Angular is a mature framework and should be taken for big projects. If you have complex business logic, Angular is your choice. If you have complex routing or form validation, Angular is your choice. If you wanna write closed or stand alone applications with one codebase, Angular is your choice.

## Developer

Two important questions for every tool you use are how mature is it and who is behind it. Angular come from a good family: [Google][0]. Igor Minar, one of the main developer, said that Angular is used in [more than 600 hundred applications in Google][15] such as Firebase Console, Google Analytics, Google Express, Google Cloud Platform and more. Since it is started in the year 2010 more than 400 developers and a big community put their efforts in it. So it is really developed and ready for professional projects and services.

## Features

Angular has more features out of the box than React. This can be a good thing, this can be a bad thing. It depends how you look at it. 

> Some of these features are built-in into the core of the framework and you don’t have an option not to use them. This requires developers to be familiar with features such as dependency injection to build even a small Angular application. Other features such as the HTTP client or forms are completely optional and can be added on an as-needed basis.

(Source: [React VS Angular][16])

As mentioned it before we do not want to get into technical depth, but if you're interested in it, here are some buzzwords Angular comes with: Dependency injection, templates, routing, ajax requests, form building, CSS encapsulation, XSS protection, utilities for unit testing and [RxJS][19]. Well, very technically. But the following two interesting things are worth to take a closer look at: [TypeScript][11] and [Angular Elements][20].

### TypeScript

[TypeScript][11] is a programming language developed by [Microsoft][17] and actively adopt by Angular. It is a superset of JavaScript that compiles to clean, simple [JavaScript][10]. TypeScript is influenced by Java and .NET, so developers are likely to find it easier to learn than plain JavaScript. Well we switched from the tool to the environment. More about this later at the section [Human Resources](#human-resources).

### Angular Elements

[Angular Elements][20] are used for defining new HTML elements in a framework way. Once an element is defined it will be rendered everywhere in the HTML. Its content is created and controlled by JavaScript. Angular provide an API to make it work with the own change detection machanism. The development team of Angular are working on [Angular Elements as a service][22].

## Angular CLI

[Angular command line interface][24] provides some very helpful commands to build up and running full stack applications in minutes. The developer has no need to figure out stuff like source maps, webpack or test runners. This all work out of the box. Angular CLI helps your developer to enforce consistent development practices by generating component, services and state management modules. You can use the tool directly in the console. There is also an UI named [Angular Console][23], which is available as desktop app.

## Ionic Framework

[Ionic][14] is a very popular framework to build hybrid mobile apps. It comes with [Cordova][27] and integrations for the latest JavaScript frameworks like Angular. Angular was tightly coupled with Ionic in the past. With Ionic you can easy build mobile application for iOS and Android with only one codebase. 

## Angular Material

[Angular Material][28] offers you many design components for Angular with modern UI that work across the web, mobile and desktop. Which it you can build fast and consistent interfaces for common interaction patterns like form controls, navigation, layout, grid, buttons etc. This helps developers to build prototypes in a very fast way. 

## Framework VS Library  

Angular is a framework, React is a library. But what's the difference between both? Short, frameworks tell you how you should structure your project, whereas libraries are building blocks that you can use anywhere in your code, in your excisting application. In other words: Frameworks call you how to code your application and within your code you call libraries to do things. Frameworks contain libraries. Libraries can easily be integrated into any existing application, e.g. by adding a `<script>` tag. With a framework the application self needs to be part of it. The framework parse it and generate the code the developers otherwise would have had to write themselves. With this in mind, if your project is a new application or a complex component of an existing one, Angular will be the right tool.

A normal development starts typically with a framework and fill out functions defined in additional libraries throught an API. Both of them, libraries and frameworks, define API, which is used for developer to use.

## Human Resources

Another important question to ask before choosing Angular - or general any library, tool or framework - is which developers are at your disposal. "It's standing and it's falling with the people." used to say my grandma. And so if there are some high skilled Angular developers available to realize the project, just choose it. But keep in mind if there are only one or two developer on board, the project might depends on these guys, if you don't have access to others. Good developers are rare these times.

## Conclusion

It depends on the clients environment wether Angular should be chosen. You have to ask the right questions. Do you need Ionic for mobile applications or progressive web apps? Do you have a complex business logic in your project or a stand alone application? Do some Angular apps in the project already exist? Are there developers available who know Angular or TypeScript or a similar programming language? If one or more questions can be answered with yes, then Angular is a really good choice you can take. 

---

## Sources

[Angular][1] Official Website  
[Angular][3] on GitHub   
[React][5]  
[Vue][6]  
[Angular or React, how to choose][29]  
[The MIT License][7]  
[JavaScript][10] Mozilla  
[Microsoft][17] Official Website  
[TypeScript][11] Official Website  
[Ionic][14] Official Website  
[Cordova][27] Official Website  
[Keynote AngularConnect 2018][15] by Igor Minar  
[React VS Angular][16]  
[Igor Minar on GitHub][17]  
[RxJS][19] Documentation  
[Angular Elements Overview][20]  
[Polyfills][21]  
[Angular Elements as a service][22] Video, 23 min  
[Angular CLI][24] Official Reference  
[Angular Console][23] UI for Angular CLI   
[Angular Material][28] Material Design components for Angular  
[Libraries VS Frameworks][25]  
[Library vs. Framework?][26]  

  
[0]: https://www.google.com "Google, Official Website"  
[1]: https://angular.io "Angular, Official Website"  
[2]: https://angularjs.org "AngularJS, Official Website"  
[3]: https://github.com/angular/angular "Angular on GitHub"  
[4]: https://github.com/angular/angular.js "AngularJS on GitHub"  
[5]: https://reactjs.org "React"  
[6]: https://vuejs.org "Vue"  
[7]: https://opensource.org/licenses/MIT "The MIT License"  
[8]: https://en.wikipedia.org/wiki/MIT_License "MIT License (Wikipedia)"  
[9]: https://fedoraproject.org/wiki/Licensing:MIT?rd=Licensing/MIT "MIT variants"  
[10]: https://developer.mozilla.org/en-US/docs/Web/JavaScript "JavaScript, Mozilla"  
[11]: https://www.typescriptlang.org "TypeScript, Official Website"  
[12]: https://github.com/Microsoft/TypeScript "TypeScript on GitHub"  
[13]: https://www.microsoft.com "Microsoft, Official Website"  
[14]: https://ionicframework.com/framework "Ionic, Official Website"  
[15]: https://www.youtube.com/watch?v=rbFLorQWlOQ&feature=youtu.be&t=358 "Keynote AngularConnect 2018 by Igor Minar"  
[16]: https://www.sitepoint.com/react-vs-angular "React VS Angular"  
[17]: https://github.com/IgorMinar "Igor Minar on GitHub"  
[18]: https://www.microsoft.com "Microsoft, Official Website"  
[19]: http://reactivex.io/rxjs/manual/overview.html "RxJS Documentation"  
[20]: https://angular.io/guide/elements "Angular Elements Overview"  
[21]: https://www.webcomponents.org/polyfills "Polyfills"  
[22]: https://www.youtube.com/watch?v=Z1gLFPLVJjY "Angular Elements as a service"  
[23]: https://angularconsole.com "Angular Console, UI for Angular CLI"  
[24]: https://angular.io/cli "Angula CLI Reference"  
[25]: https://medium.com/datafire-io/libraries-vs-frameworks-626cdde799a7 "Libraries VS Frameworks"  
[26]: https://www.programcreek.com/2011/09/what-is-the-difference-between-a-java-library-and-a-framework/ "Library vs. Framework"  
[27]: https://cordova.apache.org "Cordova, Official Website"  
[28]: https://material.angular.io "Angular Material, Material Design components for Angular"  
[29]: https://inside.namics.com/display/TAFrontend/Angular+or+React%2C+how+to+choose "Angular or React, how to choose"
 
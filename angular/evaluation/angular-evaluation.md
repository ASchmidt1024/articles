# Angular Evaluation

Why take [Angular][1] for the next project? To determine your choice you should evaluate some aspects of this popular javascript framework. The goal of this article is to show how you can evaluate the use of Angular to give you the right arguments, without getting into technical deep details.

[React][5] and [Vue][6] are the two other main players in this section. Before a comparison between the tools (e.g. [Angular or React][29]), we take a look at the differences between frameworks and libraries in general. And to save you some time, let me sum up something for you: Angular is still as good as React or as Vue, but the right choice depends on a wide range of factors which make it more or less suitable for the clients enviroment.

## Where to start?

The main argument for Angular is its place in [Ionic][14]. Ionic is used for mobile development to build cross platform hybrid apps. One codebase, any platform, e.g. for iOS and Android or progressive web apps. Past releases of Ionic were tightly coupled to Angular. Version 4 of the framework was re-engineered to work as a standalone Web Component library. So if it comes to this framework (Ionic) Angular, because of his history, is currently the best choice.

Furthermore Angular is a mature framework and should be taken for big projects. If you have complex business logic, Angular is your choice. If you have complex routing or form validation, Angular is your choice. If you wanna write closed or stand alone applications with one codebase, Angular is your choice.

## Developer

Two important questions for every tool you use are how mature is it and who is behind it. Angular come from a good family: [Google][0]. Igor Minar, one of the main developer, said that Angular is used in [more than 600 hundred applications in Google][15] such as Firebase Console, Google Analytics, Google Express, Google Cloud Platform and more. Since it is started in the year 2010 more than 400 developers and a big community put their efforts in it. So it is really developed and ready for professional projects and services.

In 2018 over 20.000 developer were asked which frontend framework they use or had heard of. A look at the results shows Angular on place three after React and Vue.

![stateofjs.com - 2018, Overall Front-end Frameworks results][37]
(Source: [stateofjs.com - 2018, Overall Front-end Frameworks results][36])

One third of developers would not use Angular again, probably of AngularJS (see [conclusion](#Conclusion)).

## Trends

Angular is a mature framework. This is seen in the trends of the last five years world wide and in the last 12 months in Germany. The values give the search interest relative to the highest point in the chart. The value 100 stands for the highest popular of this search term. The value of 50 means that the term is half popular and the value 0 means that there is not enough data to provide for. 

![Google Trends, World, last 5 years][32]
(Source: [Google Trends, World, last 5 years][34])

![Google Trends, Germany, last 12 month][33]
(Source: [Google Trends, Germany, last 12 month][35])

> (?) Interest over time
>
> Numbers represent search interest relative to the highest point on the chart for the given region and time. A value of 100 is the peak popularity for the term. A value of 50 means that the term is half as popular. A score of 0 means that there was not enough data for this term.

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

> Angular has always been at the center of what makes Ionic great. While the core components have been written to work as a standalone Web Component library, the @ionic/angular package makes integration with the Angular ecosystem a breeze. @ionic/angular includes all the functionality that Angular developers would expect coming from Ionic 2/3, and integrates with core Angular libraries, like the Angular router.

(Source: [Ionic Introduction][31])

## Angular Material

[Angular Material][28] offers you many design components for Angular with modern UI that work across the web, mobile and desktop. Which it you can build fast and consistent interfaces for common interaction patterns like form controls, navigation, layout, grid, buttons etc. This helps developers to build prototypes in a very fast way. 

## Framework VS Library

Angular is a framework, React is a library. But what's the difference between both? Short, frameworks tell you how you should structure your project, whereas libraries are building blocks that you can use anywhere in your code, in your excisting application. In other words: Frameworks call you how to code your application and within your code you call libraries to do things. Frameworks contain libraries. Libraries can easily be integrated into any existing application, e.g. by adding a `<script>` tag. With a framework the application self needs to be part of it. The framework parse it and generate the code the developers otherwise would have had to write themselves. With this in mind, if your project is a new application or a complex component of an existing one, Angular will be the right tool.

A normal development starts typically with a framework and fill out functions defined in additional libraries throught an API. Both of them, libraries and frameworks, define API, which is used for developer to use.

## Perfomance

Angular, React and even Vue are comparatively faster than other JavaScript frameworks. You should not take performance into account to draw the [conclusion](#Conclusion) because it mainly relies on the size of the application and optimization of code.

## Long Term Support

[AngularJS][2], the first version of Angular, is still a supported framework. The release of version 2 in the year 2016 came with such a huge refactoring, that we can speak of two stand alone frameworks. On 1. July 2018 AngularJS entered a [3 year Long Term Support][30] period.

## Human Resources

Another important question to ask before choosing Angular - or general any library, tool or framework - is which developers are at your disposal. "It's standing and it's falling with the people." used to say my grandma. And so if there are some high skilled Angular developers available to realize the project, just choose it. But keep in mind if there are only one or two developer on board, the project might depends on these guys, if you don't have access to others. Good developers are rare these times.

## Facts

|   | Angular  | React  |
|---:|:---:|:---:|
| Version  | <img src="https://badge.fury.io/js/%40angular%2Fcore.svg" alt="npm version" height="18"> | <img src="https://badge.fury.io/js/react.svg" alt="npm version" height="18"> |
| GitHub Stars  | ![GitHub Stars Angular][41]  | ![GitHub Stars React][42]  |
| [Downloads<br><small>2018 (npm)</small>][38]  | 16.609.604  | 128.146.570  |
| Developer  | Google  | Facebook  |
| Release Year | 2010  | 2013  |
| Licence  | [MIT][7]  | [MIT][7]  |
| Open job positions<br><small>(Germany, start 2019)</small> |
| XING  | [5.180][45]  | [3.260][46]  |
| LinkedIn  | [8.765][47]  | [5.827][48]  |
| Monster  | [286][49]  | [180][50]  |

Have a look at the [framework matrix with a closer comparison][29] (bottom of the page).

## Reason to use

- Great support for [Ionic][14]
- Many high skilled developers
- Full-featured and powerful
- Good documentation
- Powerful developer tooling

## Reason not to use

- To heavy for little projects
- No good integration in existing projects
- Lightweight alternatives like [React][5], [Vue][6] or [Ember][43]
- [One third of developers would not use it again][36] (probably of AngularJS; see [Conclusion](#Conclusion))
- Failed projects

## Conclusion

It depends on the clients environment wether Angular should be chosen. You have to ask the right questions. Do you need Ionic for mobile applications or progressive web apps? Do you have a complex business logic in your project or a stand alone application? Do some Angular apps in the project already exist? Are there developers available who know Angular or TypeScript or a similar programming language? If one or more questions can be answered with yes, then Angular is a really good choice you can take. 

On the develpers site, the following chart shows the technology’s satisfaction ratio over its total usage (Source: [stateofjs.com][44]).

![stateofjs.com - 2018, Overall Front-end Frameworks Conclusion][51]

> Many people have pointed out that Angular's poor satisfaction ratio is probably in part due to the confusion between Angular and the older, deprecated AngularJS (previous surveys avoided this issue by featuring both as separate items). So while Angular did “fall” –relatively speaking– from its dominance from a few years back, it might very well regain ground once the dust clears.

(Source: [Front-end Frameworks - Conslusion, stateofjs.com][44])

---

## Sources

[Angular][1] Official Website  
[Angular][3] on GitHub   
[AngularJS][2] Official Website  
[AngularJS][4] on GitHub   
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
[React vs Angular vs Vue.js: A Complete Comparison Guide][52]  
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
[AngularJS Long Term Support][30]  
[Ionic Introduction][31]  
[Google Trends, Worldwide, 5 years, React VS Angular][34]  
[Google Trends, Germany, 12 months, React VS Angular][35]  
[State of JavaScript, Front-end Frameworks 2018][36]  
[Download statistics for React and Angular][38]  
[Angular - bestofjs.org][39]  
[React - bestofjs.org][40]   
[Front-end Frameworks - Conslusion, stateofjs.com][44]  


  
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
[29]: https://inside.namics.com/x/IIF8Ag "Angular or React, how to choose"  
[30]: https://docs.angularjs.org/misc/version-support-status "AngularJS Long Term Support"  
[31]: https://ionicframework.com/docs/intro "Ionic Introduction"  
[32]: img/google-trends_worldwide_5years_react-angular.png "Google Trends, Worldwide, 5 years, React VS Angular"  
[33]: img/google-trends_germany_12months_react-angular.png "Google Trends, Germany, 12 months, React VS Angular"  
[34]: https://trends.google.com/trends/explore?date=today%205-y&q=React,Angular "Google Trends, Worldwide, 5 years, React VS Angular"  
[35]: https://trends.google.com/trends/explore?geo=DE&q=React,Angular "Google Trends, Germany, 12 months, React VS Angular"  
[36]: https://2018.stateofjs.com/front-end-frameworks/overview/ "State of JavaScript, Front-end Frameworks 2018"  
[37]: img/stateofjs.com_2018_frontend-frameworks.png "stateofjs.com - 2018, Overall Front-end Frameworks results"  
[38]: https://npm-stat.com/charts.html?package=react&package=angular&from=2018-01-01&to=2018-12-31 "Download statistics for React and Angular"  
[39]: https://bestofjs.org/projects/angular "Angular - bestofjs.org"  
[40]: https://bestofjs.org/projects/react "React - bestofjs.org"  
[41]: https://img.shields.io/github/stars/angular/angular.svg?label=Star "GitHub Stars Angular"  
[42]: https://img.shields.io/github/stars/facebook/react.svg?label=Star "GitHub Stars React"  
[43]: https://www.emberjs.com/ "ember, Official Website"  
[44]: https://2018.stateofjs.com/front-end-frameworks/conclusion/ "Front-end Frameworks - Conslusion, stateofjs.com"  
[45]: https://www.xing.com/jobs/search?keywords=Angular&sc_o=jobs_search_button "Angular Jobs, XING"  
[46]: https://www.xing.com/jobs/search?keywords=React&sc_o=jobs_search_button "React Jobs, XING"  
[47]: https://www.linkedin.com/jobs/search/?keywords=Angular "Angular Jobs, LinkedIn"  
[48]: https://www.linkedin.com/jobs/search/?keywords=React&location=Deutschland&locationId=de%3A0 "React Jobs, LinkedIn"  
[49]: https://www.monster.de/jobs/suche/?q=Angular&cy=DE "Angular Jobs, LinkedIn"  
[50]: https://www.monster.de/jobs/suche/?q=React&cy=DE&rad=20&intcid=swoop_HeroSearch_DE "React Jobs, Monster"  
[51]: img/stateofjs.com_2018_frontend-frameworks-conclusion.png "stateofjs.com - 2018, Overall Front-end Frameworks Conclusion"  
[52]: https://medium.com/front-end-weekly/react-vs-angular-vs-vue-js-a-complete-comparison-guide-d16faa185d61 "React vs Angular vs Vue.js: A Complete Comparison Guide"  

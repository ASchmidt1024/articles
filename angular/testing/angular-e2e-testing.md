# Angular E2E Testing

You might not know but Angular was built by software testers at Google. So testing is always the background behind the framework. Besides Unit Testing and DOM Testing End-to-End Testing is another part in the testing area; and it wouldn't be fun if you can't automate it. There is where [Protractor][1] comes in.

## Introduction

[Protractor][2] is a framework for writing E2E tests especially for Angular. With it you can run tests in the browser, interacting with it as your user would do. It comes with every new Angular app. The easiest way to dive into end to end testing is creating a new Angular app. Open a command line (CLI).

```console
npm new testing-e2e
```

By creating this new app one end to end test will be written already. Let's have a look at the folder 'e2e' in the root directory (same level like the folder 'src'). 

## File structure

In the folder 'e2e' we see two files and another folder with the following structure.

- src
  * app.e2e-spec.ts
  * app.po.ts
- protractor.conf.js
- tsconfig.e2e.json

Let's start from bottom to top. 

## tsconfig.e2e.json

The file 'tsconfig.e2e.json' contains the configuration required to compile the project. 

```json
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "module": "commonjs",
    "target": "es5",
    "types": [
      "jasmine",
      "jasminewd2",
      "node"
    ]
  }
}
```

It extends the existing file '[tsconfig.json][6]' in your root directory and holds some options for the [TypeScript][10] compiler like output directory, module, target (ECMAScript 5) and types (list of packages, that will be included).

## protractor.conf.js

This is the [Protractor configuration file][7]. 

```javascript
// Protractor configuration file, see link for more information
// https://github.com/angular/protractor/blob/master/lib/config.ts

const { SpecReporter } = require('jasmine-spec-reporter');

exports.config = {
  allScriptsTimeout: 11000,
  specs: [
    './src/**/*.e2e-spec.ts'
  ],
  capabilities: {
    'browserName': 'chrome'
  },
  directConnect: true,
  baseUrl: 'http://localhost:4200/',
  framework: 'jasmine',
  jasmineNodeOpts: {
    showColors: true,
    defaultTimeoutInterval: 30000,
    print: function() {}
  },
  onPrepare() {
    require('ts-node').register({
      project: require('path').join(__dirname, './tsconfig.e2e.json')
    });
    jasmine.getEnv().addReporter(new SpecReporter({ spec: { displayStacktrace: true } }));
  }
};
```

First the `SpecReporter` is declared. `allScriptsTimeout` holds the timeout in milliseconds for each script run on the browser. The `specs` are relative to the location of this config and point to every file which ends with `*.e2e-spec.ts`. Keep that in mind, if you create another test. The `capabilities` option holds `chrome` as testing browser. It could be also `firefox` or `internet explorer` or `netscape`. Well, the last one is a joke. There is a [list of available capabilities][8]. For Chrome (and Firefox) Protractor can `directConnect` to the browser driver. As `baseUrl` `localhost` will be used at port `4200`. The test framework to use is `jasmine`. [Jasmine][9] is fully supported as test and assertion framework. The `jasmineNodeOpts` holds the options to be passed to Jasmine like `showColors` in the terminal, the `defaultTimeoutInterval` in ms before a test fails and a `function() {}` called to `print` Jasmine results. Last but not least `onPrepare()` is a callback function called once Protractor is ready and available and before the tests are executed. At this point global variables will be available from the test framework. TypeScript Node (`ts-node`) is required and works by registering the TypeScript compiler the config file 'tsconfig.e2e.json', at which we already look at (see above). With the following line Protractor `addReporter` to `jasmine`, the `SpecReporter`, which was declared in the first line. The `[jasmine-spec-reporter][11]` will be used to enhance the Protractor tests execution report on the command line.

## app.po.ts

What's about the file 'app.po.ts'? 

```typescript
import { browser, by, element } from 'protractor';

export class AppPage {
  navigateTo() {
    return browser.get(browser.baseUrl) as Promise<any>;
  }

  getTitleText() {
    return element(by.css('app-root h1')).getText() as Promise<string>;
  }
}
```

In this file you write the code to find the elements in your DOM you want to test. It's all about the selectors you know from CSS. But, step by step. First there are some `import`s like `browser` for interacting with - you guess it - the browser, `by` for selecting elements by CSS as mentioned and `element` for converting the selected element. By `export`ing the `class` `AppPage` Protractor will know to `navigateTo()` the specific `baseUrl`, which is defined in the file protractor.conf.js (see above). This will be done by a `Promise`, an asynchronous function call. Another [promise][12] comes with the following function `getTitleText()`. It `return`s if `getText()` of the headline `element` `'app-root h1'` (which is selected `by.css`) succeeds or fails. For the future: If you change the selector of your element, you change it in this file. You don't need to change anything in your tests. Apropo test. Let's come to the test file.

## app.e2e-spec.ts

Actually, this file holds the end to end tests. 

```typescript
import { AppPage } from './app.po';
import { browser, logging } from 'protractor';

describe('workspace-project App', () => {
  let page: AppPage;

  beforeEach(() => {
    page = new AppPage();
  });

  it('should display welcome message', () => {
    page.navigateTo();
    expect(page.getTitleText()).toEqual('Welcome to testing-e2e!');
  });

  afterEach(async () => {
    // Assert that there are no errors emitted from the browser
    const logs = await browser.manage().logs().get(logging.Type.BROWSER);
    expect(logs).not.toContain(jasmine.objectContaining({
      level: logging.Level.SEVERE,
    } as logging.Entry));
  });
});
```

After `import`ing the `AppPage` from file `app.po.ts` (see above) and `browser` and `logging` from `protractor` it `describe` the test function called `'workspace-project App'`. `let`s define a variable `page` as type of `AppPage`. `beforeEach()` test it will be used to build a `new AppPage()`. 

And if there is a `beforeEach()` there is an `afterEach()`, too. Okay, not in every case, you know. But in this case it is an `async`hronous function, which `Assert that there are no errors emitted from the browser`. In the `const` named `logs` we `await` the JavaScript console `logs` from the browser. In our case from Chrome, which was defined earlier in the config of Protractor. The console helps us to spot issues. We usually use the console for reporting events or state changes. Here we `expect` that the `logs` `not.toContain` messages about things that went wrong. For instance an unknown command. This will be done through the `logging.Level.SEVERE` (for more about Log Levels read [Logging in WebDriver][13]). Last `jasmine.objectContaining` is for those times when an expectation only cares about certain key/value pairs. 

Finally let's have a look at the test itself in the middle of the file. Every test begins with `it` and an individual description, which describe the test in your own words. You will see this description later in the console in color green, if it succeeds, or in red, if it fails. In this case it `'should display welcome message'`. Protractor should `navigateTo()` the `page`, which was defined earlier, and `expect` to `getTitleText()` like ... no `toEqual('Welcome to testing-e2e!')`. That's all. If this is the case, the test succeeds. Otherway it fails. Maybe you want to test it by changing the expectiong title.

## Test run

Now, after explaining the whole thing of end to end testing with Protractor, let's make the magic happen and run the test through command line.

```console
npm run e2e
```

In your console you should see something similiar like the following output.

![npm run e2e - console output][14]

Do you see the green successfully passed test message? Magic! Awesome. At this point it makes fun. And if all test successful passed you will love your job. 

---

## Sources

[Protractor - end to end testing for Angular][1]  
[The official end to end testing framework for Angular apps][2]  
[Documentation for CLI][3]  
[Automate E2E testing of Angular 4 apps with ProtractorJS & Jasmine][4]  
[Inside: Protractor (e2e)][5]  
[tsconfig.json][6]  
[Protractor configuration file][7]  
[Selenium capabilities][8]  
[Jasmine - Behavior-Driven JavaScript][9]  
[TypeScript - JavaScript that scales][10]  
[jasmine-spec-reporter - Real time console spec reporter][11]  
[Using promises][12]  
[Logging in WebDriver][13]  
[Asserting console logs in Protractor tests][15]  

[1]: http://www.protractortest.org "Protractor - end to end testing for Angular"  
[2]: https://protractor.angular.io "The official end to end testing framework for Angular apps"  
[3]: https://angular.io/cli/e2e "Documentation for CLI"  
[4]: https://link.medium.com/yHBgYi74mV "Automate E2E testing of Angular 4 apps with ProtractorJS & Jasmine"  
[5]: https://inside.namics.com/pages/viewpage.action?pageId=359006930 "Inside: Protractor (e2e)"  
[6]: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html "tsconfig.json"  
[7]: https://github.com/angular/protractor/blob/master/lib/config.ts "Protractor configuration file"  
[8]: https://github.com/SeleniumHQ/selenium/wiki/DesiredCapabilities "Selenium capabilities"  
[9]: https://jasmine.github.io/ "Jasmine - Behavior-Driven JavaScript"  
[10]: https://www.typescriptlang.org/ "TypeScript - JavaScript that scales"
[11]: https://github.com/bcaudan/jasmine-spec-reporter "jasmine-spec-reporter - Real time console spec reporter for jasmine testing framework"  
[12]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises "Using promises"  
[13]: https://github.com/SeleniumHQ/selenium/wiki/Logging "Logging in WebDriver"  
[14]: img/npm-run-e2e_console-output.png "npm run e2e - console output"  
[15]: https://medium.com/front-end-weekly/asserting-console-logs-in-protractor-tests-fee444833373 "Asserting console logs in Protractor tests"  

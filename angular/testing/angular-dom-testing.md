# Angular DOM Testing

This article is about Angular DOM Testing. You might have read [Angular Unit Testing][1] before. Well, this text will be similar. But except of using the tools of Angular testing package we will use the [Angular Testing Library][1] instead. This testing library is an Angular adapter around [DOM Testing Library][2]. 

Why DOM Test? Well, the Document Object Model is that what the source code makes. At the end it is all about manipulating the DOM and the DOM is that what the user access through the browser. DOM testing is about to test your app the same way as your users. Tests only break when you app breaks. Or as you can read on the official website:

> The more your tests resemble the way your software is used, the more confidence they can give you.

DOM Testing encourage good testing practices and the `dom-testing-library` encourages your app to be more accessible and allows you to get your tests closer to using your components the way a user will, which allows your tests to give you more confidence that your application will work when a real user uses it.

## Introduction

For this lecture we create a brand new Angular app with the command line interface (CLI) of Angular. Run the CLI command `ng new` and provide some name like `testing-dom`.

```console
ng new testing-dom
```

If we're at the command line we can install the Angular Testing Library using `npm` in our project folder.

```console
cd testing-dom
npm install --save-dev @angular-extensions/testing-library
```

So we change the directory to our project folder and install the library for development purpose with `--save-dev`. As you might know already your new app comes with some Unit Tests included. Take a look at the source files you will see the test file called `app.component.spec.ts`. We want to use this file to write our first tests the DOM Testing way.

```typescript
// old
import { TestBed, async } from '@angular/core/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
    beforeEach(async(() => {
        TestBed.configureTestingModule({
        declarations: [
            AppComponent
        ],
        }).compileComponents();
    }));

    it('should create the app', () => {
        const fixture = TestBed.createComponent(AppComponent);
        const app = fixture.debugElement.componentInstance;
        expect(app).toBeTruthy();
    });

    it(`should have as title 'testing-dom'`, () => {
        const fixture = TestBed.createComponent(AppComponent);
        const app = fixture.debugElement.componentInstance;
        expect(app.title).toEqual('testing-dom');
    });

    it('should render title in a h1 tag', () => {
        const fixture = TestBed.createComponent(AppComponent);
        fixture.detectChanges();
        const compiled = fixture.debugElement.nativeElement;
        expect(compiled.querySelector('h1').textContent).toContain('Welcome to testing-dom!');
    });
});
```

## DOM Testing

This test is based on the Angular core testing tools:

```typescript
import { TestBed, async } from '@angular/core/testing';
```

Which we want to replace with:

```typescript
import { createComponent } from '@angular-extensions/testing-library';
```

Now we can use the new tools. The `beforeEach()` function can be deleted. We want to rewrite test by test.

```typescript
// old
// it('should create the app', () => {
//     const fixture = TestBed.createComponent(AppComponent);
//     const app = fixture.debugElement.componentInstance;
//     expect(app).toBeTruthy();
// });

// new
it(`should create the app`, async () => {
    const { container } = await createComponent('<app-root></app-root>', {
        declarations: [AppComponent],
    });
    expect(container).toBeTruthy();
});
```

The old way was to create a `fixture` and get the `componentInstance` with the `debugElement`. Now we're using `async()` and `await` to expect our component `toBeTruthy()`. But first we declare our component we want to have for this DOM testing environment: `AppComponent`. In a `container` we wait until the component (`<app-root></app-root>`) is created. This simple test setup is a basic way to test asynchronously the DOM like our user will get it.

```typescript
// old
// it(`should have as title 'testing-dom'`, () => {
//     const fixture = TestBed.createComponent(AppComponent);
//     const app = fixture.debugElement.componentInstance;
//     expect(app.title).toEqual('testing-dom');
// });
//
// it('should render title in a h1 tag', () => {
//     const fixture = TestBed.createComponent(AppComponent);
//     fixture.detectChanges();
//     const compiled = fixture.debugElement.nativeElement;
//     expect(compiled.querySelector('h1').textContent).toContain('Welcome to testing-dom!');
// });

// new
it(`should have a title 'Welcome to testing-dom!'`, async () => {
    const { getByText } = await createComponent('<app-root></app-root>', {
        declarations: [AppComponent],
    });
    expect(getByText('Welcome to testing-dom!')).toBeDefined();
});
```

Well we use the same structure like the test above, but instead to test our title if it equals to a given string, we test the DOM with `getByText()` and look if the string `Welcome to testing-dom!` `toBeDefined()`. `getByText()` is a query accessible to everyone and should be our top preference for non-form elements. For more detailed information check: [Which query should I use?][4] 

```typescript
// new
it(`should have an image with alt text 'Angular Logo'`, async () => {
    const { getByAltText } = await createComponent({
        component: AppComponent,
    }, {
        declarations: [AppComponent],
    });
    expect(getByAltText('Angular Logo')).toBeDefined();
});
```

We can also test if an `alt` for example of an image exits in the DOM. For this we use the query `getByAltText()` and `expect`, that there is one with the string `Angular logo` `toBeDefined()`.

## Result

Three tests for DOM testing our Angular app.

```typescript
// new
import { createComponent } from '@angular-extensions/testing-library';
import { AppComponent } from './app.component';

describe('AppComponent', () => {

    it(`should create the app`, async () => {
        const { container } = await createComponent('<app-root></app-root>', {
            declarations: [AppComponent],
        });
        expect(container).toBeTruthy();
    });

    it(`should have as title 'testing-app'`, async () => {
        const { getByText } = await createComponent('<app-root></app-root>', {
            declarations: [AppComponent],
        });
        expect(getByText('Welcome to testing-app!')).toBeDefined();
    });

    it(`should have a image alt text 'Angular Logo'`, async () => {
        const { getByAltText } = await createComponent({
            component: AppComponent,
        }, {
            declarations: [AppComponent],
        });
        expect(getByAltText('Angular Logo')).toBeDefined();
    });

});
```

Running `ng test` in the console should give us 3 SUCCESSful tests. 

![DOM Testing in Angular](img/testing-dom_ng-test_success_browser.png)

---

## Sources

[Angular Unit Testing][0]  
[Angular Testing Library][1]  
[DOM Testing Library][2]  
[Async and Await explained][3]  
[Which query should I use?][4]  

[0]: angular-unit-testing.md "Angular Unit Testing"  
[1]: https://testing-library.com/angular "Angular Testing Library"  
[2]: https://testing-library.com/ "DOM Testing Library"  
[3]: https://nikgrozev.com/2017/10/01/async-await/ "Async and Await explained"
[4]: https://testing-library.com/docs/guide-which-query "Which query should I use?"

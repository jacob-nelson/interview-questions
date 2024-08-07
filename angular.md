### What is Angular?
Angular is a TypeScript-based open-source front-end web application framework developed by Google.
### What are the key features of Angular?
- Component-based Architecture
- Two-way Data Binding
- Dependency Injection
- TypeScript Support
- Routing
- Forms
- Modules
- Performance
- Developer Tools
- Community and Ecosystem
- Observables for handling asynchronous data streams
- Pipes for data transformation and formatting
- Directives for adding custom behaviour to HTML elements
- Animations for creating dynamic and engaging user experiences
### What is Angular CLI, and why is it used?
Angular CLI (Command Line Interface) is a tool that helps develop, build, test, and deploy Angular applications. It simplifies common tasks and provides a consistent workflow.
### How do you create a new Angular application?
- install the Angular CLI globally using npm or yarn
- Open your terminal or command prompt.
- Navigate to the directory where you want to create your project.
- Run the command ng new <app-name>
- Follow the prompts
### Explain two-way data binding in Angular.
Two-way data binding in Angular is a mechanism that allows automatic synchronization of data between the model and the view.
### What is a component in Angular?
A component in Angular is a building block of an application, representing a part of the user interface and encapsulating its behaviour and template.
### What is Angular Directive? Provide examples.
Directives in Angular are markers on a DOM element that tell Angular to attach a behaviour to that DOM element or even transform the DOM element and its children. Examples include ngFor, ngIf, and ngModel.
### What are Angular pipes? Provide examples.
Pipes in Angular are used to transform data before displaying it in the view. Examples include the DatePipe for formatting dates and the UpperCasePipe for converting text to uppercase.
### Explain Angular services and their use.
Angular services are singleton objects that can be injected into components and other services. They are used to share data and functionality across different parts of an application.
### What is the purpose of `NgModule` in Angular?
`NgModule` is used to define a modular structure for organising and managing Angular applications. It helps in organizing components, services, and other Angular features.
### Explain the ngOnChanges lifecycle hook.
`ngOnChanges` is a lifecycle hook in Angular that is called when the data-bound properties of a component change. It receives a SimpleChanges object that contains the current and previous values of the bound properties.
### when is ngonchanges lifecycle hook called?
ngOnChanges gets called before ngOnInit and whenever a component's bound input is changed FROM THE PARENT COMPONENT. Remember that ngOnChanges is specific to bound inputs on the component. This means if you don't have any @Input properties on a child, ngOnChanges will never get called.

### What is dependency injection in Angular?
Dependency injection is a design pattern in which the dependencies of a component or service are provided from the outside, typically by the framework. Angular's DI system is responsible for injecting dependencies.
### How does routing work in Angular?
Angular's router enables navigation between different components while keeping the UI in sync with the URL. It allows the development of single-page applications (SPAs).
### What are the different types of routing in Angular?
- Feature-based Routing
- Lazy Loading
- Nested Routing
- Auxiliary Routes
- Wildcard Routes
### What are the different methods to pass data through routes?
- Route parameters: Suitable for fixed data like IDs.
    - Use named parameters in your route path to hold data values: `/users/:userId/details`.
    - Access these parameters in your component using the `ActivatedRoute` service and inject it into your component constructor.
- Query parameters: Useful for filtering or temporary data.
    - Store data as key-value pairs in the URL after the ? symbol: `/users?category=admin`.
    - Access them using the `queryParams` property of the `ActivatedRoute` object.
- Route data: Ideal for pre-fetching data specific to a route.
    - Attach data directly to a specific route using the data property in your routing module.
    - Access this data using the data property of the `ActivatedRoute` snapshot.
- Navigation extras: Convenient for programmatic navigation with data.
    - Pass data when navigating programmatically using the `queryParams` or `state` properties of the `NavigationExtras` object.
    - Access them in the target component using the `queryParams` or `state` properties of the `ActivatedRoute` snapshot.
- Shared services: Best for complex data shared across components.
    - Create a service to hold and share data across components.
    - Inject this service into different components that need access to the data.
### What are the differences between promise and observable
- Both Promises and Observables are asynchronous programming tools used in JavaScript to handle operations that take time to complete. However, they have some key differences:
- Promise: Resolves with a single value once the operation completes. Think of it like a one-time delivery.
- Observable: Emits a sequence of values over time. Think of it like a stream of data.
- Promise: Eager execution. Starts executing as soon as it's created.
- Observable: Lazy execution. Only starts emitting values when you subscribe to it.
- Promise: Once created, a Promise cannot be cancelled.
- Observable: You can unsubscribe from an Observable to stop receiving further values.
- Promise: Uses .catch to handle errors after the operation completes.
- Observable: Uses error callback within the subscribe method to handle errors for each emitted value.
- Promise: Ideal for fetching data from an API, performing a single asynchronous operation, or handling a simple success/error scenario.
- Observable: Ideal for handling real-time data streams, user interactions, or long-running operations where you need to react to multiple events over time.
- Observables are often considered more powerful and flexible than Promises, but they also have a steeper learning curve.
- Both Promises and Observables can be used in conjunction with libraries like RxJS for more advanced operations and data transformations.
### What are the differences between subject and behavior subject?

| Subject |BehaviorSubject |
|---|---|
|Has no initial value. Subscribers only receive values emitted after they subscribe.|Holds an initial value and immediately emits it to any new subscriber.|
|Emits values only when next is called.|Emits the initial value and then any subsequent values called with next.|
|Does not replay past values. New subscribers only receive future values.|Remembers the last emitted value and replays it to new subscribers upon subscription.|
|Suitable for creating new data streams or broadcasting updates to all subscribers.|Useful for establishing shared state across different parts of your application or ensuring new subscribers receive the latest information.|


### Explain View encapsulation

View encapsulation is a mechanism in Angular that helps isolate the styles of a component from the styles of other components. This prevents styles from bleeding between components and causing unexpected visual issues.

Here's a breakdown of view encapsulation in Angular:

**Why is it important?**

Prevents Style Conflicts: Without encapsulation, styles defined in one component could unintentionally affect styles in other components, leading to a mess.
Improved Maintainability: Encapsulation promotes cleaner code by keeping styles specific to each component.
Reusable Components: Styles are encapsulated within the component, making it more reusable without affecting the styles of other components.

**How does it work?**

Angular offers three view encapsulation options:

- Emulated (default): This is the default behavior. Angular adds a unique attribute to the component's host element and styles, effectively scoping them to the component's view.

- None: This disables encapsulation. Styles defined in the component are applied globally, potentially affecting other components. It's generally not recommended due to the risk of style conflicts.

- Shadow DOM: This leverages the browser's Shadow DOM API to create a truly isolated environment for the component's view and styles. It offers the strongest encapsulation but might have limited browser support for older browsers.

**Choosing the right encapsulation:**

- Emulated (default): A good choice for most cases. It provides a balance between isolation and browser compatibility.
- Shadow DOM: Ideal for stricter isolation, especially for reusable components or complex applications. Consider browser compatibility if targeting older browsers.
- None: Avoid unless absolutely necessary due to the high risk of style conflicts.

**Additional points:**

You can configure the encapsulation mode using the encapsulation property in the @Component decorator.
Encapsulation applies to styles defined within the component's template (<style>) and stylesheets referenced using styleUrls.
By effectively using view encapsulation, you can create cleaner, more maintainable, and reusable Angular components with well-defined visual styles.

### Define `standalone` components and their benefits

standalone components are a new feature introduced in version 14 that allows you to create reusable UI components without requiring them to be part of an NgModule. This offers several benefits and can streamline your development process.

#### Here's a breakdown of standalone components in Angular:

**What are they?**

- Standalone components are a special type of Angular component that doesn't need to be declared within an NgModule.
- They are self-contained units with their own template, logic, and dependencies.
- Standalone components offer a powerful and flexible way to build Angular applications. They simplify component creation, improve code organization, and make component sharing more efficient.

#### Benefits:

- **Simpler Component Creation:** You don't need to create or manage NgModules specifically for these components.
- **Improved Code Organization:** Standalone components promote a more modular approach, keeping your code focused on the component itself.
- **Easier Sharing:** Standalone components can be easily shared with other projects without requiring specific NgModule dependencies.

#### How to Create Them:

- **Component Class:** Define your component class as usual, extending the `Component` class from `@angular/core`.
- **Standalone Flag:** Use the `standalone: true` property in the component decorator. This indicates it's a standalone component.
- **Template and Logic:** Implement your component's template logic as you would with any other Angular component.
- **Imports (Optional):** If the component requires external directives, pipes, or other standalone components, you can import them directly within the component class.

#### Example:

```
import { Component, standalone } from '@angular/core';

@Component({
  selector: 'app-my-standalone-component',
  standalone: true,
  template: `
    <h1>This is a standalone component!</h1>
  `
})
export class MyStandaloneComponent { }

```

| Feature | Standalone Component | Regular Component |
|---|---|---|
| NgModule | Not required | required |
| Code Organization | More modular | Potentially less modular |
| Sharing | Easier to share | Required NgModule consideration |

### Content Projection

Content projection is a feature in frameworks like Angular that allows you to create reusable UI components with customizable content areas. It essentially lets you define a container component that can house content provided by another component. This way, you can create flexible and modular UIs that can be adapted for different use cases.

#### Here's how it works:

- **Define a container component:** This component will have a template that defines the overall structure of the UI. It will also include a special placeholder, typically denoted by the <ng-content> tag, which specifies where the projected content will be inserted.

- **Projecting content:** The child component that uses the container component can provide the content that will be inserted into the placeholder. This content can be anything from text and images to other components.

By using content projection, you can achieve a separation of concerns between the structure and the content of your UI components. The container component can focus on providing the overall layout and styling, while the child component can focus on providing the specific content that will be displayed.

#### Here are some of the benefits of using content projection:

- **Increased reusability:** Container components can be reused in different parts of your application with different projected content.
- **Improved maintainability:** By separating the structure from the content, you can make changes to one without affecting the other.
- **More flexible UIs:** Content projection allows you to create UIs that can be easily adapted to different use cases.

If you're working with a framework that supports content projection, it's a powerful technique that can help you create more modular and maintainable UIs.

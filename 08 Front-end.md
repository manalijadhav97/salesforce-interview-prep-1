# Front-end

## Lightning Web Components

### Component Structure 

The folder and its files must have the same name, including capitalization and underscores.

`myComponent`

- `├──myComponent.html` - HTML File (Optional)
- `├──myComponent.js` - JavaScript File (Required)
- `├──myComponent.js-meta.xml` - Configuration File (Optional)
- `├──myComponent.css` - CSS File (Optional)
- `|──myComponent.svg` - SVG Icon (Optional)
- `|──shared_code.js` - JavaScript File (Optional - to share code)
- `└──moreSharedCode.js` - JavaScript File (Optional - to share code)

### Events
   - [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel)
   - Custom Events
   - PubSub Limitations - can be accessed by components from other namespaces, cannot be used inside Visualforce
   - Event propagation and phases

### [Lightning Data Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_ui_api)
![image](https://user-images.githubusercontent.com/34469349/153461038-ce6ff1c6-288c-4ef0-888f-a479352d1654.png)

#### Standard LDS components

#### Difference between base lightning LDS component
![image](https://user-images.githubusercontent.com/34469349/153460813-da92e3b3-c78a-4346-a03e-19c7a992fdf1.png)

#### [Wire Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_wire_service_about)

#### `lightning/ui*Api` Wire Adapters and Functions](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_ui_api)

#### Advantages of LDS
   1. No need to write any Apex class
   2. No need to write SOQL
   3. Field level security and record sharing is inbuilt
   4. CRUD operation supported
   5. Shared cache is used by all standard and custom components
   6. Auto notification to all components


### Calling Apex from LWC

- Use case for calling apex imparatively.
- Call apex imparatively and pass parameters
- [Client Side Caching](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.apex_result_caching) (cacheable=true & refreshApex())

### [HTML Template Directives](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_directives)

### Decorators

- `@api`
- `@wire`
- `@track`

### Lifecycle Hooks

- `connectedCallback()`
- `constructor()`
- `disconnectedCallback()`
- `errorCallback()`
- `render()`
- `renderedCallback()`

### Slots

### `@salesforce` Modules

- `@salesforce/apex`
- `@salesforce/label`
- `@salesforce/resourceUrl`
- `@salesforce/messageChannel`
- `@salesforce/schema`
- `@salesforce/user`
- `@salesforce/userPermission`
- `@salesforce/customPermission`
- `@salesforce/apexContinuation`
- `@salesforce/client/formFactor`
- `@salesforce/community`
- `@salesforce/contentAssetUrl`
    

### [Lightning Locker Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.security_locker_service)

## Questions
1. [Explain the component structure of LWC component](#component-structure)
2. [What are the advantages of LDS?](#advantages-of-lds)
3. How to communicate from parent LWC to child LWC? How to access the child variables and methods?
4. How to communicate from parent LWC to grand child LWC?
5. How to communicate from child LWC to parent lwc?
6. How to communicate from child LWC to grand parent lwc?
7. How to communicate between sibling LWCs?
8. How to communicate between cousin LWCs?

## JavaScript

### data types
   #### Primitive
   Premitives types are those that always hold a single value and are always passed by value.
   
   - `number` - The number type represents both integer and floating point numbers.
   - `bigint` - the “number” type cannot represent integer values larger than (2^53-1). BigInt type was recently added to the language to represent integers of arbitrary length.
   - `string`
   - `boolean`
   - `null` - type of null returns "object" – this is an error in the language, it’s not actually an object.
   - `undefined`
   - `symbol`

   #### Non Primitive
   - `object`

### variable scope
### [closure](https://javascript.info/closure)
### implicit and explicit coercion
### event loop
### callback functions

   A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action. They are often used to continue code execution after an asynchronous operation has completed — these are called asynchronous callbacks.
   
### Promises
   This is not 100% correct analogy but you get the point.
   
   Just like real life promises, JS promises are way to let promise consumer know about the asynchronous result.
   For example, as a candidate I applied for a job position at your organization. Since, hiring activity is asynchronous, the recruiter emails me (promises) that you application is under process (executing) and they will get back (it will be settled). At this stage the promise is in pending state. Once the application is processed, the recruiter will either fulfill the promise by telling that they are scheduling next round of technical discussion or reject the promise by letting me know the reason. Either way, I have the result from recruiter and I can take my next action based on the result such as prepare for next round or apply at different organization.

### Async await
### [higher order functions](https://www.youtube.com/watch?v=80KX6aD9R7M&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ)
### [array methods](https://javascript.info/array-methods)
### [string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
### [arrow functions](https://javascript.info/arrow-functions-basics)
### [prototypical inheritance](https://javascript.info/prototypes)
`Senior Developer Stuff below`
### [generators](https://javascript.info/generators)
### [Dynamic imports](https://javascript.info/modules-dynamic-imports)

## [JS Desgin Patterns](https://betterprogramming.pub/javascript-design-patterns-25f0faaaa15)

https://github.com/leonardomso/33-js-concepts


## Lightning Aura Components

1. Events Types
1. Event Propagation
1. Component Bundle
1. Aura Methods
1. Aura Action
1. setStorable
1. setBackground
1. Interfaces
1. Limits
1. considerations


## Visualforce

1. View State - How to optimize? Transient keyword
1. Waiting State -
1. actionFunction
1. actionSupport
1. actionPollar
1. StandardController
1. CustomController
1. Page Reference Class
1. Extentions (Standard and Custom)

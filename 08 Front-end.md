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


### Lifecycle Hooks

- `constructor()`
- `connectedCallback()`
- `disconnectedCallback()`
- `errorCallback()`
- `render()`
- `renderedCallback()`

![image](https://user-images.githubusercontent.com/34469349/153795256-874fbf1f-325a-4df2-9a95-bf5c8cfcc0fc.png)


### Decorators

- `@api`
- `@wire`
- `@track`


### LWC Communication
   - [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel)
   - Custom Events
   - PubSub Limitations - can be accessed by components from other namespaces, cannot be used inside Visualforce
   - [Event propagation and phases](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.events_propagation)
   - [`lightning/empApi`](https://developer.salesforce.com/docs/component-library/bundle/lightning-emp-api/documentation)

### [Lightning Data Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_ui_api)
![image](https://user-images.githubusercontent.com/34469349/153461038-ce6ff1c6-288c-4ef0-888f-a479352d1654.png)

#### Standard LDS components

#### Difference between base lightning LDS component
![image](https://user-images.githubusercontent.com/34469349/153460813-da92e3b3-c78a-4346-a03e-19c7a992fdf1.png)

#### [Wire Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_wire_service_about)

#### [`lightning/ui*Api` Wire Adapters and Functions](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_ui_api)

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
    

### Advantages of LWC over Aura / Why do we need LWCs if we had Aura
1. **Standardization**
     - LWCs are built on top of web component that are natively supported by browsers. 
     - Because of this, the code that developer writes is already browser understandable and there is no need to transpile (convert) the code into browser understandable code. 
     - As a result of this, it is also very easy to integrate LWCs with outside applications. Also, it makes debugging easier since code is rendered as is.
    
2. **Performance**
    - Since there is no abstraction layer (transpiler), the LWCs are more likey to load faster and perform better compared to Aura components. 
    - In one [case study](https://developer.salesforce.com/blogs/2019/06/case-study-dreamhouse-gains-speed-by-switching-to-lwc), Aura components migrated to LWC showed anywhere between a 2-60% decrease in Experience Page Time (EPT).
    
3. **Code Reusability**
   - Unlike Aura, one or more LWCs can be imported and used as utilities in other LWCs. 
   - This makes it more reusable than Aura and you do not need to copy same come in each LWCs like we will have to do for Aura.

4. **Inbuilt Salesforce modules** 
   - As we know, LWCs supports `lightning/ui*Api` Wire Adapters and Functions that gives us ability to perform CRUD operations on a record as well as get object metadata, and get picklist values without having to call Apex.
   - Also LWCs support modules such as `@salesforce/schema` to import references to Salesforce objects and fields.
   - `@salesforce/userPermission` and `@salesforce/customPermission` - to check user permissions and custom permissions.
   - `@salesforce/user` - to get current user id and to check if user is guest user.
   - `@salesforce/community` - to get community info.
   - This property makes LWCs more agile than Aura and saves lots of efforts. 
   - Give example of Knowledge details component on case record page. How we eliminated the need of apex. If interviewer asks why did not you use base LDS component then tell that Knowledge object was not supported by LDS base component.

### [Lightning Locker Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.security_locker_service)


## Advance Concepts
1. [Lightning Web Securty](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.security_lwsec_architecture)
2. [Shadow DOM](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_dom)
3. [More Shadow DOM](https://developers.google.com/web/fundamentals/web-components/shadowdom)

### [Light DOM](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_light_dom)
   The Light DOM is simply the plain old DOM tree inside a HTML element.
   The term is only used in the context of web components to distinguish it from the Shadow DOM. I suppose the normal DOM was redefined as Light in contrast with    Shadow. 
   
### [Lightning Web Components Performance Best Practices](https://developer.salesforce.com/blogs/2020/06/lightning-web-components-performance-best-practices)

## Questions
1. [Explain the component structure of LWC component](#component-structure)
2. [What is LDS and what are the its advantages?](#advantages-of-lds)
3. How to communicate from parent LWC to child LWC and grand child LWC? How to access the child variables and methods?
4. How to communicate from child LWC to parent lwc and grand parent LWC? 
5. How to communicate between sibling LWCs? How to communicate between cousin LWCs?
6. Can you please explain LWC lifecycle and hooks?
7. Explain lightning locker service.
8. Explain lightning web security.
9. Explain all LWC decorators and their usage.

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

### https://javascript.info/nullish-coalescing-operator
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
### [prototypal inheritance](https://javascript.info/prototypes)
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
1. actionRegion
1. StandardController
1. CustomController
1. Page Reference Class
6. Extentions (Standard and Custom)

# Front-end

## Lightning Web Components

1. Component Structure
   The folder and its files must have the same name, including capitalization and underscores.

    `myComponent`

    - `├──myComponent.html` - HTML File (Optional)
    - `├──myComponent.js` - JavaScript File (Required)
    - `├──myComponent.js-meta.xml` - Configuration File (Optional)
    - `├──myComponent.css` - CSS File (Optional)
    - `|──myComponent.svg` - SVG Icon (Optional)
    - `|──shared_code.js` - JavaScript File (Optional - to share code)
    - `└──moreSharedCode.js` - JavaScript File (Optional - to share code)

1. Events

    - [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel)
    - Custom Events
    - PubSub -
        - Limitations - can be accessed by components from other namespaces, cannot be used inside Visualforce

1. [Lightning Data Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_ui_api)

![image](https://user-images.githubusercontent.com/34469349/153461038-ce6ff1c6-288c-4ef0-888f-a479352d1654.png)

   - Standard LDS components
**Difference between base lightning LDS component**
![image](https://user-images.githubusercontent.com/34469349/153460813-da92e3b3-c78a-4346-a03e-19c7a992fdf1.png)

   - [Wire Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_wire_service_about)
   - [`lightning/ui*Api` Wire Adapters and Functions](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_ui_api)


1. Calling Apex from LWC

    - Use case for calling apex imparatively.
    - Call apex imparatively and pass parameters
    - [Client Side Caching](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.apex_result_caching) (cacheable=true & refreshApex())

1. [HTML Template Directives](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_directives)

1. Decorators

    - `@api`
    - `@wire`
    - `@track`

1. Lifecycle Hooks

    - `connectedCallback()`
    - `constructor()`
    - `disconnectedCallback()`
    - `errorCallback()`
    - `render()`
    - `renderedCallback()`

1. Slots - when slots should be used? give an example of an use case so

1. `@salesforce` Modules

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
    

1. [Lightning Locker Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.security_locker_service)

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

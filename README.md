# A Guide for Salesforce Interview Preparation

## Data Modelling

1. Standard Objects -

    - What are the **main** Sales cloud objects? Understand the relationship between them.
      Userful Resources -

    1. High Level Overview- https://www.youtube.com/watch?v=SdQ3cQhSgEk
    1. In a little depth - https://www.youtube.com/watch?v=nj8KGwAL49k
    1. For Sales Cloud Consultant - https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_majors.htm

    - What are Service objects? Understand the relationship between them.

    1. https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_support.htm

1. Custom Objects
1. Object Relationships
1. Fields and their types
1. Indexable fields
1. Custom Setting
1. Custom Medatada

## Security Model

1.  Org Level Security

    -   Login IP Ranges
    -   Login Hours

1.  Object Level Security

    -   Profiles
    -   Permission Sets
    -   Permission Set Groups
    -   [View All, Modify All, View All Data, Modify All Data](https://help.salesforce.com/articleView?id=sf.users_profiles_view_all_mod_all.htm&type=5)
        -   **View/Modify All** - The “View All” and “Modify All” permissions ignore sharing rules and settings, allowing administrators to grant access to records associated with a given object across the organization.
        -   **View/Modify All Data** - Managing all data in an organization; for example, data cleansing, deduplication, mass deletion, mass transferring, and managing record approvals.

1.  Field Level Security

1.  Record Level Security

    1.  Organization Wide Defaults

    1.  Role Hierarchies

    1.  Sharing Rules

        -   Ownership Based
        -   Criteria Based

    1.  Manual Sharing

    1.  [Apex Managed Sharing](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_creating_with_apex.htm)

**Resources** -

1. [Salesforce Data Securirty Model Explained](https://developer.salesforce.com/blogs/developer-relations/2017/04/salesforce-data-security-model-explained-visually.html)

## Automation Tools

1. Workflows

    - Workflow Actions
    - Time-based workflows and considerations

1. Process Builders

    - Process Builder Actions
    - Limitations

1. Flows

1. Approval Process

## Apex

-   #### Triggers

    -   [Context Variables](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables.htm)
    -   [Context Variable Considerations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables_considerations.htm)
    -   [Triggers and Order of Execution](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_order_of_execution.htm)

        1. System Validation Rules
        1. Apex Before Triggers
        1. Custom Validation Rules
        1. Duplicate Rules
        1. Apex After Triggers
        1. Assignment Rules
        1. Auto-Response Rules
        1. Workflow Rules
        1. Processes
        1. Escalation Rules
        1. Roll-Up Summary Fields

-   ###### Programming Concepts

    -   Collections (List, Set, Map)
    -   Exception Handling

-   ###### Keywords (Frequently Used)

    -   [`with sharing`, `without sharing`, and `transient sharing` - Link](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_keywords_sharing.htm)
    -   `transient` vs. `static`

-   ###### Interfaces (Frequently Used)

    -   Schedulable
    -   Batchable
    -   Queueable
    -   HttpCalloutMock
    -   Custom Interfaces

-   ###### [Asynchronous Apex](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_async_overview.htm)

    -   Batch Apex

        -   Can we call another batch class from a batch class?
        -   Can we call future method from a batch? How?
        -   Can we make a callout from a batch apex? How?
            implement Database.AllowsCallouts
        -   What is the number of maximum batch Apex jobs that can be queued or can be active concurrently?
            5 jobs
        -   What is the default batch size?
            200
        -   What's the maximum batch size that you can set?
            (2000 in Database.executeBatch() method. If set to more than 2000, the batch size becomes 200 by default.)
        -   What are the governor limits for a batch apex?

    -   Future Methods

        -   Can we call future method from another future method
        -   Can we make a callout from a future method? How? @future(callout=true)
        -   How many future methods are allowed per transaction?
        -   What type of parameters does future method accepts? Premitives only. no sObjects.

    -   Scheduled Apex

        -   What is the maximum number of Apex classes scheduled concurrently? 100

    -   Queueable Apex

-   ###### DML Statements

    -   Insert
    -   Update
    -   Upsert
    -   Delete
    -   Undelete
    -   Merge

-   ###### Class Reference (Frequently Used)

    1.  Schema Class
    1.  Database Class
    1.  System Class
    1.  Limit Class
    1.  Test class

-   #### [Annotations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_annotation.htm)

    @AuraEnabled
    @Future
    @InvocableMethod  
    @InvocableVariable
    @TestSetup
    @TestVisible
    @IsTest
    @RemoteAction

## SOQL & SOSL

SOQL Optimization

## Lightning Web Components

-   Component Structure
    The folder and its files must have the same name, including capitalization and underscores.

    `myComponent`

    -   `├──myComponent.html` - HTML File (Optional)
        `├──myComponent.js` - JavaScript File (Required)
        `├──myComponent.js-meta.xml` - Configuration File (Optional)
        `├──myComponent.css` - CSS File (Optional)
        `└──myComponent.svg` - SVG Icon (Optional)
        `├──shared_code.js` - JavaScript File (Optional - to share code)
        `└──moreSharedCode.js` - JavaScript File (Optional - to share code)

-   Events
-   [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel)
-   [Lightning Data Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_ui_api)
-   [Lightning Locker Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.security_locker_service)
-   [Wire Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_wire_service_about)
-   [Client Side Caching](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.apex_result_caching) (cacheable=true & refreshApex())

-   [`lightning/ui*Api` Wire Adapters and Functions](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_ui_api)

-   [HTML Template Directives](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_directives)

-   Decorators

    -   `@api`
    -   `@wire`
    -   `@track`

-   Lifecycle Hooks

    -   `connectedCallback()`
    -   `constructor()`
    -   `disconnectedCallback()`
    -   `errorCallback()`
    -   `render()`
    -   `renderedCallback()`

-   `@salesforce` Modules

    -   `@salesforce/apex`
    -   `@salesforce/apexContinuation`
    -   `@salesforce/client/formFactor`
    -   `@salesforce/community`
    -   `@salesforce/contentAssetUrl`
    -   `@salesforce/label`
    -   `@salesforce/messageChannel`
    -   `@salesforce/resourceUrl`
    -   `@salesforce/schema`
    -   `@salesforce/user`
    -   `@salesforce/userPermission`
    -   `@salesforce/customPermission`

## Lightning Aura Components

-   Events Types
-   Event Propagation
-   Component Bundle
-   Aura Methods
-   Aura Action
-   setStorable
-   setBackground
-   Interfaces
-   Limits
-   considerations

## Visualforce

-   View State
-   Waiting State
-   actionFunction
-   actionSupport
-   StandardController
-   CustomController
-   Page Reference Class
-   Extentions (Standard and Custom)

## Integration

Integration - done
webservice
callouts
Limits
considerations

Emails -
Limits
Considerations

Complex queries in the standard object. master-detail / lookup
commonly occurring code scenarios

# Misc

-   Record Row Lock
-   Data Skew
    -   Ownership Skew - Large number of records (more than 10000) are assigned to single user
    -   Lookup Skew - Large number of records are associated with single record.
-   [You have uncomitted work pending](https://help.salesforce.com/articleView?id=000328873&type=1&mode=1)
-   [Maximum CPU time exceeded](https://help.salesforce.com/articleView?id=000339361&type=1&mode=1)
    -   Use Map Based Queries
    -   Perform Aynchronous Operations
    -   Aggregate SOQL usage
    -   Only take necessary data and run a loop

# Common Interview Questions

1. Write a batch class
2. Write a trigger to not allow multiple accounts insertion with the same Name (Answer - We can use adderror() method)
3. Write a trigger on Account to update all the related contacts email with the associated account's email
4. Contact and Account have lookup relationship but when we delete an account all the associated contacts are deleted. Why? (Answer - Contacts are deleted because their lookup relationship with the Account is a "cascade delete" relationship. Cascade deletes don't run triggers as well.)
5. Can we call a batch from another batch and if yes then how? How can we write test classes for such batches?
6. Can we do callouts from a batch? If yes, then what is the prerequisite for that?
7. How to write a test class for a batch? How it is different from other apex test classes? How can we run a batch in test class?
8. What are the options available to run a batch?
9. What is a stateful batch?
10. Apex best practices
11. Order of execution in an apex transaction? What are system validations?
12. Why we should bulkify our code?
13. What is the difference between insert DML statement and Database.insert
14. If we have 2 savepoints and we rollback first savepoint, what happens to the second savepoint?
15. What is custom setting and custom metadata? How they are different? Types of custom settings and the difference between them.
16. What is the difference between REST and SOAP API?
17. What is the difference between the POST and PUT method in REST? Can we perform the update using the POST method and if yes then how it is different from PUT?
18. What are governor limits?
19. How lightning is different from classic? How lightning components are different from VF pages?
20. What are the events in lighting and what's the difference between them?
21. Can we directly convert VF pages to lighting components?
22. What is lighting out? What is @AuraEnabled annotation?
23. Can we use Angular is the lighting? If yes, what is the prerequisite for that?
24. Can we modify the records in the after events?
25. What can be after deleting of a record? Can we modify it?
26. How do we ensure object and field-level security in lighting? (Answer - using lighting data service)
27. Security model of the salesforce.
28. How do you handle NullPointerException in apex?

###### [Google Interview Experience](https://www.youtube.com/watch?v=MN1jxnmqFhM)

Apex coding questions
Triggers
LWCs
Aysnc apex
Integration - low confidence - convert
mock callout testing
batch scenario
approval process
governor limits
apex governer limits

Interview Questions for experience less than 2 years - https://www.youtube.com/watch?v=vRZwFvvCbFk

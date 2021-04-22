# Salesforce Developer Interview Preparation Guide

---

## Table of Contents

1. Technical Section
    1. Data Modelling
    1. Security Model
    1. Automation tools
    1. Apex
        1. Triggers
        1. Programming Concepts
        1. Keywords (Frequently Used)
        1. Interfaces (Frequently Used)
        1. Asynchronous Apex
        1. Class Reference (Frequently Used)
        1. Annotations
    1. SOQL & SOSL
    1. Lightning Web Components
    1. Lightning Aura Components
    1. Visualforce
    1. Integration
    1. Misc
    1. FA Technical Qs
1. Behavioural Section
    1. How to answer behavioral questions
    1. Tell me about yourself
    1. Why Do You Want to Work Here?
    1. Question to ask interviewer after the interview
    1. FA Behavioural Qs
1. Interview Experiences
    1. PayPal
    1. Zoom
    1. Expedia
    1. Workday

## Inteview Process

| Rounds               | Competency                                                    |
| -------------------- | ------------------------------------------------------------- |
| Screening (Optional) | Screening Round                                               |
| Round 1              | Technical Coding                                              |
| Round 2              | Technical depth, Coding and Communication Skills/Cultural Fit |
| Round 3              | Problem Solving/Design                                        |
| Round 4              | Business Acumen/Collaboration (Behavioural)                   |

---

# Technical Section

## Data Modelling

1. Standard Objects -

    - What are the **main** Sales cloud objects? Understand the relationship between them.
      Userful Resources -

        1. [High Level Overview](https://www.youtube.com/watch?v=SdQ3cQhSgEk)
        1. [In a little depth](https://www.youtube.com/watch?v=nj8KGwAL49k)
        1. [For Sales Cloud Consultant](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_majors.htm)

    - What are Service objects? Understand the relationship between them.

        1. [SOAP API Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_support.htm)

    - Account-Contact relationship is a special cascase delete Lookup relationship.

1. Custom Objects
1. Object Relationships

    - Lookup
        - Lookup provides 2 option on deletion of the record
    - Master-Detail

        - Cascade delete and undelete do not invoke the triggers on the child records.
        - Sharing options available for the child records at the time of creating field
            - Read Only
            - Read/Write
        - Reparenting

    - Hierarchy (Only available for User obect)

    - [Guide to Salesforce Relationship Types – and When to Use Them!](https://www.salesforceben.com/guide-to-salesforce-relationship-types-and-when-to-use-them/)

    - [Unable to lock row - Record currently unavailable errors](https://help.salesforce.com/articleView?id=000338933&type=1&mode=1)

1. Fields and their types
1. Indexable fields

    - Default -
        - Primary keys (ID, Name, and Owner fields).
        - Foreign keys (lookup or master-detail relationship fields).
        - Audit dates (such as SystemModStamp).
        - Custom fields marked as External ID or Unique
    - Custom -
        - Auto Number
        - Email
        - Number
        - Text

1. Custom Settings and Custom Medatada, thier differences and limitations.

1. What is Data Skews? What are the types?
    - Ownership Skew - Large number of records (more than 10000) are assigned to single user
    - Lookup Skew - Large number of records are associated with single record.

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

        -   Check grant access using role hierarchies in Sharing Settings (OWD)

    1.  Sharing Rules

        -   Ownership Based
        -   Criteria Based

    1.  Manual Sharing

    1.  [Apex Managed Sharing](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_creating_with_apex.htm)

        -   What is the use for using apex managed sharing? Let us say you create/update an account and based on total Amount of the related opportunities you need to assign that account to particular Sales Rep programatically. This cannot be achieved using any of the declarative tools.

    1.  [Salesforce Data Securirty Model Explained](https://developer.salesforce.com/blogs/developer-relations/2017/04/salesforce-data-security-model-explained-visually.html)

## Automation Tools

1. Workflows

    - Workflow Actions
    - Difference between everytime created and edited and subsequently meet the criteria
    - Time-based workflows and considerations
    - Limitations - Cannot be executed before record is modified.

1. Process Builders

    - Process Builder Actions
    - Limitations

1. Flows

1. Approval Process

## Apex

### Triggers

1. [Context Variables](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables.htm)
1. [Context Variable Considerations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables_considerations.htm)
1. [Triggers and Order of Execution](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_order_of_execution.htm)

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

### Programming Concepts

1. Collections (List, Set, Map)
1. Exception Handling

### Keywords (Frequently Used)

1. [`with sharing`, `without sharing`, and `inherited sharing` - Link](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_keywords_sharing.htm)
1. `transient` vs. `static`

### Interfaces (Frequently Used)

1. Batchable
1. Queueable
1. Schedulable
1. HttpCalloutMock
1. Custom Interfaces

### [Asynchronous Apex](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_async_overview.htm)

1.  Batch Apex

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

1.  Future Apex

    -   Can we make a callout from a future method? How? @future(callout=true)
    -   Can we call future method from another future method? No.
    -   Can we call future method from batch apex? No.
    -   Can we call future method from queueable apex? Yes, only 1 is allowed.
    -   How many future methods are allowed in single transaction? 50.
    -   What type of parameters does future method accepts? Premitives only. no sObjects.Why?

1.  Queueable Apex

    -   Maximum number of queued apex jobs? 50.

1.  Scheduled Apex

    -   What is a cron expression?
    -   What is the maximum number of Apex classes scheduled concurrently? 100

### Class Reference (Frequently Used)

1.  Schema Class

    -   When should you use schema class?

1.  Database Class

    -   What is use case of savepoints?
    -   What is use case of SaveResults, UpdateResults, DeleteResults etc.

1.  System Class
    -   When should you use runAs()? - Know about isTestRunning, isFuture, isBatch, isQueueable?
1.  Limit Class
1.  Test class
    -   startTest() - stopTest() - @isTest - seeAllData - Setup Objects

### [Annotations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_annotation.htm)

    @AuraEnabled
    @Future
    @InvocableMethod
    @InvocableVariable
    @TestSetup
    @TestVisible
    @IsTest
    @RemoteAction

## SOQL & SOSL

1. Try writing complex queries using **Apex** -

    - Query all accounts with all related contacts
    - Query all accounts with count of all related contacts
    - Query all accounts and its opporutnities that have more than 2 opporunitites
    - Query all accounts with all related opporutnities where opporunity amount is more than 10000
    - Query all accounts with sum of its all opportunity amounts
    - find average amount of all opportunities in the org
    - find min amount of all opp in the org
    - find max amount of all opp in the org
    - Query all opportunities where account country is USA (check actual valuesin system first)
    - query all opportunities whose accounts have more than 2 opportunities

1. SOQL Optimization

    - [Write Efficient Queries](https://trailhead.salesforce.com/en/content/learn/v/modules/database_basics_dotnet/writing_efficient_queries) - Must Read

    - [Maximizing the Performance of Force.com SOQL, Reports, and List Views](https://developer.salesforce.com/blogs/engineering/2013/07/maximizing-the-performance-of-force-com-soql-reports-and-list-views.html)

    ##### Very Advanced Stuff Below (Architect level, but it deserves a read)

    - [SOQL Best Practices: Nulls and Formula Fields](https://developer.salesforce.com/blogs/engineering/2013/02/force-com-soql-best-practices-nulls-and-formula-fields.html)

    - [SOQL Performance Tips: LastModifiedDate vs SystemModStamp](https://developer.salesforce.com/blogs/engineering/2014/11/force-com-soql-performance-tips-systemmodstamp-vs-lastmodifieddate-2.html)

1. Learn about Query Planner Tool

    - [Query Plan Tool (How To & FAQ)](https://help.salesforce.com/articleView?id=000334796&type=1&mode=1)

    ##### Very very advance, salesforce implementation level stuff below (nothing to lose even if you don't read)

    - [Query and Search Optimization Cheat Sheet (pdf)](http://resources.docs.salesforce.com/194/0/en-us/sfdc/pdf/salesforce_query_search_optimization_developer_cheatsheet.pdf)

## Lightning Web Components

1. Component Structure
   The folder and its files must have the same name, including capitalization and underscores.

    `myComponent`

    - `├──myComponent.html` - HTML File (Optional)
      `├──myComponent.js` - JavaScript File (Required)
      `├──myComponent.js-meta.xml` - Configuration File (Optional)
      `├──myComponent.css` - CSS File (Optional)
      `|──myComponent.svg` - SVG Icon (Optional)
      `|──shared_code.js` - JavaScript File (Optional - to share code)
      `└──moreSharedCode.js` - JavaScript File (Optional - to share code)

1. Events

    - [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel)
    - Custom Events
    - PubSub -
        - Limitations - can be accessed by components from other namespaces, cannot be used inside Visualforce

1. [Lightning Data Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.data_ui_api)

    - Standard LDS components
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


## Integration

What are types of Integration?
    - Inbound
    - Outbound
    
Communication types - 
    - Synchronous
    - Asynchronous

What type of Integrations you should know?

1. Workflow outbound messages - outbound
1. Apex callouts (outbound) and Web Services (inbound)
1. Salesforce Connect - both inbound and outbound depending on use case
    Salesforce Connect provides seamless integration of data across system boundaries by letting your users view, search, and modify data that’s stored outside your Salesforce org. For example, perhaps you have data that’s stored on premises in an enterprise resource planning (ERP) system. Instead of copying the data into your org, you can use external objects to access the data in real time via web service callouts.
    Use Salesforce Connect when:
    -   You have a large amount of data that you don’t want to copy into your Salesforce org.
    -   You need small amounts of data at any one time.
    -   You want real-time access to the latest data.

Authentication and Authorization - 
1. OAuth flows
    - Web Server flow
    - JWT Server to Servier integration
    
REST Methods - 
1. PUT vs PATCH
    - Short difference - PUT does an UPSERT with complete payload.
      Meaning if the request payload is -
      Request endpoint - /person/1
      {
      name : "John Doe",
      age : 30
      }

    the PUT operation will check if person with id 1 exists, if yes then it will update the name and age.
    if notm then it will create new person at id 1.

    However,
    PATCH modifies existing data with given payload.
    Meaning, Request endpoint - /person/1
    payload-
    {
    name: "Jane Doe"
    }
    The path will only update the name and not whole object.
    Also, if the resource does not exists, then it will fail.
    
1. [Architect Stuff] Platform Events - https://www.apexhours.com/integrating-with-salesforce-using-platform-events/

## Misc

-   [Unable to lock row - Record currently unavailable errors](https://help.salesforce.com/articleView?id=000338933&type=1&mode=1)

-   [Maximum CPU time exceeded](https://help.salesforce.com/articleView?id=000339361&type=1&mode=1)

    -   Use Map Based Queries
    -   Perform Aynchronous Operations
    -   Aggregate SOQL usage
    -   Only take necessary data and run a loop

-   [You have uncomitted work pending](https://help.salesforce.com/articleView?id=000328873&type=1&mode=1)

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


### FA Technical Qs

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

https://www.sfdc99.com/2014/12/18/common-interview-questions-for-salesforce-developers/

---

# Behavioural Section

1. [How to answer behavioral questions](https://www.youtube.com/watch?v=lJOf8EtjV8g)
   Answer all the question using the STAR methodology.
   Situation - The time when something you did and the thing you did.
   Task - What was the goal
   Action - What did you do?
   Result - What was the outcome?

1. Tell me about yourself

    Explain -
    Current Role (shows you are professional. Interviewer is not interested in your personal life and what is your hometown, this is irrelavant)

    Success Metrics (shows you are result oriented, confident and capability)

    Recent Achievement that you are proud of (keeps the interviewer enagaed with your stroy and makes her/him curious about you. DO NOT TRY TO IMPRESS)

    Methods-
    Past, Present, Future method
    Highlight Method

    Must Watch -
    https://www.youtube.com/watch?v=es7XtrloDIQ

1. Why Do You Want to Work Here?

1. Question to ask interviewer after the interview

    - Ask about themselves
    - Ask questions about the role
    - Ask questions about the company

---

### FA Behavioural Qs

1. How do you handle criticism - introspection and work on it
1. How do you criticize - let them know in a way that will help them getting better, for ex. what would have happened good if they did/did not have done that.
1. What is the worst feedback you have got - complaining (was not saying no, got burned out)
1. What does your past work aligns with this job role?
1. How will you handle the situation where you got into an argument with co-worker over implementation of a feature? What if manager supports the person with their decision? And What will be your reaction after something goes wrong with the co-worker's solution in Production and you know your solution would have worked? (the classic Told you so moment)

---

## Interview Experiences

#### 1. PayPal

##### Round 1 (Problem Solving + Technical Coding + Platform Knowledge) -

|      |                  |
| ---- | ---------------- |
| With | Senior Developer |
| Time | 1 Hour           |

1. Tell me about your current role in the team.
1. Write a code to store number of occurences of each integer in array.
1. What are multiple ways to call apex in lwc?
    - wire and imparatively.
1. How to pass parameters to apex method from lwc?
1. How to show data in template from JS? How to get particular field?
1. What are Promises in JS?
1. Write a trigger for given scenario.
   A custom Shipment object has a lookup on Account object and a has a custom field Quantity.
   Account has a custom field called Total Shipment Quantity which is sum of quantites of all the related shipments of the account.
   write a trigger to calculate the sum of all shipment quantities and store in Total Shipment Quantity field on Account.
1. How to communicate from child LWC to Parent LWC?
1. Any questions for me?

##### Round 2 (Technical depth, Coding) -

|      |                |
| ---- | -------------- |
| With | Lead Developer |
| Time | 1 Hour         |

1. Tell me about your current role in the team.
1. Write a lwc to get data from apex and show the data in the remplate

Student\_\_c Object -

| Degree   | Name     | Age |
| -------- | -------- | --- |
| B. Tech. | Ross     | 30  |
| MBA      | Monica   | 28  |
| B. Tech. | Chandler | 30  |
| MBA      | Rachel   | 27  |
| MA       | Joey     | 29  |
| MBA      | Pheobe   | 28  |

**Excpeted Output in LWC**

<table>
    <thead>
        <tr>
            <th>Degree</th>
            <th>Name</th>
            <th>Age</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=2>B. Tech.</td>
            <td>Ross</td>
            <td>30</td>
        </tr>
        <tr>
            <td>Chandler</td>
            <td>30</td>
        </tr>
        <tr>
            <td rowspan=3>MBA</td>
            <td>Monica</td>
            <td>28</td>
        </tr>
         <tr>
            <td>Rachel</td>
            <td>27</td>
        </tr>
        <tr>
            <td>Pheobe</td>
            <td>28</td>
        </tr>
         <tr>
            <td>MA</td>
            <td>Joey</td>
            <td>29</td>
        </tr>
    </tbody>
</table>

1. From above table, make the age field editable and whenever any age is modified, related name should be displayed in alert

1. How to establish communication betn two non related lwcs? assume they are on the account record details page.
   Ans - lms,pubsub,custom events

1. How to securely store api keys?
   Ans - Named credentials

1. What is the difference between future and queueable apex?

1. Why does the future method not allow non primitive data types whereas queueable allowes.
   Ans - The complex data types are passed by reference and not by value so by the time the future method gets executed, the state of the complex types might get changed and the future method might still refer to the old data

1. Whenever an Account is updated, another web application should be informed about the record change. this should be done immidiately when account is updated.
    1. In how many ways can we implement this?
       Ans - Workflow Outbound Message, Trigger, Platform Events.
    1. What if we have to do this asynchronously?
       Ans - Batch, Platform Events (check if this is possible)
1. Any questions for me?

##### Round 3 (System Design) -

|      |                |
| ---- | -------------- |
| With | Staff Engineer |
| Time | 1 Hour         |

1. Tell me about your current role in the team.
1. Given an employee table, design a system that prints org chart of the employees with thier manager and imidiate reportees (like in Role Hierarachy in salesforce).

Functionalities of the Org Chart -

1. We can find employee by thier name
1. Clicking on the employee name will show a tree structure that shows the manager of the employee and it's immidiate employees.
1. What is your tech stack? (Aura/LWC, Apex etc.)
1. How many components will be there
1. Give end-to-end design and explain how it will work.

| Employee Id | Name     | Manager Id |
| ----------- | -------- | ---------- |
| 1           | Ross     |            |
| 2           | Monica   | 1          |
| 3           | Chandler | 2          |
| 4           | Rachel   | 1          |
| 5           | Joey     | 3          |
| 5           | Pheobe   | 2          |

Follow up questions -

1. Will you build new component right away?
1. Will you use any external libraries to present data? If yes name what libraries will you use?
1. What if there is already a packge on AppExchange that provides this functionality?

1. Can we package code in Apex?
1. Any questions for me?

##### Round 4 (Behavioural) -

|      |                |
| ---- | -------------- |
| With | Hiring Manager |
| Time | 1 Hour         |

1. When was a time when you took some initiative and it was implemented? (this is a leadership question)
1. Any questions for me?

---

#### 2. Zoom

##### Round 1 (Screening + Platform Knowledge ) -

|      |                |
| ---- | -------------- |
| With | Hiring Manager |
| Time | 1 Hour         |

1. Tell me about your current role and responsibilities.
1. If I update the child record in MD relationship, what impact does it have on the parent record? (It locks the parent record)
1. What is the row lock timout limit? (a record will be locked for max 10 seconds and then error will be thrown)
1. How to avoid row lock on account when doing bulk data load (updating more then 20 million reocrds) on one of the chid objects of the account.
1. Why did you choose LWC over Aura?
1. Differentiate between future, batch and queueable.
1. Have you come across any governor limits? how did you tackle them?
1. What are some best practices in Salesforce?
1. Have you worked on apex? what have you done in apex?
1. When did you use batch apex? what was the use case?
1. What is the difference betn list and map?
1. Have you faced any challanges in the past and how did you overcame those?
1. Why did you particualry for Batch Data Activity for Knowledge Article Migration and why didn't choose Bulk API?
1. Why do you want to leave your current organization?
1. Any questions for me?

---

#### 3. Expedia

##### Round 1 (Screening + Platform Knowledge )

|      |                             |
| ---- | --------------------------- |
| With | Online HackeRrank           |
| Time | 30 Minutes for 30 Questions |

Questions were on the Salesforce topics such as Apex code output, Triggers, SOQL, Visualforce, LWC and LWC Testing, Integration scenarios.
These were pretty basic and simple questions with one or advanced questions. Anyone with 1.5+ experince should be able to answer.

#### 4. Workday

##### Round 1 ()

|      |     |
| ---- | --- |
| With |     |
| Time |     |

RoadMap -

1. LinkedIn Profile
2. Resume
3. Technical Skills
4. Behavioural

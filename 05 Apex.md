# Apex 

1. [Collections (List, Set, Map)](https://developer.salesforce.com/blogs/2021/10/mastering-apex-collections)
1. Exception Handling - https://developer.salesforce.com/blogs/2017/09/error-handling-best-practices-lightning-apex

### Keywords (Frequently Used)

1. [`with sharing`, `without sharing`, and `inherited sharing`](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_keywords_sharing.htm)

### Class Reference (Frequently Used)

1.  Schema Class

1.  Database Class

    - What is use case of savepoints?
    - What is use case of SaveResults, UpdateResults, DeleteResults etc.

1.  System Class

    - When should you use runAs()? - Know about isTestRunning, isFuture, isBatch, isQueueable?

1.  Limit Class

1.  Test class

    - startTest() - stopTest() - @isTest - seeAllData - Setup Objects

1.  [Apex Best Practices](https://developer.salesforce.com/blogs/developer-relations/2015/01/apex-best-practices-15-apex-commandments.html) - This is a must read. you should atleast know 5 apex best practices.

### [Annotations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_annotation.htm)

    @AuraEnabled
    @Future
    @InvocableMethod
    @InvocableVariable
    @TestSetup
    @TestVisible
    @IsTest
    @RemoteAction

# [Asynchronous Apex](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_async_overview.htm)

## Asynchronous vs Synchronous
### Asynchronous
   - Actions that will not block the transaction or Process
   - Duration is not priority
   - Higher Governor limits

### Synchronous
   - Quick and Immediate actions
   - Transactions are immediate and serial
   - Normal Governor Limits

## Ways to use asynchronous processing 
   - Schedule & Batch jobs
   - Queues
   - @future
   - Change Data Capture – Apex Triggers (Summer ’19)
   - Platform Events – Event Based
   - Continuations (UI)
   - 
### Why to use Anyc process Scenarios
Integrations to External Applications
Long running processes
Mixed DML Operations
Large volume of data loads & transactions


### Future Method
A “set it and forget it” method
Call it and the async job is launched
No ability to monitor the job
Cannot chain @future calls
A public static method, decorated with @future
Arguments: Primitives (Integer, String, etc.)
Collections of primitives (List, Map, Set)
NOT SObjects or Apex objects
You can use JSON.serialize() and pass in a String
Returns void


### Queueable Apex
A class and method that can be added to the queue to be executed
It’s monitorable and abortable
It’s chainable
A public class that implements the Queueable interface
Includes an execute method that accepts only a QueueableContext parameter
The execute method can access instance properties for the class
Returns void
Launch by calling System.enqueueJob(cls) with an instance of the class.
Returns an AsyncApexJob Id


### Batch Apex
A technique designed specifically for:
Processing large numbers of records
Doing more work than can be done in a single transaction
It’s monitorable and abortable
A global class that implements the Database.Batchable interface
Includes:

Start method – identifies the scope (list of data to be processed)

Execute method – processes a subset of the scoped records

Finish method – does any post-job wrap-up

#### Additional interfaces:
Database.Stateful
Database.AllowsCallouts

Launch by calling Database.executeBatch(cls) with an instance of the class and an optional scope size
Default scope size is 200
Max scope size is 2,000
Returns an AsyncApexJobId
Schedulable Class
A global class that implements the Schedulable interface
Includes an execute method
Schedule by calling
System.Schedule(‘job name’, cron expression, cls)
Cron expression can be complex
Returns a CronTrigger Id
Can also schedule via the Salesforce UI
seconds minutes hours   day_of_month   month   day_of_week   optional_year
Run at 30 minutes past midnight on Jan 1 every year

GeocodingSchedulable cls = new GeocodingSchedulable();
System.Schedule('Geocode on Jan ',  '0  30  0  1  1  ?  *', cls);

Run every hour
System.Schedule('Geocode hourly', '0 0  *  *  *  ?  *', cls);


### Questions
1. Batch Apex
   - Can we call another batch class from a batch class? - Yes, it is called batch chaining
   - Can we call future method from a batch? - No we cannot call a future method from a batch
   - Can we make a callout from a batch apex? How?
      implement Database.AllowsCallouts
   - What is the number of maximum batch Apex jobs that can be queued or can be active concurrently?
      5 jobs
   - What is the default batch size?
      200
   - What's the maximum batch size that you can set?
      (2000 in Database.executeBatch() method. If set to more than 2000, the batch size becomes 200 by default.)
   - What are the governor limits for a batch apex?
   - How to use AggregateResult in batch?
   - When to use Interable interface in batch apex?

1.  Future Apex

    - Can we make a callout from a future method? How? @future(callout=true)
    - Can we call future method from another future method? No.
    - Can we call future method from batch apex? No.
    - Can we call future method from queueable apex? Yes, only 1 is allowed.
    - How many future methods are allowed in single transaction? 50.
    - What type of parameters does future method accepts? Premitives only. no sObjects.Why?

1.  Queueable Apex

    - Maximum number of queued apex jobs? 50.

1.  Scheduled Apex

    - What is a cron expression?
    - What is the maximum number of Apex classes scheduled concurrently? 100


### When should we use which asynchronous apex
![image](https://user-images.githubusercontent.com/34469349/152400033-a64f6099-4c49-48bf-92e0-b9b4cf57b732.png)


### Important Interfaces (Frequently Used)

1. Database.Batchable - To impletement batch class
2. Database.Stateful - To maintain the state of variable across multiple batches
3. Database.AllowsCallouts - To make callouts from batch apex
4. Database.RaisesPlatformEvents - To publish platform events from batch
5. Queueable - To implement queueable class
6. Schedulable - To implement schedular class 
7. HttpCalloutMock - To mock http request
8. Callable - Enables developers to use a common interface to build loosely coupled integrations between Apex classes or triggers, even for code in separate packages.
9. Custom Interfaces

- [Unable to lock row - Record currently unavailable errors](https://help.salesforce.com/articleView?id=000338933&type=1&mode=1)

- [Maximum CPU time exceeded](https://help.salesforce.com/articleView?id=000339361&type=1&mode=1)

  - Use Map Based Queries
  - Perform Aynchronous Operations
  - Aggregate SOQL usage
  - Only take necessary data and run a loop

- [You have uncomitted work pending](https://help.salesforce.com/articleView?id=000328873&type=1&mode=1)
- Mixed DML Statement
- [Mixed DML Operations in Test Methods](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_dml_non_mix_sobjects_test_methods.htm)
- [sObjects That Cannot Be Used Together in DML Operations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_dml_non_mix_sobjects.htm)

### [SOLID Principles](https://www.youtube.com/watch?v=yxf2spbpTSw)

# Object Oritented Concepts

# interface vs abstract vs virtual

CODING PRINCIPLES -


# [Apex Design Patterns](https://salesforcecookcode.wordpress.com/2021/02/26/apex-design-patterns/)
  - Singleton – restricts the instantiation of a class to one “single” instance only within a single transaction context.
  - Strategy – lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.
  - Decorator – allow you to add new functionality to an existing object without altering its structure.
  - Facade – hides the complexity of the system and provides simple interface.
  - Composite – lets you compose objects into tree structures and then work with these structures as if they were individual objects.
  - Bulk State Transition – used to perform bulk actions efficiently based on change of state of one or more records.


# [Apex Enterprise Patterns](https://www.apexhours.com/apex-enterprise-patterns/)
  - [Apex Enterprise Patterns — Separation of Concerns](https://andyinthecloud.com/2012/11/16/apex-enterprise-patterns-separation-of-concerns/)
  - [Apex Enterprise Patterns — Selector Layer](https://andyinthecloud.com/2013/09/09/apex-enterprise-patterns-selector-layer/)
  - [Apex Enterprise Patterns — Domain Layer](https://andyinthecloud.com/2013/04/24/apex-enterprise-patterns-domain-layer/)
  - [Apex Enterprise Patterns — Service Layer](https://andyinthecloud.com/2013/02/11/apex-enterprise-patterns-service-layer/)
  - [Apex Enterprise Patterns — Unit Of Work](https://andyinthecloud.com/2013/06/09/managing-your-dml-and-transactions-with-a-unit-of-work/)
  - [Apex Enterprise Patterns — Unit Of Work](https://andyinthecloud.com/2014/07/17/doing-more-work-with-the-unit-of-work/)
  - [Apex Enterprise Patterns — FinancialForce Apex Common Updates](https://andyinthecloud.com/2014/06/28/financialforce-apex-common-updates/)

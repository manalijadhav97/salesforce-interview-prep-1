# Object Oritented Concepts

## Inheritance
## Polymorphism
## Abstraction
## Encapsulation

# [interface vs abstract vs virtual](https://salesforceprofs.com/abstract-virtual-interface-in-apex/)

# [SOLID Principles](https://www.youtube.com/watch?v=yxf2spbpTSw)
  ## The Single Responsibility Principle
   The Single Responsibility Principle states that a class should do one thing and therefore it should have only a single reason to change.
   
  ## Open-Closed Principle
   The Open-Closed Principle requires that classes should be open for extension and closed to modification.
   
   Modification means changing the code of an existing class, and extension means adding new functionality.
   
  ## Liskov Substitution Principle
   The Liskov Substitution Principle states that subclasses should be substitutable for their base classes.

   This means that, given that class B is a subclass of class A, we should be able to pass an object of class B to any method that expects an object of class A and the method should not give any weird output in that case.
   
  ## Interface Segregation Principle
   Segregation means keeping things separated, and the Interface Segregation Principle is about separating the interfaces.
   
  ## Dependency Inversion Principle
   The Dependency Inversion principle states that our classes should depend upon interfaces or abstract classes instead of concrete classes and functions.

https://www.freecodecamp.org/news/solid-principles-explained-in-plain-english/

# [Apex Design Patterns](https://salesforcecookcode.wordpress.com/2021/02/26/apex-design-patterns/)
  - Singleton – restricts the instantiation of a class to one “single” instance only within a single transaction context.
  ## Strategy
  lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.

  ![image](https://user-images.githubusercontent.com/34469349/155385118-69b3e245-6c12-4abc-bbcd-1d334074f5f0.png)

  
  ## Decorator
   
   The decorator design pattern falls into the structural category, that deals with the actual structure of a class, whether is by inheritance, composition or both. The goal of this design is to modify an objects’ functionality at runtime without altering its structure.
   
   In Salesforce context, you need to obtain or display temporary information on a LWC/Visualforce page that is not needed beyond the context of the interaction.
   For example, you may have a specific requirement to show Accounts along with the sum of Amount of all related closed opportunities.
   Now just for this specific requirement we will not create a new field on Account object since that would be an overkill. Instead, we will implement decorator pattern and create a new variable called opptyAmountSum which is temporary field (proxy field) in the Response class that will be calculated at run time based on the Account. Since we did not create a field on object, we did not change the structure and we also modified functionality at run time. So we successfully implemented Decorator pattern.
   
   
  ## Facade
  hides the complexity of the system and provides simple interface (not be confused with interface class, here we mean literal interface, something to interact with).
  
  Example - 
  Suppose you have a requirement of showing Contact details on a LWC. These details include First Name, Last Name, Account Name, Sum of all oppty amounts of parent account. Now for this we will need to create some Wrapper class and we will only get/calculate these details and assign them to wrapper class's members(variables)
  In this use case Wrapper is nothing but Facade for our LWC. It hid all the complexity of calculating sum or other non required fields of Contact object and only provided simple interface with required details.
  
  
 ## Composite
 lets you compose objects into tree structures and then work with these structures as if they were individual objects.
 
 Example - 
 Let's say we need order details. Now Order contains multiple things such as Order id, Customer info, Line Items, Shipment details etc. Futher, Customer contains many things such as Id, Name, Email etc. Line Item contains Product, quantity, total price etc. We can break Product further down into Product Name, Id, price etc. So the complex Order class is COMPOSED of sub parts and again these sub parts are composed of more smaller parts until there are no sub parts.
 This is called as Composite Design patter.
 
 ## Bulk State Transition
 used to perform bulk actions efficiently based on change of state of one or more records.
 
 Example - 
 Write bulkified methods/code that can do a generic task and it should be very specific to particular requirement (it shuld be extensible)
 Give example from this link - https://salesforcecookcode.wordpress.com/2021/02/28/bulk-state-transition/


# [Apex Enterprise Patterns](https://www.apexhours.com/apex-enterprise-patterns/)
  - [Apex Enterprise Patterns — Separation of Concerns](https://andyinthecloud.com/2012/11/16/apex-enterprise-patterns-separation-of-concerns/)
  - [Apex Enterprise Patterns — Selector Layer](https://andyinthecloud.com/2013/09/09/apex-enterprise-patterns-selector-layer/)
  - [Apex Enterprise Patterns — Domain Layer](https://andyinthecloud.com/2013/04/24/apex-enterprise-patterns-domain-layer/)
  - [Apex Enterprise Patterns — Service Layer](https://andyinthecloud.com/2013/02/11/apex-enterprise-patterns-service-layer/)
  - [Apex Enterprise Patterns — Unit Of Work](https://andyinthecloud.com/2013/06/09/managing-your-dml-and-transactions-with-a-unit-of-work/)
  - [Apex Enterprise Patterns — Unit Of Work](https://andyinthecloud.com/2014/07/17/doing-more-work-with-the-unit-of-work/)
  - [Apex Enterprise Patterns — FinancialForce Apex Common Updates](https://andyinthecloud.com/2014/06/28/financialforce-apex-common-updates/)

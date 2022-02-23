# Object Oritented Concepts

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
  - Strategy – lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.
  
  ## Decorator
   
   The decorator design pattern falls into the structural category, that deals with the actual structure of a class, whether is by inheritance, composition or both. The goal of this design is to modify an objects’ functionality at runtime without altering its structure.
   
   
   
   
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

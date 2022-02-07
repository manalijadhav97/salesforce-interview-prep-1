# Salesforce Developer Interview Preparation Guide
## Topics for Technical Discussion

1. Objects, Fields and Rows
1. Data Modelling & Object Relationships
1. Salesforce Data Security Model
1. Front-end (LWC, Aura, Visualforce)
1. Apex
1. Database (SOQL, DML, Indexing)
1. Integration
1. Platform Events
1. Platform Cache
1. Governor limits

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
# Technical Section

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


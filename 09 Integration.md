# Integration

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

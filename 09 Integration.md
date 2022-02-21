# Integration

REST vs SOAP

<table class="alt">
<tr><th>No.</th><th>SOAP</th><th>REST</th></tr>
<tr><td>1)</td><td>SOAP is a <strong>protocol</strong>.</td><td>REST is an <strong>architectural style</strong>.</td></tr>
<tr><td>2)</td><td>SOAP stands for <strong>Simple Object Access Protocol</strong>.</td><td>REST stands for <strong>REpresentational State Transfer</strong>.</td></tr>
<tr><td>3)</td><td>SOAP <strong>can't use REST</strong> because it is a protocol.</td><td>REST <strong>can use SOAP</strong> web services because it is a concept and can use any protocol like HTTP, SOAP.</td></tr>
<tr><td>4)</td><td>SOAP <strong>uses services interfaces to expose the business logic</strong>.</td><td>REST <strong>uses URI to expose business logic</strong>.</td></tr>
<tr><td>5)</td><td>SOAP <strong>defines standards </strong> to be strictly followed. </td><td>REST does not define too much standards like SOAP.</td></tr>
<tr><td>6)</td><td>SOAP <strong>requires more bandwidth</strong> and resource than REST.</td><td>REST <strong>requires less bandwidth</strong> and resource than SOAP.</td></tr>
<tr><td>7)</td><td>SOAP <strong>defines its own security</strong>.</td><td>RESTful web services <strong>inherits security measures</strong> from the underlying transport.</td></tr>
<tr><td>8)</td><td>SOAP <strong>permits XML</strong> data format only.</td><td>REST <strong>permits different</strong> data format such as Plain text, HTML, XML, JSON etc.</td></tr>
<tr><td>9)</td><td>SOAP is <strong>less preferred</strong> than REST.</td><td>REST <strong>more preferred</strong> than SOAP.</td></tr>
</table>

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
    
## Named Credentials
Benefit of using Named credentials is we do not have to explicitly specify remote site settings and also they can store the password safely. It takes care of the authentication as well.

state param in oAuth is used to secure the request. If the state param is sent in the request and same state param is responded back. If the param is tampered with, then the request is considered compromised.


### [Integration Design Patterns](https://developer.salesforce.com/docs/atlas.en-us.integration_patterns_and_practices.meta/integration_patterns_and_practices/integ_pat_intro_overview.htm)


JWT

https://medium.com/@tou_sfdx/salesforce-oauth-jwt-bearer-flow-cc70bfc626c2
https://jwt.io/
https://help.salesforce.com/s/articleView?id=000335524&type=1

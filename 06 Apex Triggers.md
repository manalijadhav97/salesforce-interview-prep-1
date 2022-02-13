# Apex Triggers
1. [Context Variables](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables.htm)
1. [Context Variable Considerations](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_context_variables_considerations.htm)

![image](https://user-images.githubusercontent.com/34469349/153751105-a5789a44-1619-4232-baeb-d9189f764f91.png)



### When should you use before and after triggers?

The rule of thumb is we should use before triggers if we need to add any custom validations on the record or update the field of the same record.
Use the after trigger for all other scenarios.

Why should we use after trigger for all other scenarios? For example, creating a contact after an account is created. You might ask.
The simple reason is there could be some calculations/updates happening on the same record by after trigger/flows/processes etc. And we do not want to impact the result of those actions because of our code in before trigger.

### [Triggers and Order of Execution](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_order_of_execution.htm)

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

![image](https://user-images.githubusercontent.com/34469349/153751113-921ed046-43f6-4782-99ac-268a7e2eb3c9.png)

# Platform Events and Triggers

### Custom Platform Events
### Data Capture Change Events

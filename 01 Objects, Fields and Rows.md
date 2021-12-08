# Objects
Objects are containers for your information, but they also give you special functionality. For example, when you create a custom object, the platform automatically builds things like the page layout for the user interface.

Standard objects are objects that are included with Salesforce. Common business objects like Account, Contact, Lead, and Opportunity are all standard objects.

Custom objects are objects that you create to store information that’s specific to your company or industry. For DreamHouse, D’Angelo wants to build a custom Property object that stores information about the homes his company is selling.

[Sales Standard Objects Reference](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_majors.htm)

[Service Standard Objects Reference](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_support.htm)


# Fields
### What are Indexable fields -
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

1. [Custom Settings and Custom Medatada, thier differences and limitations](https://www.biswajeetsamal.com/blog/difference-between-custom-settings-and-custom-metadata-types/).

1. What is Data Skews? What are the types?
  - Ownership Skew - Large number of records (more than 10000) are assigned to single user
  - Lookup Skew - Large number of records are associated with single record.

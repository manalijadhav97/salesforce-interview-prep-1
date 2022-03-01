# Objects 

Objects are containers for your information, but they also give you special functionality. For example, when you create a custom object, the platform automatically builds things like the page layout for the user interface.

Standard objects are objects that are included with Salesforce. Common business objects like Account, Contact, Lead, and Opportunity are all standard objects.

Custom objects are objects that you create to store information that’s specific to your company or industry.

[Sales Standard Objects Reference](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_majors.htm)

[Service Standard Objects Reference](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_erd_support.htm)

## Data Skews

### Ownership Skew

Ownership data skew is a type of date skew which is very common in Salesforce. This issue occurs when more than 10000 records are owned by a single Salesforce user. Since every record inside Salesforce needs to have an owner, it is quite common in organizations to make a default owner or queue, to which all the unassigned or unused records go to. It is a preferred solution for many organizations in such use cases, but little do they know that though this might work for small data sets, this will fail when we are dealing with large data. This increases the probability of performance issues whenever some change to the sharing settings or some similar operation occurs. For example, if a user owns a large number of records and he/she is moved around in the role hierarchy, then the sharing rules for all the records owned by that user will be reevaluated and that will result in a long-running operation.

#### Possible Ways for Avoiding Ownership Skew:

The best way to avoid this kind of skew will be even distribution of such records among multiple users rather than having a single user for all.

If you are compelled to stay put with this solution, then the performance impacts can be reduced by not assigning the user (record owner) to a role.

If the owner must have a role, then try to keep the user on top of the role hierarchy. This will avoid the user being passed around the role hierarchy.

Make sure that the user is not a member of any public group which is acting as the source for a sharing rule.

### Lookup Skew

Lookup skew happens when a large number of records are associated with a single record in the lookup object. Since lookup fields can exist on standard as well as custom fields, lookup skew problems can arise on any custom object in the organization. This happens regardless of whether that lookup exists on a single object or across multiple objects.

#### Possible Ways for Avoiding Lookup Skew:

One method is to distribute the skew across multiple lookup fields. The main cause of the problem is that a large number of records are lookup to the same record. By providing additional lookup values to distribute the skew, record lock exceptions can be minimized or even eliminated.

Remove unnecessary workflow rules or process builders on the objects in order to reduce the record saving time. Also, make sure that the synchronous apex code and triggers are well optimized.

In case the number of lookup values is low and definite, you can use picklist values to represent the lookup values rather than using lookup fields.

# Fields

### What are Indexable fields -

- Default :
  - Primary keys (ID, Name, and Owner fields).
  - Foreign keys (lookup or master-detail relationship fields).
  - Audit dates (such as SystemModStamp).
  - Custom fields marked as External ID or Unique
- Custom :

  - Auto Number
  - Email
  - Number
  - Text

More on this in Database section

# Custom Settings and Custom Metadata

[Custom Metadata Types](https://www.salesforceben.com/custom-metadata-types/)

Limitations mentioned in above post are not valid anymore as the article is dated. However, it gives pretty good understanding of what custom metadata is and when to use it.

[Custom Settings and Custom Medatada, thier differences and limitations](https://www.biswajeetsamal.com/blog/difference-between-custom-settings-and-custom-metadata-types/).


[Custom Metadata Types vs Custom Settings](https://developer.salesforce.com/blogs/engineering/2017/10/platform-on-the-platform.html)

<img src="https://d259t2jj6zp7qm.cloudfront.net/images/v1507175772-cmt_features_summer_17_jaqorx.png"/>


You can add up to 300 fields per custom setting, unless your field limit for custom objects is lower than 300. If your custom objects field limit is lower than 300, your field limit for custom settings is equal to your custom objects field limit.
You can’t share a custom setting object or record.
No owner is assigned when a custom setting is created, so the owner can’t be changed.

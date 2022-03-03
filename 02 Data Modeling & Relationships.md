# Object Realtionships

[Guide to Salesforce Relationships](https://www.salesforceben.com/guide-to-salesforce-relationship-types-and-when-to-use-them/)

### Lookup Considerations

- Account-Contact relationship is a special cascase delete Lookup relationship.

- What to do if the lookup record is deleted?
  - Clear the value of this field. You can't choose this option if you make this field required.
  - Don't allow deletion of the lookup record that's part of a lookup relationship.

### Master-Detail Considerations
- Sharing options available for the child records at the time of creating field
  - Read Only - Perform CRUD on the child record if you have at least read access on master.
  - Read/Write - Perform CRUD on the child record if you have at least read and write access on the master record.
  - Cascade delete and undelete do not invoke the triggers on the child records.


### Convert MD into Lookup
To convert a master-detail relationship to a lookup relationship, we have to make sure there are no roll-up summary fields on the master object. If there are rollup summary fields we have to delete those fields to convert it. Deleted Roll-up fields should also be permanently deleted.

### Convert Lookup into MD
To convert lookup to the master-detail relationship you need to give parent records on all child records. Then only you can convert a lookup relationship to a master-detail relationship if the lookup field in all the records contains a value.

### Hierarchy is only available for User obect

### [Considerations for Relationships](https://help.salesforce.com/s/articleView?id=sf.relationships_considerations.htm&type=5)

# Questions
1. [Why use MD for many-to-many relnship in stead of lookups?](https://salesforce.stackexchange.com/questions/10166/why-does-the-documentation-stipulate-that-a-many-to-many-object-relationship-req)
2. What happens if you delete either of the parent record of a child record?
    - One Object can have only two Master-Detail relationships.
    - If we delete record A (First Master detail relationship is always primary)  – then child record c will be deleted.
    - If we delete record B then in this case also child record C will be deleted.
    - If we delete record c then only C will be deleted , master record will not be deleted.
    - If child C has two Master record A and B, Where A is primary relation then Child record C will inherit the look and feel of Parent object A.
3. In a many-to-many relationship, a user can't delete a parent record if there are more than 200 junction object records associated with it and if the junction object has a roll-up summary field that rolls up to the other parent. To delete this object, manually delete junction object records until the count is fewer than 200.


# Object Realtionships
[Guide to Salesforce Relationships](https://www.salesforceben.com/guide-to-salesforce-relationship-types-and-when-to-use-them/)

### Lookup Considerations
1. Account-Contact relationship is a special cascase delete Lookup relationship.

1. What to do if the lookup record is deleted?
1) Clear the value of this field. You can't choose this option if you make this field required.
2) Don't allow deletion of the lookup record that's part of a lookup relationship.

### Master-Detail Considerations
1. Cascade delete and undelete do not invoke the triggers on the child records.
1. Sharing options available for the child records at the time of creating field
1)Read Only
2)Read/Write

### Hierarchy is only available for User obect
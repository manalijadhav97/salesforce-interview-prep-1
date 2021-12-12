# Salesforce Data Security Model

## Org Level Security

- Login IP Ranges :
  Prevent users from logging into the org by setting login IP ranges at the org level and at the profile level.

- Login Hours :
  Prevent users from logging into the org by setting login hours. Users will not be able to login outside login hours.

## Object Level Security

- Profiles
- Permission Sets
- Permission Set Groups
- [View All, Modify All, View All Data, Modify All Data](https://help.salesforce.com/articleView?id=sf.users_profiles_view_all_mod_all.htm&type=5)
- **View/Modify All** - The “View All” and “Modify All” permissions ignore sharing rules and settings, allowing administrators to grant access to records associated with a given object across the organization.
- **View/Modify All Data** - Managing all data in an organization; for example, data cleansing, deduplication, mass deletion, mass transferring, and managing record approvals.

## Field Level Security

## Record Level Security

1.  Organization Wide Defaults

1.  Role Hierarchies

    - Check grant access using role hierarchies in Sharing Settings (OWD)

1.  Sharing Rules

    - Ownership Based
    - Criteria Based

1.  Manual Sharing

1.  [Apex Managed Sharing](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_creating_with_apex.htm)

    - What is the use for using apex managed sharing? Let us say you create/update an account and based on total Amount of the related opportunities you need to assign that account to particular Sales Rep programatically. This cannot be achieved using any of the declarative tools.

1.  Must Read - [Salesforce Data Securirty Model Explained](https://developer.salesforce.com/blogs/developer-relations/2017/04/salesforce-data-security-model-explained-visually.html)

## Difference b/w Profile and Permission Set

The key UI difference in my experience is that only profiles can be used to control page layout assignment.

Things that are in profile but not in permission sets -
- Page layout assignment
- Desktop client access
- Login Hours
- Login IP Ranges
- Session settings
- Password policies
- Delegated authentication
- Two-factor authentication with Single Sign on
- Organization-Wide Email Addresses are assignable by Profile only (idea to fix this)
- Default record type per object
- Profile specific search layouts (winter 20)

Permission sets and profiles have come very close to parity. Now that record type assignment can be done in either, it's just a few key things that remain, and these likely would remain on profile, as a user can only be assigned one page layout at a time, so it wouldn't really make sense on a permission set.

FWIW, besides for the page layouts, which I knew about from general experience, I came up w this list by looking at a perm set and a profile in the enhanced editor and noted which top-level sections were missing from perm set.

Also, Profile is the user;s base set of permissions and all users are assigned to one. A Permission set is just a way to give a user or a set of users extended permissions without granting them to the entire group of users with a certain Profile.
 

Key example would be that 5 users share the same Profile which does not have permission to create custom report types, but one of the 5 users needs to create custom report types. Rather than create a new Profile just for this one user, you would create a Permission Set that included the Create Custom Report Types permission and assign it to that one user.
 

Profiles can be used to give or take away permission from the users assigned to it. Permission Sets can only give or extend permission to the users assigned to it.

[Source](https://salesforce.stackexchange.com/questions/119220/exclusive-differences-profiles-vs-permission-sets/119297)

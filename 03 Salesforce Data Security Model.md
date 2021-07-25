## Security Model

1.  Org Level Security
    -   Login IP Ranges
    -   Login Hours

1.  Object Level Security
    -   Profiles
    -   Permission Sets
    -   Permission Set Groups
    -   [View All, Modify All, View All Data, Modify All Data](https://help.salesforce.com/articleView?id=sf.users_profiles_view_all_mod_all.htm&type=5)
    -   **View/Modify All** - The “View All” and “Modify All” permissions ignore sharing rules and settings, allowing administrators to grant access to records associated with a given object across the organization.
    -   **View/Modify All Data** - Managing all data in an organization; for example, data cleansing, deduplication, mass deletion, mass transferring, and managing record approvals.

    .  Field Level Security

1.  Record Level Security

    1.  Organization Wide Defaults

    1.  Role Hierarchies

        -   Check grant access using role hierarchies in Sharing Settings (OWD)

    1.  Sharing Rules

        -   Ownership Based
        -   Criteria Based

    1.  Manual Sharing

    1.  [Apex Managed Sharing](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_creating_with_apex.htm)

    -   What is the use for using apex managed sharing? Let us say you create/update an account and based on total Amount of the related opportunities you need to assign that account to particular Sales Rep programatically. This cannot be achieved using any of the declarative tools.

1.  Must Read - [Salesforce Data Securirty Model Explained](https://developer.salesforce.com/blogs/developer-relations/2017/04/salesforce-data-security-model-explained-visually.html)

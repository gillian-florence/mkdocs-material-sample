# Custom Objects

The following custom objects are included with the installation of the Union Rules feature:

- Union
- Union Rules
- Union Rule Sets
- Union Rule Set Assignment
- Service Resource Union Member
- Time Type

This section provides details about each custom object and their custom fields.

## Union

The **Union** object represents a work group within an organization where a specific set of union rules can be applied. Service Resources are added to a Union through the **Service Resource Union Member** junction object. A set of Union Rules is assigned to the Union. These rules apply when time is logged for the Service Resource.

### Fields

The custom fields in the Union object are listed in the table below:

| Label       | API Name         | Data Type       | Description               | Configuration Options |
|-------------|------------------|------------------|---------------------------|------------------------|
| Union Name  | `Name`           | Text(80)         | The name of the Union.    | Required: Yes          |
| Description | `Description__c` | Text Area (255)  | Description for the Union | Required: No           |

## Union Rules

A **Union Rule** record contains the configuration for a specific rule and is tied to a parent **Union Rule Set**. The fields on the Union Rule control how the system processes the rule when time is logged for a Service Resource.

### Fields

The custom fields for the Union Rule object are listed in the table below:

| Label            | API Name         | Data Type         | Description                                            | Configuration Options                                                                 |
|------------------|------------------|-------------------|--------------------------------------------------------|----------------------------------------------------------------------------------------|
| Union Rule Name  | `Name`           | Text(80)          | The name of the Union Rule.                            | Required: Yes                                                                          |
| Description      | `Description__c` | Text Area (255)   | Description for the Union Rule                         | Required: No                                                                           |
| Day              | `Day__c`         | Picklist          | Indicates which day the Union Rule is for              | Picklist values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday        |
| Holiday          | `Holiday__c`     | Checkbox          | Indicates if the rule is for a holiday                 | Default: False                                                                         |
| Locked           | `Locked__c`      | Checkbox          | Indicates if the Union Rule is locked                  | Formula: `Time_Rule_Set__r.Locked__c = true`                                           |
| Time Type        | `Time_Type__c`   | Lookup (Time Type)| Identifies the Time Type for the Union Rule            | Lookup Options: Prevent deletion of referenced record. Filter: Active equals `True`    |
| Threshold        | `Threshold__c`   | Number(2,2)       | Max hours allowed for the specified Time Type          | Required: Yes                                                                          |

## Union Rule Sets

A **Union Rule Set** is a collection of Union Rules that will be assigned to a Union. Once a Union Rule Set is assigned to a Union (and the assignment is within the date criteria), the **Locked** field is automatically set to `true` via a Flow. A locked Union Rule Set cannot be modified — Union Rules cannot be added or deleted.

### Fields

The custom fields for the Union Rule Set object are listed in the table below:

| Label       | API Name         | Data Type       | Description               | Required |
|-------------|------------------|------------------|---------------------------|----------|
| Union Name  | `Name`           | Text(80)         | The name of the Union     | Yes      |
| Description | `Description__c` | Text Area (255)  | Description for the Union | No       |

# Custom Objects #
<p>The following custom objects are included with the installation of the Union Rules feature:
<ul>
<li>Union</li>
<li>Union Rules</li>
<li>Union Rule Sets</li>
<li>Union Rule Set Assignment</li>
<li>Service Resource Union Member</li>
<li>Time Type</li> </ul> 
This section provides details about each custom object and their custom fields.</p>
## Union
<p> The Union object represents a work group within an organization where a specific set of union rules can be applied. Service Resources are added to a Union through the Service Resource Union Member junction object. A set of Union Rules is assigned to the Union, these rules apply when time is logged for the Service Resource.</p>
 
### Fields
The custom fields in the Union object are listed in the table below:

| Label       | API Name         | Data Type       | Description               | Configuration Options  |
| ----------- | ---------------- |-----------------|-------------------------- |-----------|
| Union Name  | `Name`           | Text(80)        | The name of the Union.    | Requied: Yes       |
| Description | 'Description__c' | Text Area (255) | Description for the Union | Required: No        |
  
## Union Rules
<p> 
A Union Rule record contains the configuration for a specific rule and is tied to a parent Union Rule Set. The fields on the Union Rule control how the system processes the rule when time is logged for a Service Resource. </p>
### Fields
The custom fields for the Union Rule object are listed in the table below:

| Label            | API Name         | Data Type       | Description                    |  Configuration Options |
| -----------      | ---------------- |-----------------|------------------------------- |------------------------|
| Union Rule Name  | `Name`           | Text(80)        | The name of the Union Rule.    | Required: Yes                    |
| Description      | Description__c   | Text Area (255) | Description for the Union Rule | Required: No                     |
| Day              | Day__c           | Picklist        | Used to indicate which day the Union Rule is for. | Picklist values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| Holiday          | Holiday__c       | Checkbox        |  Used to indicate if the rule is for a holiday | Default: False   |
| Locked           | Locked__c        | Checkbox        | Indicates if the Union Rule is Locked (true) or not (false).| Formula: `Time_Rule_Set__r.Locked__c = true` |  
| Time Type        | Time_Type__c     | Lookup(Time Type)| Identifies the Time Type for the Union Rule. | <b>Lookup Options:</b> Don't allow deletion of the lookup record that's part of a lookup relationship. <b>Lookup Filter:</b> Filter Criteria: Time Type: Active equals `True` |
| Threshold        | Threshold__c     | Number(2,2)     | Indicates the maximum number of hours for the Time Type specified. |  Required: Yes |


## Union Rule Sets
<p>
A Union Rule Set is a collection of Union Rules that will be assigned to a Union. Once a Union Rule Set is assigned to a Union, if the assignment is within the date criteria, then the Locked field is automatically set to true (via a Flow) A locked Union Rule Set cannot be modified – Union Rules cannot be added or deleted</p>

### Fields
<p> The custom fields for the Union Rule object are listed in the table below:</p>

| Label       | API Name         | Data Type       | Description               | Required  |
| ----------- | ---------------- |-----------------|-------------------------- |-----------|
| Union Name  | `Name`           | Text(80)        | The name of the Union.    | Yes       |
| Description | 'Description__c' | Text Area (255) | Description for the Union | No        |
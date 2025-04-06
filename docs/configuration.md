
# Configuration
<P>To configure the Union Rules feature, you must complete the following:
<ul>
<li>Create custom fields for time tracking categories.</li>
<li>Create Time Type records that correspond to time categories.</li>
<li>Create roll-up summary Fields to aggregate time entries.</li>
<li>Create formula fields to convert minutes into hours.</li>
<li>Assign permission sets to ensure proper access.</li>
</ul> </P>

## Create Custom Fields 
<p> Custom number fields must be created on the Time Sheet Entry object for each time category your organization requires. These time type fields store the categorized time in minutes, based on Time Rules applied per day.</p>
<p> For example, if your organization categorizes time worked into Regular, Overtime, and Doubletime, create corresponding fields for these categories. These fields will automatically update with the numerical value of the categorized minutes based on the rules for each day.</p>

!!! note
     A System Administrator must create the fields.


# Configuration

To configure the **Time Rules** feature, complete the following steps:

- Create custom fields for time tracking categories.
- Create **Time Type** records that correspond to time categories.
- Assign **Permission Sets** to ensure proper access.
- Create **Roll-Up Summary Fields** to aggregate time entries.
- Create **Formula Fields** to convert minutes into hours.

---

## Creating Custom Fields for Time Sheet Entry

Custom number fields must be created on the **Time Sheet Entry** object for each time category your organization requires. These fields store categorized time in **minutes**, based on the Time Rules applied per day.

> Example: If your organization uses *Regular*, *Overtime*, and *Doubletime* categories, create one field for each.

> ⚠️ **Note:** This configuration must be completed by a System Administrator.

These fields will automatically populate with the number of minutes categorized by the Time Rule logic.

### Steps:

1. From **Setup**, click **Object Manager**, then open the **Time Sheet Entry** object.
2. Click **Fields & Relationships**.
3. Click **New**.
4. Select **Number** as the data type, then click **Next**.
5. Enter a **Field Label** (e.g., `Regular`).
6. Set:
   - **Length** = `4` (digits to the left of the decimal)
   - **Decimal Places** = `0` (no decimal places)

   > ⚠️ The values will display as **minutes** on Time Sheet Entry records.

7. Keep the default **Field Name**.

   > 🔑 This value must be entered in the **Field API Name** of the corresponding **Time Type** record.

8. Click **Next**.
9. Configure **field-level security** as needed, then click **Next**.
10. Click **Save & New** to create additional fields (e.g., `Overtime`, `Doubletime`).
11. Repeat steps for each time category required.

---

## Creating Roll-Up Summary Fields for Time Sheet

For each time type, create a **Roll-Up Summary Field** on the **Time Sheet** object. This field will aggregate time from all related **Time Sheet Entry** records.

### Steps:

1. From **Setup**, click **Object Manager**, then open the **Time Sheet** object.
2. Click **Fields & Relationships**.
3. Click **New**.
4. Select **Roll-Up Summary** as the data type, then click **Next**.
5. Enter a **Field Label** (e.g., `Regular Time Roll-Up`). Keep the default **Field Name** and click **Next**.
6. In the **Summarized Object** dropdown, select **Time Sheet Entries**.
7. Select **SUM** as the roll-up type.
8. For **Field to Aggregate**, select the custom number field (e.g., `Regular`).
9. Ensure the filter criteria is set to:
   > *All records should be included in the calculation.*
10. Click **Next**, then **Save**.

Repeat these steps to create roll-up summary fields for each time category (e.g., `Overtime`, `Doubletime`).

## Creating Formula Fields to Convert Minutes to Hours

To display categorized time in **hours** rather than **minutes**, create a **Formula Field** on the **Time Sheet** object for each time category. This allows for easy reporting and readability while maintaining system-calculated values in minutes.

> ⚠️ **Note:** Formula fields are read-only and do not affect the stored value of the original field.

### Steps:

1. From **Setup**, click **Object Manager**, then open the **Time Sheet** object.
2. Click **Fields & Relationships**.
3. Click **New**.
4. Select **Formula** as the data type, then click **Next**.
5. Enter a **Field Label** (e.g., `Regular Time (Hours)`). The **Field Name** will populate automatically.
6. For **Formula Return Type**, select **Number**.
7. Set:
   - **Decimal Places** = `2`
8. In the formula editor, enter a formula that divides the roll-up field value by 60.
   ```plaintext
   Regular_Time_Roll_Up__c / 60
> Replace Regular_Time_Roll_Up__c with the actual API name of your roll-up field.
9. Click Next.
10. Configure field-level security as needed, then click **Next**.
11. Click **Save & New** to create additional formula fields for other categories (e.g., Overtime (Hours), Doubletime (Hours)).
12. Repeat steps for each time category you want to convert to hours.
Once complete, your Time Sheet records will show both the total minutes (from roll-up fields) and the corresponding hour values (from formula fields), enhancing reporting clarity.
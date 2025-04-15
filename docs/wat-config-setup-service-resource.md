Ensure a **Service Resource** is created for your dispatchers and that they are added to the correct **Service Territories**.

> 📘 **Reference:** [Create Service Resources for Field Service (Salesforce Help)](https://help.salesforce.com/s/articleView?id=sf.fs_create_resources.htm&type=5)

#### Create a Dispatcher Service Resource

1. Navigate to the **Service Resources** tab.
2. From the list view, click **New**.
3. Enter a **Name** for the resource.
4. In the **User** field, select the dispatcher user.
5. From the **Resource Type** picklist, select **Dispatcher**.
6. Enable the **Active** checkbox.
7. Click **Save**.

A **Service Resource** record is now created for the user with the Dispatcher resource type.
#### Add Dispatcher as a Service Territory Member

Once the Dispatcher Service Resource is created, add the resource as a Service Territory Member.

1. Open the **Service Resource** record for the dispatcher.
2. In the **Service Territories** related list, click **New**.  
   The **Service Resource** will be pre-filled.
3. Select an existing **Service Territory** or click to create a new one.
4. Set the **Territory Type**, enter an **Address**, and click **Save**.

The dispatcher is now a member of the selected Service Territory and will receive alerts from technicians assigned to the same territory.

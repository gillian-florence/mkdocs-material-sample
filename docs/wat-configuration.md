## Configure the Working Alone Timer Feature

Once the SFS-X package is installed, if your org has the **Working Alone Timer** feature enabled, you must complete the following configuration steps to ensure full functionality for both dispatcher and mobile technician users:

- [**Set Up Service Resources and Service Territories**](wat-config-setup-service-resource.md)  
  Dispatchers and technicians must be created as service resources and added to appropriate service territories. Dispatchers will receive alerts only from technicians who are members of their assigned service territory.

- **[Assign Permission Sets](#)**  
  The SFS-X package includes permission sets that must be assigned to both **mobile technicians** and **dispatchers** to ensure they have access to the necessary components.

- **[Configure Alerts Custom Utility Item](#)**  
  Add the **Alerts** custom utility item to the appropriate Field Service Lightning apps so that dispatchers can view and manage active working alone alerts.

- **[Add Working Alone Timer Action to Service Appointment Page Layouts](#)**  
  The **Working Alone Timer** Lightning Web Component (LWC) action must be added to **Service Appointment** page layouts, enabling technicians to launch the timer directly from the Field Service mobile app.

- **[Add Duration Options and Modify Reminder Frequencies](#)**  
  Use the **Times and Frequencies Configuration** Custom Metadata Type to customize timer duration options and set countdown reminder frequencies that match your organization's safety protocols.

- **[Customize Alerts Using Field Sets](#)**  
  Use the provided field sets on the **Alert** object to control which fields display on pop-up notifications, in the utility panel, and in the alert detail view for dispatchers and technicians.

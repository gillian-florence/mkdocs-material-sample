## Custom Object: Alert

The **Alert** object is used to track and manage safety-related notifications initiated by technicians using the Working Alone Timer. Each alert record stores detailed information about the technician, associated service appointment, timing data, and status transitions. This object plays a key role in ensuring visibility and traceability of field safety events, enabling dispatchers to intervene when necessary.

| **Field Label**            | **API Name**                    | **Data Type**           | **Description**                                                                                                                                      |
|----------------------------|----------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Accepted By                | `AcceptedById__c`               | Lookup (User)            | User that accepted the alert.                                                                                                                        |
| Accepted Time              | `AcceptedTime__c`               | Date/Time                | Date and time when the alert was accepted.                                                                                                           |
| Alert Location             | `LocationCoordinates__c`        | Geolocation              | Latitude and longitude from the technician’s mobile device when starting the timer.                                                                 |
| Alert No.                  | `Name`                          | Auto Number              | Format: `A-{0000}`. Auto-generated alert number.                                                                                                     |
| Comments                   | `Description__c`                | Long Text Area           | Text entered by the technician when initiating the Working Alone Timer in the Field Service mobile app.                                              |
| Completed By               | `CompletedById__c`              | Lookup (User)            | User who completed the alert.                                                                                                                        |
| Completed Time             | `CompletedTime__c`              | Date/Time                | Timestamp of when the alert was completed. Empty if the alert expired before being acknowledged.                                                    |
| Created By                 | `CreatedById`                   | Lookup (User)            | User who created the alert by starting a Working Alone Timer.                                                                                       |
| Initial Duration (Mins)    | `InitialDuration__c`            | Number (18,0)            | Duration (in minutes) set by the technician when the timer was started.                                                                             |
| Received Time              | `ReceivedTime__c`               | Date/Time                | Time when the alert was received by the system. May differ from Start Time in offline situations. Useful for reporting.                             |
| Resource                   | `Resource__c`                   | Lookup (User)            | Technician (Service Resource) who initiated the alert.                                                                                               |
| Service Appointment        | `ServiceAppointment__c`         | Lookup (Service Appointment) | Service Appointment associated with the timer.                                                                                                  |
| Start Time                 | `AlertDateTime__c`              | Date/Time                | Timestamp when the timer was started.                                                                                                                |
| Status                     | `Status__c`                     | Picklist                 | Current status of the alert: <br>• **New** – Timer started, not yet accepted <br>• **Accepted** – Dispatcher accepted <br>• **Completed** – Timer completed <br>• **Escalated** – Timer expired |
| Total Duration (Mins)      | `AlertDurationTime__c`          | Number (6,0)             | Total time the alert was active, including any extensions.                                                                                          |
| Work Order                 | `WorkOrder__c`                  | Lookup (Work Order)      | Reserved for future enhancements and associations.                                                                                                   |

## Metadata for Alert Customization

This section outlines configurable metadata related to the **Alert** object, which allows for tailored experiences across desktop and mobile interfaces, including how alert information is displayed to dispatchers and technicians.
## Field Sets
The following **field sets** are included with the Alert object to customize the display of alert data in various UI components:

- **Alerts – Pop-Up Notifications**  
  Controls the fields shown in the pop-up notifications received by dispatchers when a technician starts a Working Alone Timer.

- **Utility Panel Alerts**  
  Defines the fields shown in the alert record preview in the Utility Panel of the Field Service console app.

- **Alert Details**  
  Determines the fields displayed when a dispatcher clicks the **View** button on an alert within the Utility Panel.

- **Alert Mobile UI Fields**  
  Specifies the fields shown to technicians on the Field Service mobile app in the *Working Alone Timer* component.
## Quick Action (Service Appointment Object)

- **Working Alone Timer**  
  A Lightning Web Component quick action configured on the Service Appointment object.  
  This action is used by mobile technicians to start a working alone timer and send an alert to dispatchers. It is launched from the Field Service mobile app.
## Custom Metadata Types

The following custom metadata types are included to support flexibility and control over timer behavior and fields that display:

- **Times and Frequencies Configuration**  
  Used to define duration labels and their corresponding values, as well as the countdown frequency for reminder notifications sent to dispatchers.

- **Working Alone Timer Settings**  
  Allows for configuration of:
  - A **Flow** that is triggered upon completion of a Working Alone Timer (e.g., follow-up tasks or safety checklists), based on user profile.
  - The **Field Set** used to display fields on the Working Alone Timer component, enabling further UI customization by profile or use case.

## Working Alone Timer and Dispatcher Alert System

The Working Alone Timer and Dispatcher Alert System is designed for organizations with mobile technicians engaged in high-risk activities who may be working alone. It enhances technician safety by providing a timer mechanism to indicate lone work status and delivers real-time alerts to Field Service dispatchers for timely support and intervention.

### Key Features

The Working Alone Timer and Alert System consists of the following components:

#### Working Alone Timer Action

The Working Alone Timer is a Lightning Web Component available as a quick action for mobile technicians. It allows technicians to:

- Start a timer when engaged in high-risk, lone work.
- Enter a timer duration.
- Add comments visible to their dispatchers.

This action must be configured on the Service Appointment object and made available in the Field Service mobile app.

#### Alerts Utility Item

The Alerts utility item displays all active Working Alone alerts for dispatchers. Key functionality includes:

- Available within the SFS-X Lightning app** (included in the package).
- Can be added to any existing or new Field Service Lightning app.
- Expanding an alert reveals more details about the alert and associated Service Appointment.
- Displayed field details can be customized.

#### Notifications

Dispatchers receive pop-up notifications when a technician in their Service Territory starts a Working Alone Timer. These notifications:

- Remain on the Field Service Console until acknowledged.
- Allow for timely dispatcher awareness and action.

#### Alert Records

The Alert custom object tracks the history of Working Alone Timer activities, including:

- Timer start and completion times.
- Technician name and location.
- Associated Service Appointment details.

The Alerts tab is included as a navigation item in the provided SFS-X Lightning app.

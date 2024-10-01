## Bounded Contexts

After the event storming session, the following contexts have been identified:

-   **Auth**: Responsible for managing the authentication and authorization of the users. It also is responsible for managing the permissions of the users.
-   **User**: This context is responsible for managing the users of the system, in particular, nothing regarding the authentication process but only the management of the user registry.
-   **Monitoring**: It is responsible for managing the devices and the data they produce. This context is responsible for consulting the data produced by the devices, their configurations and everything regarding the WoT interactions.
-   **Alarm**: Responsible for managing the alarms in the overall system. It is also responsible for the object recognition feature of the system.
-   **Notification**: Responsible for managing the notifications of the system. It is responsible for sending notifications to the users when particular events occur.
-   **Location**: Responsible for the location management of the system.

# System Architecture and Design Decisions V1.0

## Functional Requirements (What does the system do ?).

- All system functionalities require authentication, unauthenticated users are routed to authentication.
- Authentication is through Google or Microsoft **OAUTH**. On successful authentication registration is required.
- Returning users (already registered but logged out) authenticate and are routed directly to the application, not registration.
- Registers with user profile data namely:
  - unique anonymous reveal name (public visibility mandatory and cannot have the first or last name in it based on case-insensitive substring match against full name tokens) 
  - full name (visibility to be revealed based on user specified scope, **Private** by default, pulled from Microsoft or Google during Authentication, editable)
  - sex (visibility to be revealed based on user specified scope, **Connections only** by default)
  - birth date (visibility to be revealed based on user specified scope, **Private** by default)
    - users under the age of 21 will not be allowed to log in with a cheeky message in response if attempt is made.  
  - age (derived from the birth date, **Public** by default)
  - email (always hidden, pulled from Microsoft or Google during Authentication, editable)
  - phone number (always hidden, pulled from Microsoft or Google during Authentication, editable, **OTP-Verified**)
  - location (always hidden, but used for proximity calculation)
  - profile picture (visibility to be revealed based on user specified scope, **Connections only** by default)
  - On successful registration, the user account gets created and will be prompted for user data, the actual data used for matching and recommendations.
- The USER provides personal data post registration namely (Has to be public, since this is what allows the user to know what requirement matched):
  - Profession (Business or Employee)
  - Job Role / Unemployed / Looking for a job
  - Hobby (At max 3 hobbies)
  - Status (Single, Dating, Married)
- The USER provides intent (what is the user looking for) based on 6 different criteria, namely (provided successfully authorized):
  - Business partner
  - Employer
  - Employee
  - Date
  - Matching Hobby
  - Custom Request
- The USER can at max input 3 intents, and min of one intent.
- The order of the list is the order of importance in matching, lower number is higher priority.
- Proximity Condition
  - The proximity condition at max is the current city.
  - The proximity condition at min is a 100 meters radius from the current geolocation.
  - USER sees in-proximity users whose intent and personal data fit their criteria, ranked by relevance, with each surfaced user's info visible per that user's scope settings.
- Current USER can go through all the users that are brought up with all the info they have made visible and send them a request to connect. This connection logic can be made fun in different way the ideation to which has to be quite different in it's own rights. Linked in has connection requests, Instagram has followers and following, the same this has to have something unique like **Add to Orbit** and **Orbiting**.
- USERS can directly chat with **orbiters** (actually **connections only** can be replaced with **orbiters only**).
- Every request the USER accepts the counter on the **orbiter** increases, every request of the USER that gets accepted the counter on the **orbiting** increases.
- Profile editing (registration profile + matching profile + visibility scopes)
- Notifications (request received, request accepted, new message, nearby match)
- Location controls (pause, ghost mode, only-when-app-open) — non-negotiable for Indian metro audience, especially women
- Block / report / disconnect — safety floor for any social app
- Logout, account deletion
- Login


### This is the first revision of the Functional Requirements, changes to this can be added and modifications to be made, where the logic might not make sense or is vague.

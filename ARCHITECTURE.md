# System Architecture and Design Decisions

## Functional Requirements (What does the system do ?).

- All system functionalities require authentication, unauthenticated users are routed to authentication.
- Authentication is through Google or Microsoft **OAUTH**. On successful authentication the registration is required.
- Returning users (already registered but logged out) authenticate and are routed directly to the application, not registration.
- Registers with user profile data namely
  - unique anonymous reveal name (public visibility mandatory and cannot have the first or last name in it based on case-insensitive substring match against full name tokens) 
  - full name (visibility to be revealed based on user specified scope, **Private** by default, pulled from Microsoft or Google during Authentication, editable)
  - sex (visibility to be revealed based on user specified scope, **Connections only** by default)
  - birth date (visibility to be revealed based on user specified scope, **Private** by default)
    - users under the age of 21 will not be allowed to log in with a cheeky message in response if attempt is made.  
  - age (derived form the birth date, **Public** by default)
  - email (always hidden, pulled from Microsoft or Google during Authentication, editable)
  - phone number (always hidden, pulled from Microsoft or Google during Authentication, editable, **OTP-Verified**)
  - location (always hidden, but used for proximity calculation)
  - profile picture (visibility to be revealed based on user specified scope, **Connections only** by default)
  - On successful registration, the user account gets created and will be prompted for user data, the actual data used for matching and recommendations.
- Gets Matches and Recommendations based on personal data, choices and defined proximity.
- Users can also view people with locked profile images or unlocked in app images within the proximity and view all that they have made public (which the app allows).
- Users have a set of predefined options on the basis of which they can prioritize matches.
- Users are required to list there interests in order of criticality.
- System surfaces matches when conditions match.
- The user defines what are the goals or criteria of a successful match, it can be multiple (hobby partner, romantic partner, business partner, recruiter to employee or vice versa).
- Proximity is mapped throughout the day and best matches are shown (real-time or after a buffer chosen by the user among the predefined options).
- User connects with a request.
- Successful connection results in the unlocking of a chat interface among the connections.
- Users can request for groups among their connections (on successful acceptance).
- Users can reveal their other socials on the platform, where the visibility of each of their data is based on their scope definition for each field (Private, Public, To Connections only).


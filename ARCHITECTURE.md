# System Architecture and Design Decisions

## Functional Requirements (What does the system do ?).

- User sees registration page, on hitting the application the first time.
- Registers with user credentials namely
  - unique anonymous reveal name (public visibility mandatory and cannot have the first or last name in it) 
  - full name (visibility to be revealed based on user specified scope)
  - age (visibility to be revealed based on user specified scope)
  - sex (visibility to be revealed based on user specified scope)
  - birth date (visibility to be revealed based on user specified scope)
  - email (always hidden)
  - phone number (always hidden)
  - location (always hidden)
  - profile picture (visibility to be revealed based on user specified scope)
  On successful registration, the user account gets created and will be prompted for user data, the actual data used for matching and recommendations.
- Gets Matches and Recommendations based on personal data, choices and defined proximity.
- Users can also view people with locked profile images or unlocked in app images within the proximity and view all that they have made public (which the app allows).
- System surfaces matches when conditions match.
- The user defines what are the goals or criteria of a successful match, it can be multiple (hobby partner, romantic partner, business partner, recruiter to employee or vice versa).
- Proximity is mapped throughout the day and best matches are shown (realtime or after a buffer chosen by the user among the predefined options).
- User connects with a request.
- Successful connection results in the unlocking of a chat interface among the connections.
- Users can request for groups among their connections (on successful acceptance).
- Users can reveal their other socials on the platform, where the visibility of each of there data is based on there scope definition for each field (Private, Public, To Connections only).


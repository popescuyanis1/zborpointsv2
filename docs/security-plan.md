# Security plan

## Current state

- The app uses Firebase Authentication.
- The interface checks user roles in frontend code.
- Managers and coordinators can access management features.
- Volunteers can use view-only mode.
- Data is stored in Firebase Realtime Database.

## Required upgrade

- Add Firebase Realtime Database Security Rules.
- Block public writes.
- Allow anonymous users to read only safe public data.
- Allow authenticated managers to manage all operational data.
- Allow department coordinators to edit only their department data.
- Validate all database writes.
- Add audit logging for important changes.
- Keep private backups outside GitHub.
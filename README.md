# ZBOR Hub Volunteer Management

A live web platform for managing volunteers, departments, coordinators, points, monthly rankings, and engagement status inside ZBOR Hub Târgu Jiu.

## Project status

This project is already deployed and used as an internal operational platform.

The current version supports volunteer management, point tracking, department coordination, role-based access, and Firebase-based data storage.

## Problem

Volunteer coordination can become difficult when information is spread across messages, spreadsheets, informal notes, and separate people.

This project centralizes the main workflow:

* who the volunteers are
* which department they belong to
* who coordinates each department
* what actions were completed
* how many points each volunteer has
* who is active, inactive, or at risk of low engagement
* what rules are used for points

## Main features

* Firebase Hosting deployment
* Firebase Authentication
* email and password login for managers and coordinators
* anonymous view-only access for volunteers
* dashboard with monthly statistics
* volunteer list and profile management
* department management
* coordinator and manager management
* point rules management
* point/action history
* monthly leaderboard
* department leaderboard
* engagement status system
* role-based interface

## User roles

### Community manager

Can manage the platform, coordinators, departments, volunteers, and point rules.

### Department coordinator

Can manage operational data related to volunteers and activity.

### Volunteer

Can access the platform in view-only mode.

## Technology stack

* HTML
* CSS
* JavaScript
* Firebase Hosting
* Firebase Authentication
* Firebase Realtime Database

## Current project structure

```text
zborpointsv2/
  public/
    index.html
    login.html
    volunteers.html
    departments.html
    users.html
    puncte.html
  docs/
    production-checklist.md
    current-features.md
    security-plan.md
  firebase.json
  README.md
```

## Data model

The app currently uses Firebase Realtime Database.

Main data areas:

* users
* volunteers
* actions
* department settings
* point rules
* general rule messages

A complete database schema will be documented in `docs/database-schema.md`.

## Security plan

The current version uses Firebase Authentication and frontend role checks.

The next major upgrade is to add Firebase Realtime Database Security Rules that enforce permissions at database level.

Planned rules:

* block public writes
* allow volunteers to read only safe data
* allow coordinators to edit only allowed operational data
* allow community managers to manage platform data
* validate all required fields
* prevent invalid roles, departments, names, and point values
* add audit logging for important actions

More details are in:

```text
docs/security-plan.md
```

## Production safety

Because this project is already in real use, every live change must follow a production checklist.

The checklist is stored in:

```text
docs/production-checklist.md
```

## Planned improvements

* Firebase Realtime Database Security Rules
* staging deployment before live deployment
* audit log for edits and deletions
* database schema documentation
* cleaner shared JavaScript files
* shared CSS file
* export to CSV
* anonymized demo mode
* improved analytics dashboard
* screenshots and short demo video
* impact report

## Impact goals

This project is designed to help youth and volunteer organizations manage activity more clearly, reduce manual tracking, and give coordinators a faster view of involvement across departments.

Future impact documentation will include:

* number of volunteers managed
* number of departments
* number of coordinators
* number of recorded actions
* time saved compared to manual tracking
* feedback from users

## Privacy note

The platform may contain real volunteer names, roles, and activity history.

Private data must not be uploaded to GitHub.

Database backups must stay outside the repository.

Screenshots used for presentations must hide or anonymize personal data.

## Author

Yanis Popescu

## License

Private project for now.

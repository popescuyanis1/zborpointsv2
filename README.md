# ZBOR Hub Volunteer Management

A web platform built for ZBOR Hub Târgu Jiu to manage volunteers, departments, coordinators, activity points, monthly rankings, and engagement status in one centralized place.

## Project status

This project is deployed and used as an internal operational platform.

The current version supports volunteer management, department coordination, point tracking, role-based access, monthly statistics, leaderboards, and Firebase-based data storage.

## My role

I designed, built, documented, and deployed this platform for ZBOR Hub Târgu Jiu.

My work included:

* structuring the platform pages and user flows
* building the frontend with HTML, CSS, and JavaScript
* connecting the app to Firebase Hosting, Firebase Authentication, and Firebase Realtime Database
* creating the volunteer, department, coordinator, point tracking, and leaderboard sections
* documenting the current features, security plan, and production checklist
* preparing the project for real internal use by coordinators and managers

## Problem

Volunteer coordination can become difficult when information is spread across messages, spreadsheets, informal notes, and different people.

This project centralizes the main operational workflow so coordinators can quickly understand:

* who the volunteers are
* which department each volunteer belongs to
* who coordinates each department
* what actions were completed
* how many points each volunteer has
* who is active, inactive, or at risk of low engagement
* what rules are used for awarding points

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
* point and action history
* monthly leaderboard
* department leaderboard
* engagement status system
* role-based interface
* production checklist for safe live updates

## User roles

### Community manager

Can manage the platform, coordinators, departments, volunteers, point rules, and operational settings.

### Department coordinator

Can manage operational data related to volunteers, activity, points, and department involvement.

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

A complete database schema will be documented in:

```text
docs/database-schema.md
```

## Security plan

The current version uses Firebase Authentication and frontend role checks.

The next major upgrade is to add Firebase Realtime Database Security Rules that enforce permissions directly at database level.

Planned security improvements include:

* blocking public writes
* allowing volunteers to read only safe data
* allowing coordinators to edit only approved operational data
* allowing community managers to manage platform data
* validating required fields
* preventing invalid roles, departments, names, and point values
* adding audit logging for important actions

More details are documented in:

```text
docs/security-plan.md
```

## Production safety

Because this project is already used operationally, every live change must be tested carefully before deployment.

The production checklist includes:

* checking Firebase configuration
* testing authentication
* testing role-based access
* testing volunteer and department pages
* testing point updates
* checking that no private data is exposed
* confirming that the live version still works after deployment

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
* screenshots with anonymized data
* short demo video
* impact report

## Impact goals

This project is designed to help youth and volunteer organizations manage internal activity more clearly.

The platform aims to:

* reduce manual tracking
* replace scattered spreadsheets and messages
* give coordinators a faster view of volunteer involvement
* make monthly activity easier to measure
* support clearer department coordination
* improve transparency around points and rankings

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

This repository does not include:

* database backups
* Firebase private credentials
* personal volunteer data
* internal exports
* screenshots with visible personal information

Any screenshots used for presentations must hide or anonymize private data.

## Repository note

This repository is public for portfolio and documentation purposes.

The live platform is intended for internal operational use by ZBOR Hub Târgu Jiu.

## Author

Yanis Popescu

## License and use

Source code is public for portfolio purposes.

Real volunteer data, database backups, private credentials, and internal operational information are not included.

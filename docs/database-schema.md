# Database schema

This file documents the current Firebase Realtime Database structure for the ZBOR Hub Volunteer Management platform.

The app uses this root path:

```text
zborHubTgJiu
```

## Main structure

```text
zborHubTgJiu/
  users/
  volunteers/
  actions/
  departmentSettings/
  pointRules/
  ruleMessages/
```

## users

Stores internal user profiles for managers and coordinators.

Path:

```text
zborHubTgJiu/users/{uid}
```

Expected fields:

```text
uid: string
fullName: string
email: string
role: string
department: string | null
activeStatus: boolean
createdAt: string
updatedAt: string
```

Allowed roles:

```text
community_manager
department_coordinator
```

Purpose:

* identify authenticated users
* decide what each user can access
* assign coordinators to departments
* block inactive accounts

## volunteers

Stores volunteer profiles.

Path:

```text
zborHubTgJiu/volunteers/{volunteerId}
```

Expected fields:

```text
id: string
fullName: string
department: string
avatar: string
activeStatus: boolean
totalPoints: number
monthlyPoints: number
streakDays: number
badges: array
actionCount: number
role: "volunteer"
createdAt: string
updatedAt: string
```

Allowed departments:

```text
HR
PR si Comunicare
Creatie si Implementare
```

Purpose:

* store volunteer identity
* store volunteer department
* track active or inactive status
* store point totals
* support leaderboard and monthly status

## actions

Stores point history and activity records.

Path:

```text
zborHubTgJiu/actions/{actionId}
```

Expected fields:

```text
id: string
volunteerId: string
volunteerName: string
department: string
type: string
points: number
reason: string
description: string
createdAt: string
createdByUid: string
createdByName: string
```

Common action types:

```text
participare
punctualitate
task
initiativa
impact
cross-team
bonus
penalizare
```

Purpose:

* record why points were added or removed
* create transparent volunteer history
* calculate monthly totals
* support dashboard activity feed
* support engagement status

## departmentSettings

Stores department configuration and coordinator assignment.

Path:

```text
zborHubTgJiu/departmentSettings/{departmentId}
```

Expected fields:

```text
id: string
displayName: string
coordinatorUid: string | null
coordinatorName: string | null
target: string
notes: string
updatedAt: string
```

Allowed department IDs:

```text
hr
pr
create
```

Purpose:

* store department display name
* assign one coordinator per department
* store monthly objective
* store internal notes

## pointRules

Stores editable point rules.

Path:

```text
zborHubTgJiu/pointRules/{ruleType}/{ruleId}
```

Rule types:

```text
positive
negative
```

Expected fields:

```text
id: string
type: string
title: string
description: string
points: number
createdAt: string
updatedAt: string
```

Purpose:

* explain how points are awarded
* explain how points are removed
* keep the scoring system transparent

## ruleMessages

Stores general messages shown on the points legend page.

Path:

```text
zborHubTgJiu/ruleMessages
```

Expected fields:

```text
monthlyPrize: string
negativeRule: string
riskRule: string
updatedAt: string
```

Purpose:

* explain the monthly prize
* explain negative points
* explain the risk rule

## Access model

Current intended access model:

### Anonymous volunteer

Can read basic platform data.

Should not write data.

### Department coordinator

Can manage volunteers and actions.

Should eventually be limited to their department.

### Community manager

Can manage all users, volunteers, departments, actions, and point rules.

## Security requirements

The database rules should enforce:

* no public writes
* only authenticated managers can create users
* only valid roles can be saved
* only valid departments can be saved
* volunteers cannot edit data
* points must be numbers
* point values must stay within a safe range
* required fields must exist
* inactive users cannot manage data
* important writes should be logged

## Privacy requirements

The database may contain real names, emails, departments, and activity history.

Rules:

* do not upload database exports to GitHub
* do not publish screenshots with personal data
* use anonymized demo data for public presentations
* keep backups private

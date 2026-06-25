# Security rules change log

## Before Security Rules v1

Date: 2026-06-25

Current rules were copied into:

backup-private/database-rules-before-security-v1.json

Reason:

The project is already live and used by real volunteers. Rules must be changed carefully.

Security goals:

1. Keep the live app working.
2. Keep staging working.
3. Block unauthenticated database access.
4. Block public writes.
5. Allow anonymous volunteer accounts to read only through the app.
6. Allow managers and coordinators to write operational data.
7. Later restrict department coordinators to their own departments.
8. Later separate public volunteer view from private manager data.
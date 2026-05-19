TryHackMe OWASP TOP_TEN Room

Failures in how Identity, Authentication, Authorisation, and Accountability (IAAA)

A01: Broken Access Control
A07: Authentication Failures
A09: Logging & Alerting Failures

Identity - the unique account (e.g., user ID/email) that represents a person or service.
Authentication - proving that identity (passwords, OTP, passkeys).
Authorisation - what that identity is allowed to do.
Accountability - recording and alerting on who did what, when, and from where.

Broken Access Control happens when the server doesn’t properly enforce who can access what on every request.  IDOR (Insecure Direct Object Reference)

Authentication Failures happen when an application can’t reliably verify or bind a user’s identity. Used username: aDmin to trick the server into confusion.

Accountability is the key piece of IAAA since we use it to track, detection and learn from incidents. 

A01 Broken Access Control: Enforce server-side checks on every request
A07 Authentication Failures: Enforce unique indexes on the canonical form, rate-limit/lock out brute force, and rotate sessions on password/privilege changes.
A09 Logging & Alerting Failures: Log the full auth lifecycle (fail/success, password/2FA/role changes, admin actions), centralise logs off-host with retention, and alert on anomalies (e.g., brute-force bursts, privilege elevation).

https://tryhackme.com/room/owasptopten2025one?utm_campaign=social_share&utm_medium=social&utm_content=share-completed-room&utm_source=copy&sharerId=6682ddd2110a18c8c54faa6b
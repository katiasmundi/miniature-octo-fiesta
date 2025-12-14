# Authorization Test Report

The following actions and findigs were identified through manual exploration, OWASP ZAP scanning, and endpoint fuzzing (ffuf).

## 1️⃣ Endpoint & Action List

UI Pages:
- /
- /login
- /register
- /resources
- /reservation?id={id}
- /status.html

API Endpoints:
- GET /api/users
- GET /api/resources
- GET /api/reservations
- GET /api/reservations/{id}
- POST /api/reservations
- PUT /api/reservations/{id}
- DELETE /api/reservations/{id}

## 2️⃣ Findings



## 3️⃣ Roles

## Guest

✅ Can do
  - Can view public resource list — /
  - Can access login form — /login
  - Can access the registration form — /register
  - Can access system status page — /status.html
  - Can access full resource list /api/resources
  - Can access full reservations list /api/reservations
  - Can access full user list — /api/users

❌ Cannot do
  - Cannot create reservations via UI — /reservation
  - Cannot access reservation creation form (redirected to login)
  - Cannot access admin pages — /admin
  - Cannot access user management UI
  - Cannot authenticate as another user via frontend

<img width="557" height="642" alt="image" src="https://github.com/user-attachments/assets/24b86ab6-7d63-43b3-81a4-fa70f9ae55af" />
<img width="1004" height="221" alt="image" src="https://github.com/user-attachments/assets/4fa939d3-b1ab-4546-a348-aa66700d6edb" />
<img width="944" height="1063" alt="image" src="https://github.com/user-attachments/assets/c41258d4-c24c-4183-86ba-9587db72a665" />

## Reserver

✅ Can do
  - Can log in to the system
  - Can create reservations for themselves — POST /api/reservations
  - Can access reservations belonging to other users via IDOR — GET /api/reservations/{id}
  - Can modify reservation ownership by changing the reserver field
  - Can delete reservations after reassigning ownership

❌ Cannot do
  - Cannot access admin-only UI elements directly
  - Cannot officially manage users via frontend
  - Cannot modify system-wide resources through intended UI controls

<img width="1004" height="736" alt="image" src="https://github.com/user-attachments/assets/f94eff79-6ad0-4eac-9faf-0e581652ff9f" />
<img width="1004" height="382" alt="image" src="https://github.com/user-attachments/assets/f801d0c6-2528-4bb5-b42d-7a52ef2a2778" />
<img width="983" height="177" alt="image" src="https://github.com/user-attachments/assets/5569074f-6278-4df1-8b13-a9fd5ff4855a" />
<img width="1004" height="754" alt="image" src="https://github.com/user-attachments/assets/61917c8a-cf4c-4cfa-96cd-6bf3ffe3c8d4" />
<img width="1004" height="314" alt="image" src="https://github.com/user-attachments/assets/5c318bc5-951d-492d-b7ff-a79cddffb900" />


## Administrator

✅ Can do
  - Can log in as administrator
  - Can add, modify, and delete resources
  - Can create, modify, and delete any reservation
  - Can change reservation ownership

❌ Cannot do
  - Cannot modify or delete users (or atleast I didnt't find a way)
  - Cannot rely on backend authorization to prevent lower roles from accessing admin data
  - Cannot prevent reservation enumeration via predictable IDs

<img width="1004" height="536" alt="image" src="https://github.com/user-attachments/assets/a69eccf5-6c6a-4bab-b7cf-6ebf4bf20cc1" />






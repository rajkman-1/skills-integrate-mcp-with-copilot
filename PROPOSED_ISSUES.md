# Proposed Issues — Extracurricular Features

Below are proposed GitHub issues to implement feature parity and improvements inspired by the Ayushmanas student-extracurricular project.

---

## 1) Add persistent database and schema
**Description:** Replace the in-memory activity store with a persistent relational database (Postgres or MySQL). Implement a schema for `students`, `activities`, `enrollments`, `faculty`, and `users` based on the `student.sql` structure.

**Acceptance criteria:**
- Database configuration and connection added.
- SQL migration or ORM models for `students`, `activities`, `enrollments`, `faculty`, `users`.
- Endpoints persist and read from DB.

**Labels:** enhancement, backend

---

## 2) Implement user authentication and roles
**Description:** Add secure authentication with user roles (admin, faculty, student). Implement login, logout, and protected routes for admin operations.

**Acceptance criteria:**
- Passwords hashed (bcrypt/argon2).
- JWT or session-based auth implemented for API and admin UI.
- Role-based access control: only admins can enroll/edit/delete students.

**Labels:** enhancement, security

---

## 3) Admin dashboard & student CRUD
**Description:** Add admin UI (or server-rendered pages) for enrolling, editing, viewing, and deleting student records, matching the flows in `dashboard.php` (Enroll, Edit, View, Delete).

**Acceptance criteria:**
- Admin endpoints for create/read/update/delete student records.
- Admin UI page linked from repo `static` or new frontend.
- Server-side validation and basic UX for forms.

**Labels:** enhancement, frontend, backend

---

## 4) Support student profile images and uploads
**Description:** Allow storing student photos (as files or blob storage). Add upload endpoint, storage strategy, and display in student details.

**Acceptance criteria:**
- Image upload endpoint with size/type checks.
- Store images on disk or cloud and save path in DB (or store as blob if desired).
- Display image in student profile UI.

**Labels:** enhancement, storage

---

## 5) Migrate activity enrollment to DB relationships
**Description:** Replace arrays of `participants` with proper `enrollments` table linking students to activities; update signup/unregister endpoints to operate on DB.

**Acceptance criteria:**
- `enrollments` table and ORM model added.
- `POST /activities/{name}/signup` and `DELETE /activities/{name}/unregister` update the DB.
- Proper uniqueness and capacity checks.

**Labels:** enhancement, backend

---

## 6) Add faculty records and activity assignment
**Description:** Add `faculty` table and API to assign faculty to activities (for scheduling and admin responsibilities).

**Acceptance criteria:**
- `faculty` model and CRUD endpoints.
- Activity -> faculty relationship implemented.
- Admin UI to assign/unassign faculty to activities.

**Labels:** enhancement, backend

---

## 7) Add tests and CI
**Description:** Add unit and integration tests for API endpoints and a CI workflow to run tests on push.

**Acceptance criteria:**
- Test suite covering DB integration, auth, and enrollment flows.
- GitHub Actions workflow that runs tests on PR and push.

**Labels:** tests, ci

---

*If you want, I can open real GitHub issues from these drafts next — confirm and I'll create them.*

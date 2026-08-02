### FR-001 – User Authentication

**Description**

The system shall provide a secure authentication mechanism for Citizens, Officers, and Administrators through a common login interface using email and password.

**Actors**

- Citizen
- Officer
- Administrator

**Priority**

High

**Preconditions**

- User account exists.
- User is not currently logged in.

**Postconditions**

- User is authenticated.
- A secure JWT access token is generated.
- User is redirected to the appropriate dashboard based on role.

**Acceptance Criteria**

- Valid credentials authenticate successfully.
- Invalid credentials are rejected.
- Passwords are stored as secure hashes.
- Users cannot access unauthorized dashboards.

### FR-002 – Citizen Registration

**Description**

The system shall allow citizens to create an account by providing their full name, email address, mobile number, password, state, and preferred language.

The system shall automatically generate a unique Citizen ID.

**Actors**

- Citizen

**Priority**

High

**Acceptance Criteria**

- Duplicate email addresses are rejected.
- Password meets security requirements.
- Citizen ID generated automatically.
- Account created successfully.

### FR-003 – Officer Account Management

**Description**

The system shall allow Administrators to create, update, deactivate, and manage Officer accounts.

Officers shall not be permitted to self-register.

**Actors**

- Administrator

**Priority**

High

**Acceptance Criteria**

- Only Administrators can create Officer accounts.
- Officer receives login credentials.
- Deactivated Officers cannot log in.

### FR-004 – Administrator Account Management

**Description**

The system shall restrict Administrator account creation to authorized system administrators.

Administrator accounts shall not support public registration.

**Actors**

- Administrator

**Priority**

High

**Acceptance Criteria**

- Public registration is unavailable.
- Only authorized Administrators can create new Administrator accounts.

### FR-005 – Role-Based Access Control

**Description**

The system shall enforce role-based authorization to ensure users can only access resources and functionalities permitted for their assigned role.

**Actors**

- Citizen
- Officer
- Administrator

**Priority**

High

**Acceptance Criteria**

- Citizens cannot access Officer or Admin pages.
- Officers cannot access Admin features.
- Unauthorized API requests return appropriate error responses.
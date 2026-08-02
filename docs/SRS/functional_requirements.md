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

# Module 2 – Citizen Complaint Management

---

### FR-006 – Create Complaint

**Description**

The system shall allow authenticated citizens to create a new grievance by entering complaint details and uploading supporting evidence.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Preconditions**

- Citizen is logged in.

**Postconditions**

- Complaint is created as a draft.
- Complaint receives a unique Complaint ID.

**Acceptance Criteria**

- Complaint form opens successfully.
- Complaint ID generated automatically.
- Draft saved successfully.

---

### FR-007 – AI Complaint Assistant

**Description**

The system shall provide an AI-powered complaint assistant that helps citizens convert natural language into a clear, structured grievance.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Acceptance Criteria**

- AI generates structured complaint text.
- Citizen may edit AI-generated content.
- AI suggestions are optional.

---

### FR-008 – AI Complaint Analysis

**Description**

Before submission, the system shall analyze the complaint and provide intelligent recommendations to improve complaint quality.

The analysis shall include:

- Complaint Quality Score
- Complaint Readiness Indicator
- Grammar improvement
- Missing information detection

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Acceptance Criteria**

- Analysis completes successfully.
- Suggestions displayed clearly.
- Citizen may ignore recommendations.

---

### FR-009 – Department Recommendation

**Description**

The system shall recommend the most appropriate government department based on complaint content.

Citizens shall have the option to accept or manually change the recommended department.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Acceptance Criteria**

- Department recommendation generated.
- Confidence score displayed.
- Manual override supported.

---

### FR-010 – Draft Management

**Description**

The system shall automatically save complaint drafts and allow citizens to continue editing them later.

**Actors**

- Citizen

**Priority**

Medium

**Status**

Approved

**Acceptance Criteria**

- Draft auto-saved periodically.
- Citizen can reopen drafts.
- Draft can be edited until final submission.

### FR-011 – Upload Supporting Evidence

**Description**

The system shall allow citizens to upload supporting documents such as images, PDF files, and other relevant evidence while creating or updating a complaint draft.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Preconditions**

- Citizen is logged in.
- Complaint draft exists.

**Postconditions**

- Uploaded files are securely stored.
- Files are linked to the corresponding complaint.

**Acceptance Criteria**

- Multiple files can be uploaded.
- Supported file formats are accepted.
- Invalid or oversized files are rejected with an appropriate message.

### FR-012 – AI Duplicate Complaint Detection

**Description**

The system shall analyze newly created complaints and identify similar complaints using semantic similarity techniques.

The system shall notify the citizen if similar complaints already exist before final submission.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Preconditions**

- Complaint draft exists.

**Postconditions**

- Similar complaints are displayed.

**Acceptance Criteria**

- Similar complaints are identified.
- Citizen may ignore the recommendation and continue.
- Duplicate detection shall not prevent complaint submission.

### FR-013 – Complaint Submission

**Description**

The system shall allow citizens to submit a complaint after completing the required information and AI analysis.

Upon submission, the complaint shall be assigned a unique Complaint ID and routed to the selected government department.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Preconditions**

- Complaint draft completed.

**Postconditions**

- Complaint submitted successfully.
- Complaint status initialized as "Submitted."

**Acceptance Criteria**

- Complaint receives a unique ID.
- Department assigned successfully.
- Citizen receives submission confirmation.

### FR-014 – Complaint Tracking

**Description**

The system shall allow citizens to monitor the current status and progress of submitted complaints.

**Actors**

- Citizen

**Priority**

High

**Status**

Approved

**Acceptance Criteria**

- Current complaint status displayed.
- Timeline of status updates available.
- Department handling the complaint displayed.
- Last updated timestamp displayed.

### FR-015 – Complaint History

**Description**

The system shall maintain a history of all complaints submitted by a citizen and allow them to search and filter previous complaints.

**Actors**

- Citizen

**Priority**

Medium

**Status**

Approved

**Acceptance Criteria**

- Previous complaints displayed.
- Search functionality available.
- Filter by complaint status and submission date.
- Complaint details accessible.
### Nike Material Workspace – High-Level Architecture
                      
                           +----------------------------+
                           |        Admin User          |
                           +-------------+--------------+
                                         |
                                  HTTPS / Okta Auth
                                         |
                           +--------------------------------+
                           |   React Admin Dashboard        |
                           |  (SPA + EDS Component Library) |
                           +--------------------------------+
                                          |
                           +--------------------------------+
                           | - Business logic: CRUD for     |
                           |   Fabrics, Leathers, Colors,   |
                           |   Styles, BOM                  |
                           +--------------------------------+
                                         |
                                   [Axios API Layer]
                                         |
                             [RESTful / GraphQL API calls]
                                         |
                            [Nike Material Workspace REST APIs]
                                         |
                               [Nike Databases & Services]



|                       CI/CD Pipeline                     |
|----------------------------------------------------------|
| - Code Repository: GitHub                                |
| - Code Analysis (ESLint, Prettier)                       |
| - Unit/Integration Tests (Vite, React Testing Library)   |
| - Build & Bundle React App (Webpack)                     |
| - Deploy Frontend:Jenkins Job                            |




### Frontend Architecture (React)
✅ React + Vite for SPA

✅ React Router for route-based code splitting

✅ Redux Toolkit for global state

✅ Axios  Query for API data fetching

✅ Component Library Nike's EDS component

✅ Form management via React Hook Form

✅ Charting using Recharts

✅ Testing with Vite + React Testing Library



### Presentation Layer (React UI)

🔷 Layout Components
DashboardLayout: main container with

Header: logo, user profile, logout

Sidebar: navigation links to each CRUD section

Content: main view area to render child pages

🔷 CRUD Pages & Components
For each entity, create:

EntityPage: e.g., FabricsPage, LeathersPage, etc.

Shows table/grid of items

Has “Add”, “Edit”, “Delete” buttons

EntityForm: e.g., FabricForm, LeatherForm, etc.

Modal or page for create/update form

EntityTable: table/grid listing entity records with pagination and actions

Entities you’ll cover:
✅ Fabrics
✅ Leathers
✅ Colors
✅ Styles
✅ BOM (Bill of Materials)

🔷 Admin User Management
AdminUsersPage: list all admin users

AdminUserForm: create/edit admin user

AdminUserTable: display admin users with roles/status/actions

🔷 Shared / Reusable Components
Modal: confirmation dialogs, forms

Notification/Toast: success/error messages

Breadcrumbs: navigation aid inside the dashboard

Loader/Spinner: for async operations

🔷 Routing
Use React Router to map paths to CRUD pages:

/fabrics, /leathers, /colors, /styles, /bom

/admin-users

### Authentication Layer (OktaAuth)

Okta React SDK for login/logout and token management.

User info (profile, roles) extracted from the Okta ID token.


4️⃣ API Integration Layer

Axios instance with interceptor:

Attaches Okta access token to every API request.

Handles 401 errors with automatic redirect to login.

Communication with Nike Material Workspace services to CRUD:




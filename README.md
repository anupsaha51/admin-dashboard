### High-Level Architecture
                      
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


+----------------------------------------------------------+
|                       CI/CD Pipeline                     |
|----------------------------------------------------------|
| - Code Repository: GitHub                                |
| - Code Analysis (ESLint, Prettier)                       |
| - Unit/Integration Tests (Vite, React Testing Library)   |
| - Build & Bundle React App (Webpack)                     |
| - Deploy Frontend:Jenkins Job                            |
+----------------------------------------------------------+



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

components for:

Dashboard Layout (Header, Sidebar, Content)

Material Libraries

Material Inventory Tables

Admin User Management

### Authentication Layer (OktaAuth)

Okta React SDK for login/logout and token management.

User info (profile, roles) extracted from the Okta ID token.


4️⃣ API Integration Layer

Axios instance with interceptor:

Attaches Okta access token to every API request.

Handles 401 errors with automatic redirect to login.

Communication with Nike Material Workspace services to CRUD:




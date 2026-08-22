Dayflow — Human Resource Management System (HRMS)Every workday, perfectly aligned.Dayflow is a modular, zero-dependency, single-page Human Resource Management System built with native HTML5, modern CSS3, and ES6 Javascript. It digitizes core HR workflows including role-based access, attendance tracking with clock-in/out toggles, leave management approval queues, payroll visibility with PDF payslip downloads, and visual analytics.Technical Architecturedayflow-hrms/
├── index.html                # Main SPA Shell & Entry Container
├── css/
│   ├── variables.css         # CSS Custom Properties (Colors, Typography, Elevation)
│   ├── base.css              # Global Resets & Typography Base
│   ├── animations.css        # Smooth Transitions & View Animations
│   └── components.css        # UI Cards, Tables, Badges, Modals, Toasts
├── js/
│   ├── core/
│   │   ├── store.js          # Centralized LocalStorage DB & State Management
│   │   ├── auth.js           # Auth Logic & Role-Based Route Guards
│   │   ├── router.js         # Hash-based SPA Navigation Router
│   │   └── seed.js           # Mock Initializer for First-Time Setup
│   ├── components/
│   │   ├── sidebar.js        # Dynamic Navigation Menu
│   │   ├── topbar.js         # Header Navigation & User Profile Control
│   │   ├── modal.js          # Reusable Modal Wrapper
│   │   ├── toast.js          # Global Alert & Notification System
│   │   └── table.js          # Reusable Dynamic Data Table Renderer
│   └── pages/
│       ├── auth.js           # Sign In & Sign Up Views
│       ├── dashboard.js      # Quick Stats & Action Cards
│       ├── profile.js        # Employee Profile Management
│       ├── attendance.js     # Daily/Weekly Clock-In & Time Logs
│       ├── leave.js          # Leave Applications & HR Approvals Queue
│       ├── payroll.js        # Salary Structure & PDF Pay Slip Exporter
│       └── analytics.js      # Attendance & Department Reports
└── README.md                 # System Documentation & Setup Guide
Core Features & Role AccessModuleFeature CapabilitiesEmployeeAdmin / HRAuthenticationSign up with employee ID, email validation, and role assignment✓✓DashboardOverview cards, time-aware greeting, pending tasks, recent alertspersonalorg-wideProfile ManagementView profile info, update personal details (phone, address, avatar)edit selfedit allAttendance TrackingInteractive check-in / check-out toggle, daily & weekly logspersonalorg-wideLeave ManagementApply for paid/sick/unpaid leave, check status, review approvalssubmitapprove/rejectPayroll VisibilitySalary breakdown view, monthly pay structure, PDF payslip exportviewedit/manageAnalytics DashboardHeadcount metrics, department distributions, attendance breakdown—✓Quick Start & InstallationBecause Dayflow uses native ES6 JavaScript modules, it can run directly in any modern browser using a static server.PrerequisitesA modern browser (Chrome, Firefox, Edge, Safari) and a simple HTTP static file server.Running LocallyOption 1: PythonBash# In the root directory of dayflow-hrms
python3 -m http.server 8080
Then navigate to http://localhost:8080 in your web browser.Option 2: Node.js / serveBashnpx serve .
Option 3: VS Code Live ServerRight-click index.html inside VS Code and select "Open with Live Server".Pre-Seeded Test CredentialsThe application auto-populates mock data into localStorage on initial load. You can log in using these preset credentials:Admin / HR OfficerEmail: admin@dayflow.comPassword: Admin123!Permissions: Full management access, organization-wide attendance & leave approvals, salary structure editor, analytics.Standard EmployeeEmail: alex@dayflow.comPassword: User123!Permissions: Personal dashboard, personal clock-in/out, leave application form, read-only pay slip view.Customization & Extension GuidelinesStyling & Themes: Modify design tokens inside css/variables.css to update global color palettes, radius settings, shadows, and typography.Adding New Routes: Define your page component inside js/pages/, import it into js/core/router.js, and map the hash path (e.g., #/new-feature).Database Reset: To purge test state and reset to seeded defaults, clear localStorage via DevTools Console:JavaScriptlocalStorage.clear();
location.reload();

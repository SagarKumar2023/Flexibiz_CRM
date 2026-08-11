# Flexibiz CRM

## Project Overview
Flexibiz CRM is a robust Flutter-based mobile application designed for field staff and CRM managers. It facilitates efficient lead management, activity tracking, project monitoring, and attendance recording. The application integrates with Flexibiz ERP to provide real-time data access and streamlined business processes for field operations.

## App Screenshots
Access the full visual gallery of the application here: [App Screenshots Document](https://docs.google.com/document/d/1kwBpxqYpc2auh94gFIYURh-wiAR71-6LSpENyxDJz4o/edit?usp=sharing)

## Key Features
*   **Comprehensive Activity Tracking:** Manage leads, contacts, customers, complaints, and inquiries in one place.
*   **Field Staff Attendance:** Geolocation-based mark-in/mark-out with attendance history.
*   **Task & ToDo Management:** Track personal and team tasks with status updates.
*   **Expense Management:** Offline-first tour expense tracking using Hive database.
*   **Project & Work Order Monitoring:** Real-time access to project details and work orders.
*   **Contact Management:** Synchronize business contacts with the mobile device.
*   **Multi-Layered Authentication:** Secure login using Register URL, Client ID, and User credentials.

## Application Modules

### Authentication
*   **Purpose:** Secure user access to the CRM system.
*   **Functionality:** Register link validation, dual-factor login (Client ID & Username), and session persistence ("Keep me logged in").
*   **Status:** Completed.

### Dashboard
*   **Purpose:** Central hub for all CRM operations.
*   **Functionality:** Grid-based navigation to Activities, Projects, Attendance, Expenses, and Tasks.
*   **Status:** Completed.

### Activity Management
*   **Purpose:** Core CRM module for managing business interactions.
*   **Functionality:** Sub-modules for Leads, Contacts, Customers, Complaints, and Inquiries. Supports notes, attachments, follow-ups, and location updates.
*   **Status:** Completed.

### Attendance Module
*   **Purpose:** Track employee presence and location.
*   **Functionality:** Mark In, Mark Out, Delete Attendance, and View Attendance History.
*   **Status:** Completed.

### Tour Expenses
*   **Purpose:** Record field expenses on the go.
*   **Functionality:** Offline storage of expenses (Place, Date, Amount, Remarks).
*   **Status:** Completed.

### Work Order & Projects
*   **Purpose:** Monitor operational tasks and project progress.
*   **Functionality:** View detailed project info and work order criteria-based search.
*   **Status:** Partially Implemented (UI and search flows exist).

## User Flow
1.  **Splash Screen:** Initial app loading and session check.
2.  **URL Registration:** User enters the ERP server link.
3.  **Login:** User enters Client ID/Password and Username/Password.
4.  **Dashboard:** Access to all major CRM modules via a responsive grid.
5.  **Module Interaction:** User performs actions like logging activities, marking attendance, or recording expenses.
6.  **Data Synchronization:** Data is stored locally or sent to the backend via APIs.

## Technology Stack

| Technology | Usage |
| ---------- | ----- |
| Flutter | Cross-platform mobile framework |
| Dart | Programming language |
| GetX | State management and Navigation |
| Riverpod | State management (ProviderScope) |
| Hive | Local NoSQL database for offline expenses |
| Shared Preferences | Persistent local storage for user sessions |
| Google Maps | Location tracking and routing |
| Socket.io | Real-time communication |
| HTTP | REST API integration |

## Architecture
The project follows a **Feature-based Architecture** with a clear separation of concerns:
*   **UI Layer:** Located in `lib/screens/` and `lib/widgets/`, using reusable components.
*   **Logic Layer:** Uses Controllers (GetX) and Providers (Riverpod) to handle business logic.
*   **Data Layer:** Models in `lib/model/` and Local Database utilities in `lib/local_database/`.
*   **Constants:** Centralized management of colors, images, and URLs in `lib/constant/`.

## Project Structure
```text
lib/
├── constant/             # App constants (colors, images, URLs, prefs)
├── local_database/      # Hive database setup and models
├── model/               # Data models
├── screens/             # Feature-based UI screens
│   ├── authentication/  # Login and registration flows
│   ├── dashboard/       # Main dashboard and sub-modules
│   └── provider/        # Business logic controllers
└── widgets/             # Reusable UI components
```

## State Management
*   **GetX:** Used for reactive UI updates and simplified navigation.
*   **Riverpod:** Implemented via `ProviderScope` in `main.dart` for robust dependency injection and state handling.

## API Integration
*   **Service:** Centralized API endpoint management in `AppUrl` class.
*   **Request Handling:** Uses `http` package for communicating with the ERP backend.
*   **Authentication:** Token-based authentication stored in `Shared Preferences`.

## Local Storage
*   **Hive:** Used for storing "New Tour Expenses" locally, allowing offline entry.
*   **Shared Preferences:** Stores user login status, tokens, unique IDs, and profile information.

## UI / UX
*   **Theme:** Material 3 design with a custom color palette (Primary & Secondary).
*   **Components:** Custom `TextFieldWidget`, `ButtonWidget`, `TextWidget`, and `AnimatedShowGeneralDialog`.
*   **Responsive Design:** Optimized for various Android and iOS screen sizes using custom `screen_Size` utilities.

## Installation & Setup
1.  **Clone the Repository:** `git clone <repository_url>`
2.  **Install Dependencies:** Run `flutter pub get`.
3.  **Local Database:** Run `flutter pub run build_runner build` (if Hive models are modified).
4.  **Run the App:** `flutter run` on an emulator or physical device.

## Configuration
*   **API Base URL:** Configure in `lib/constant/AppUrl/app_Url.dart`.
*   **Maps API:** Ensure Google Maps API keys are added to `AndroidManifest.xml` and `AppDelegate.swift`.

## Current Development Status
### Completed
*   Authentication System (URL/Client/User)
*   Dashboard UI & Navigation
*   Activity Management (Leads, Contacts, etc.)
*   Attendance (Mark In/Out)
*   Local Expense Tracking (Hive)
*   ToDo & Task Management

### Partially Implemented / In Progress
*   Work Order search and details.
*   Project progress tracking.
*   Web menu integration.

## Author
**Developed by:** Sagar Kumar
**Role:** Flutter Developer

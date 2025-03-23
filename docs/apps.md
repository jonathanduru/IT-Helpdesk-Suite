# 🧠 Power Apps – Ticketing System

This app is part of the **IT Helpdesk Suite**, designed to let employees submit tickets and allow IT staff to manage them through a Model-Driven App interface.

---

## 🗂 Ticket Management (Model-Driven App)

**Purpose:**  
Used by IT staff to view, filter, and update tickets efficiently in a structured Dataverse view.

### ✅ Features:
- Displays all submitted tickets with filtering and sorting
- Columns: Ticket ID, Title, Priority, Status, Owner, Assigned Resource, Last Updated, Resolution Notes
- Integrated with Power Automate flows for status updates and notifications
- Fields automatically updated by technician actions (e.g. resolving tickets)

### 📸 Example View:
![Tickets View](../assets/screenshots/ticket-list-view.png) <!-- Replace this with actual screenshot filename -->

---

## 🎨 Ticket Submission App (Canvas App) *(Planned)*

**Purpose:**  
User-friendly front-end for employees to create new support tickets from desktop or mobile.

### Planned Features:
- Form to capture issue title, description, priority, and related asset
- Confirmation screen + ticket reference ID
- Optional: view ticket history or status

---

## 🗃 Dataverse Table: `Tickets`

**Core columns:**
- `Ticket ID` – Custom formatted unique ID (e.g., TIC-2025-000101)
- `Title` – Short description of the issue
- `Priority` – Low, Medium, High, Critical
- `Status` – Open, In Progress, Resolved, Closed
- `Assigned Resource` – Lookup to user/team
- `Resolution Notes` – Multiline text field
- `Created On` / `Last Updated` – System timestamps

---

📂 You can find app exports in `/exported-components/`


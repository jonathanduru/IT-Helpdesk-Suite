# 🔄 Power Automate Flows

This page documents the Power Automate flows used in the **IT Helpdesk Suite**.  
Each flow supports ticket lifecycle automation, asset tracking, or team communication.

---

## SLA Date Assignment Flow

- **Trigger:** When a new ticket is created in Dataverse  
- **Purpose:** Set the SLA due date based on ticket priority

### Logic:
- Low → +3 days  
- Medium → +2 days  
- High → +1 day  
- Critical → +4 hours  

### Steps:
1. Get ticket by ID  
2. Switch on Priority  
3. Use Compose to calculate SLA date
4. Update SLA Date field

#### Example Expression (Critical Priority)
- Adds 4 hours to the ticket's Created On date to calculate the SLA deadline for Critical tickets
```plaintext
addHours(outputs('Get_a_row_by_ID_-_Ticket')?['body/createdon'], 4)
```

![SLA Flow](https://raw.githubusercontent.com/jonathanduru/IT-Helpdesk-Suite/refs/heads/main/assets/screenshots/SLAdateFlow.png)


---

## 📧 New Ticket Notification Flow

- **Trigger:** When a new ticket is created in Dataverse
- **Purpose:** Notify IT staff of new submissions
- **Actions:**
  - Compose message with ticket title, priority, and description
  - Send Adaptive Card to Teams channel
  - Add timeline note to ticket record

---

## 🔄 Ticket Status Update Flow

- **Trigger:** When a ticket is updated
- **Purpose:** Automatically update ticket status based on technician input
- **Logic:**
  - If technician assigned → set to "In Progress"
  - If resolved date filled → set to "Closed"
  - Logs changes to audit table

---

## ⏰ SLA Reminder Flow *(In Progress)*

- **Trigger:** Every 1 hour (scheduled)
- **Purpose:** Identify tickets close to SLA breach
- **Planned Logic:**
  - Find tickets due within 24 hours
  - Send email or Teams reminder to technician
  - Mark record as "SLA Warning"

---

## ✅ Coming Soon

- Asset maintenance trigger flow  
- Escalation to supervisor based on category/priority  
- Auto-assign based on skillset or availability

---

📁 Exported versions of these flows will be available in `/exported-components/flow-definitions/`


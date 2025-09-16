# Rapid-Custom-Task-Agent (RCTA)

Current Counterpoint features using RCTA:
1. Rapid Automated Reporting
2. Raipd Automated Purchase Order (PO) Send
3. Rapid Bound Book Local Copy
4. Rapid (S)FTP File Sender

# Rapid Custom Task Agent (RCTA) – Overview

## 📌 What is RCTA?

The **Rapid Custom Task Agent (RCTA)** is a powerful, automated task engine developed by **Rapid POS**. It is designed to execute scheduled tasks in the background, eliminating the need for manual intervention. RCTA runs as a **Windows service** and is commonly used to automate processes within **Counterpoint** environments.

Using simple, human-readable **YAML configuration files**, RCTA enables you to define and run a wide variety of automated workflows such as:

- Report generation and email delivery
- Data extraction from SQL databases
- File transfer to external systems via FTP or SFTP
- Integration with third-party APIs or internal scripts

---

## ⚙️ How It Works

RCTA operates by reading structured YAML files that define a series of **tasks**. Each task contains:

- A **name** and **description**
- A **trigger**, such as a scheduled time (using cron syntax) or file system change
- A list of **variables** used for dynamic values (e.g., database credentials)
- A series of **steps**, which define what the task does

When a trigger condition is met, RCTA executes each step in order.

---

## 🧩 Core Features

RCTA includes several pre-configured features designed to handle common automation scenarios for Counterpoint users:

### 📄 Rapid Automated Reporting
Automatically generates Crystal Reports based on scheduled jobs defined inside Counterpoint, and emails them to specified recipients.

- Users configure report settings inside Counterpoint.
- RCTA reads the report schedule and sends reports in formats like PDF, XLS, or CSV.
- All activity is logged for auditing and troubleshooting.

### 📦 Rapid Automated Purchase Order (PO) Send
Extracts Purchase Orders from Counterpoint and sends them automatically via email or FTP/SFTP to vendors.

- Scheduled execution with no user interaction required.
- Supports custom PO formats and secure delivery methods.

### 🔒 Rapid Bound Book Local Copy
Maintains a local copy of firearm transaction data for ATF compliance.

- Runs on a schedule to generate and store a complete copy of bound book records.
- Ensures local backup is always up to date.

### 🌐 Rapid File Sender (FTP/SFTP)
Executes SQL queries, generates `.CSV` files, and securely transfers them to client or vendor FTP/SFTP directories.

- Fully configurable SQL source and destination folder.
- Secure protocols (SFTP, FTPS) supported.
- Used for integrations with external inventory, accounting, or compliance systems.

---

## 🛠️ Installation & Operation

- RCTA runs as a Windows service:  
  `RapidPOS.Service.CustomTaskAgent`
- YAML configuration files are stored in:  
  `C:\Program Files\Rapid POS\RapidPOS.Service.CustomTaskAgent\work\yaml\rapid`
- Logs are written to:  
  `C:\Program Files\Rapid POS\Logs\RapidPOS.Service.CustomTaskAgent.log`
- The service automatically starts after a reboot and runs quietly in the background.

---

## 🔍 Monitoring & Troubleshooting

- Check **Windows Services** to ensure the agent is running.
- Review the **log file** for task status, success, and errors.
- YAML configurations can be updated as needed without redeploying the application (just restart the service).

---

## ✅ Benefits

- **Automation-first**: Eliminate manual report running, emailing, or file uploads.
- **Highly configurable**: Easy-to-edit YAML files allows for quick customization.
- **Secure & compliant**: Integrates with secure email, database, and SFTP protocols.
- **Low maintenance**: Once configured, it runs continuously and silently in the background.


# Rapid Custom Task Agent (RCTA)
Updated 7/21/2026

---

The **Rapid Custom Task Agent (RCTA)** is a powerful task engine that automates scheduled tasks within your Counterpoint environment — from report generation and purchase order delivery to custom file, script, and API-driven workflows. It runs quietly in the background, so routine processes happen reliably, on time, and without manual intervention. 

This document outlines RCTA's system requirements, core features, installation details, and operational guidance.

---

## Minimum System Requirements:
- Minimum Counterpoint version: **8.5.6.2**  
- Minimum SQL Server version: **2016**  
- Minimum Supported Operating System version: **Windows Server 2016** or **Windows 11 Pro** 
- Minimum PowerShell version: **5.1**  

If you would like the Rapid Custom Task Agent but your system does not meet these minimum requirements, please consult your Care Team Lead (vCIO) for an upgrade quote.

> [!WARNING]
> Your environment must meet our [CI/CD Connector Requirements](https://github.com/Rapid-POS/Miscellaneous-Documents/blob/main/CICD-Connector-Requirements.md) (server access, firewall rules, etc.) before any install or upgrade. Troubleshooting, manual installs, or follow-up work resulting from unmet requirements will be billed at standard T&M rates.

---

## Core Features

RCTA is a platform with multiple features layered on top of it. Some features are configured within Counterpoint, others are configured using the RCTA YAML file. 

### 1. Rapid Automated Reporting
Automatically generates Crystal Reports based on scheduled jobs defined inside Counterpoint, and emails them to specified recipients.

- Users configure report settings inside Counterpoint.
- RCTA reads the report schedule and sends reports in formats like PDF, XLS, or CSV.
- All activity is logged for auditing and troubleshooting.

### 2. Rapid Automated Purchase Order (PO) Send
Extracts Purchase Orders from Counterpoint and sends them automatically via email or FTP/SFTP to vendors.

- Scheduled execution with no user interaction required.
- Supports custom PO formats and secure delivery methods.

### 3. Rapid Bound Book Local Copy
Maintains a local copy of firearm transaction data for ATF compliance.

- Runs on a schedule to generate and store a complete copy of bound book records.
- Ensures local backup is always up to date.

---

## Additional Custom Tasks
RCTA can also handle the scheduled automation of custom tasks, such as:

- File monitoring, editing, and management
- Executing SQL, PowerShell, and Batch scripts
- File uploading and downloading to external systems via FTP or SFTP
- Communicating with third-party APIs (GET, POST, PUT, DELETE, etc.)

### Configuration & Scoping

- The YAML file must include a task definition for each specific process a client needs RCTA to perform.
- Custom YAML instructions are quoted on a case-by-case basis, and these features may carry a monthly subscription fee. YAML changes are typically quick to customize, which helps keep quotes low for development effort. 
- In some cases, the underlying RCTA functionality must also be expanded to support a new YAML capability — those code-level changes are also quoted as needed. 

---

## How the YAML File Works

RCTA operates by reading one simple, human-readable YAML file that defines a series of **tasks**. Each task contains:

- A **name** and **description**
- A **trigger**, such as a scheduled time (using cron syntax) or a file system change
- A list of **variables** used for dynamic values (e.g., database credentials)
- A series of **steps**, which define what the task does

When a trigger condition is met, RCTA executes each step in order.

---

## Installation & Operation

- RCTA runs as a Windows service:  
  `RapidPOS.Service.CustomTaskAgent`
- The YAML configuration file is stored in:  
  `C:\Program Files\Rapid POS\RapidPOS.Service.CustomTaskAgent\work\yaml\rapid`
- Logs are written to:  
  `C:\Program Files\Rapid POS\Logs\RapidPOS.Service.CustomTaskAgent.log`
- The service automatically starts after a reboot and runs quietly in the background.

---

## Monitoring & Troubleshooting

- Check **Windows Services** to ensure the agent is running.
- Review the **log file** for task status, success, and errors.
- YAML configurations can be updated as needed without redeploying the application (just restart the service).

---

## Benefits

- **Automation-first**: Eliminate manual report running, emailing, or file uploads.
- **Highly configurable**: An easy-to-edit YAML file allows for quick customization.
- **Secure & compliant**: Integrates with secure email, database, and SFTP protocols.
- **Low maintenance**: Once configured, it runs continuously and silently in the background.

# Rapid Custom Task Agent (RCTA)
Updated 6/9/2026

---

The **Rapid Custom Task Agent (RCTA)** automates scheduled tasks within your Counterpoint environment — from report generation and purchase order delivery to custom workflows. Configured through simple YAML files, RCTA runs silently in the background so routine processes happen reliably, on time, and without manual intervention.

This document outlines RCTA's system requirements, core features, installation details, and operational guidance.

---

## Minimum System Requirements:
- Minimum Counterpoint version: **8.5.6.2**  
- Minimum SQL Server version: **2016**  
- Minimum Windows Server version: **2016**  
- Minimum PowerShell version: **5.1**  

If you would like the Rapid Custom Task Agent but your system does not meet these minimum requirements, please consult your Care Team Lead (vCIO) for an upgrade quote.

> [!WARNING]
> Your environment must meet our [CI/CD Connector Requirements](https://github.com/Rapid-POS/Miscellaneous-Documents/blob/main/CICD-Connector-Requirements.md) (server access, firewall rules, etc.) before any install or upgrade. Troubleshooting, manual installs, or follow-up work resulting from unmet requirements will be billed at standard T&M rates.

---

Current Counterpoint features using RCTA:
1. Rapid Automated Reporting
2. Rapid Automated Purchase Order (PO) Send
3. Rapid Bound Book Local Copy

Additional capabilities include scheduled activities such as:
1. File monitoring, editing & management
2. Executing SQL, PowerShell and Batch Scripts
3. FTP uploading and downloading
4. Communicating to REST API (GET, POST, PUT, DELETE, etc.)

# Rapid Custom Task Agent (RCTA) – Overview

## What is RCTA?

The **Rapid Custom Task Agent (RCTA)** is a powerful, automated task engine developed by **Rapid POS**. It is designed to execute scheduled tasks in the background, eliminating the need for manual execution. RCTA runs as a **Windows service** and is commonly used to automate processes within **Counterpoint** environments.

Using simple, human-readable **YAML configuration files**, RCTA enables you to define and run a wide variety of automated workflows such as:

- Report generation and email delivery
- Data extraction from SQL databases
- File transfer to external systems via FTP or SFTP
- Integration with third-party APIs or internal scripts

---

## How It Works

RCTA operates by reading structured YAML files that define a series of **tasks**. Each task contains:

- A **name** and **description**
- A **trigger**, such as a scheduled time (using cron syntax) or file system change
- A list of **variables** used for dynamic values (e.g., database credentials)
- A series of **steps**, which define what the task does

When a trigger condition is met, RCTA executes each step in order.

---

## Core Counterpoint Features

RCTA includes several pre-configured features designed to handle common automation scenarios for Counterpoint users:

### Rapid Automated Reporting
Automatically generates Crystal Reports based on scheduled jobs defined inside Counterpoint, and emails them to specified recipients.

- Users configure report settings inside Counterpoint.
- RCTA reads the report schedule and sends reports in formats like PDF, XLS, or CSV.
- All activity is logged for auditing and troubleshooting.

### Rapid Automated Purchase Order (PO) Send
Extracts Purchase Orders from Counterpoint and sends them automatically via email or FTP/SFTP to vendors.

- Scheduled execution with no user interaction required.
- Supports custom PO formats and secure delivery methods.

### Rapid Bound Book Local Copy
Maintains a local copy of firearm transaction data for ATF compliance.

- Runs on a schedule to generate and store a complete copy of bound book records.
- Ensures local backup is always up to date.

---

## Installation & Operation

- RCTA runs as a Windows service:  
  `RapidPOS.Service.CustomTaskAgent`
- YAML configuration files are stored in:  
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
- **Highly configurable**: Easy-to-edit YAML files allows for quick customization.
- **Secure & compliant**: Integrates with secure email, database, and SFTP protocols.
- **Low maintenance**: Once configured, it runs continuously and silently in the background.


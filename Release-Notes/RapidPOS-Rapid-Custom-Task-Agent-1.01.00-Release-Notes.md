# Rapid Custom Task Agent v1.1.0 Release Notes

_Release Date: September 24, 2025_

### SQL Script Counterpoint User Security Code Fix
The SQL install script has been updated to avoid overriding the **RCTA user’s security code**.

- **Previous Behavior**: The security code in Counterpoint for the RCTA user was hard-coded to `MGR`.  
- **New Behavior**: The value is now **parameter-driven** from the library variable, making it configurable per client.  

### File Stability and Retry Mechanism
A new method was introduced to **wait for file stability** before reading. If the first two attempts fail, the system now retries automatically.  

- **Impact**: Improves success rates and reliability of file handling.  

### Logging Extensions Upgrade
The logging extensions were upgraded to remediate **“file not found”** errors for logs.  

### User Preference Value Updates
The `SY_USR_PREF` SQL script was enhanced:

- **Change**: The `MERGE` statement now updates user preference values if they differ from the default.  
- **Impact**: Ensures user preferences remain accurate and aligned with expected defaults.  

### Dynamic Filename Generation
The file upload process now supports **dynamic filename generation** to include stamp date in filename.

- **For example**:
  - `2025-09-04_company_name.csv`  
  - `2025-09-05_company_name.csv`

---

## Feature Specific Updates: Rapid Automated Reporting

### Weekly Occurrence Logic Fix
Corrected the **`ComputeNextWeeklyOccurrence`** logic:

- **Previous Behavior**: Weekly occurrences began at `0`.  
- **New Behavior**: Weekly occurrences now correctly start at `1`.  

### Report Parameters and Constraint
A new stored procedure was introduced to strengthen reporting data integrity:

- **Change**: Added support for **report parameters**.  
- **Constraint**: Introduced a **foreign key constraint** to prevent accidental deletion of report parameters.

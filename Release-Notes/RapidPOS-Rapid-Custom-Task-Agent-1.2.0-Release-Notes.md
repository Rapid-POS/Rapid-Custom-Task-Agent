# Rapid Custom Task Agent v1.2.0 Release Notes

_Release Date: November, 10, 2025_  

---

## New Functionality  

### Report Configuration Rules  
- Added **built-in validation for report parameters** to help prevent incorrect or incomplete setups before they are saved.  
- Only one report can be scheduled to send at a specific time. This prevents consuming too many resources at once.  
- This new stored procedure will ensure that reports are not misconfigured.  

---

## Bug Fixes and Performance Enhancements  

### Code Optimization  
- Optimized **FTP/SFTP handling** and **report execution logic**, improving performance and reliability when data is transferred and reports are generated.  

### Added Foreign Key Constraint  
- Introduced `FK_USER_RCTA_REPORT_USER_RCTA_REPORT_HDR` in the `USER_RCTA_REPORT` table referencing the `EMAIL_HOST` column in `USER_RCTA_REPORT_HDR` to ensure referential integrity.  
- Enforced a stronger link between report headers and report details so that each report parameter set always belongs to a valid report configuration. This helps keep report definitions clean and consistent over time.  

### Improved Error Messages
- Updated error messages for report parameter issues so they are clearer, more descriptive, and easier for users to understand.    

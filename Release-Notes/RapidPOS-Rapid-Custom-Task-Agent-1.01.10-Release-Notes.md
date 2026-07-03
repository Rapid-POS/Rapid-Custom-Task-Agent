# Rapid Custom Task Agent 1.01.10 Release Notes
_Expected Release Date: July 8, 2026_

---

## Bug Fixes and Performance Enhancements

### Email Validation for Automated Reports

Previously, if an email list for an automated report (in either the "To" or "CC" fields) contained a formatting error — such as a trailing comma — the report would silently fail to send. Report setup now validates each email address in these fields at save time, blocking the save with a clear error message such as "CC email address list cannot end with a comma. Please remove the comma at the end."

- Applies to both the "To" and "CC" email address fields on report setup.
- Prevents reports from being saved with malformed email lists, so they no longer fail silently.

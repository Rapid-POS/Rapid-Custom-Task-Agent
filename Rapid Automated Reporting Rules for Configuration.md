# Rules for Configuring Rapid Automated Reporting  
Updated 11/10/2025  

---

To ensure Rapid Automated Reporting generates reports correctly, the following rules are enforced in the Rapid Automated Reporting setup screen:  

## Daily Rules  

- When **`Occurs`** is set to **Daily**, a value **must** be entered in **`Recurs every x day(s)`**.  
- The **`Recurs every x day(s)`** field can **only** be used when **`Occurs`** is set to **Daily**.  

## Weekly Rules  

- When **`Occurs`** is set to **Weekly**, at least one day of the week **must be selected** (e.g., Monday, Tuesday, etc.).  
- Day-of-week options (Sunday–Saturday) are **only valid** when **`Occurs`** is set to **Weekly**.

## Monthly Rules

- When **`Occurs`** is set to **Monthly**, both **`Recurs the x day`** (day of month) *and*  **`Of every x months`** (interval in months) must be specified.  
- The **`Recurs the x day`** and **`Of every x months`** fields can **only** be used when **`Occurs`** is set to **Monthly**.

## Send Time(s)

These rules govern the **time-of-day** options (e.g., **`Occurs once at`** vs **`Occurs every`**):  

- Exactly one style **must be chosen**:  
  - Either **`Occurs once at`** *or* **`Occurs every`** with an interval value  
  - Both cannot be left blank, and both cannot be filled in at the same time.  

- Reports **cannot** use the same **`Occurs once at`** time as another report.  
  - Configuring multiple reports to run at exactly the exact same time may consume excessive resources.  

- If **`Occurs every`** is selected, a valid interval type **must also be selected**, such as **Hour, Minute, or Second**.  

## Cross-Rule Consistency  

- Day-of-week options must **not** be used when the schedule is set to **Daily** or **Monthly**.  
- Monthly recurrence fields (**`Recurs the x day`** and **`Of every x months`**) must **not** be filled in when the schedule is **Daily** or **Weekly**.  

## Email Rules  

- All email addresses in the **To** (and related) fields must be in a **valid email format**.  
- Invalid addresses (missing `@`, domain, etc.) will be rejected.  

These validations are enforced to keep automated report schedules clean, predictable, and error-free.  

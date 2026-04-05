# APEX Debug Dashboard

A lightweight Oracle APEX application for querying and visualising 
`APEX_DEBUG_MESSAGES` — the built-in Oracle APEX debug log view.

Built and tested on Oracle APEX 24.2.

## What It Does

Most new Oracle APEX developers enable debug mode occasionally but never 
query the underlying data directly. This app surfaces that data in a 
structured, readable dashboard with four focused views:

**Page 1 — Debug Sessions**  
One row per page view, grouped by `PAGE_VIEW_ID`. Shows error count, 
duration, message count, and slowest operation per session at a glance.

**Page 2 — Session Detail**  
Full message trace for a selected session in chronological order. 
Messages are colour coded by level — errors in red, warnings in orange, 
info in blue, verbose in grey.

**Page 3 — Performance View**  
All operations across all sessions ranked by `EXECUTION_TIME`. 
Operations are classified by type (Session State, Plugin Load, 
Page Render, Commit, etc.) and colour coded. Slow operations 
above 100ms highlighted in orange, above 500ms in red.

**Page 4 — Session State Trace**  
Parses `Session State:` and `... id=, name=, type=, value=` message 
patterns to show a chronological trace of every session state read 
and write during a page load. Extracts item name, type, and value 
using `REGEXP_SUBSTR`.

## Technologies Used

- Oracle APEX 24.2
- Oracle Autonomous Database
- `APEX_DEBUG_MESSAGES` built-in view
- Interactive Reports with custom HTML expressions
- Page Load Dynamic Actions (JavaScript)
- `REGEXP_SUBSTR` for message parsing

## Prerequisites

- Oracle APEX 24.2 or later
- Debug mode must be enabled on target applications to generate data
- The installing user must have access to `APEX_DEBUG_MESSAGES`

## Installation

1. Log in to your Oracle APEX workspace
2. Go to **App Builder → Import**
3. Select `apex_debug_dashboard.sql`
4. Follow the import wizard — accept all defaults
5. Run the application
6. Enable debug mode on any APEX app (`?debug=YES`) to generate data
7. Return to the dashboard to view results



## Screenshots
<img width="1904" height="905" alt="image" src="https://github.com/user-attachments/assets/6363bb94-2ed4-444e-b654-95c7517d179c" />
<img width="1911" height="909" alt="image" src="https://github.com/user-attachments/assets/a0a681d1-2a18-48ff-ab8e-406c37d2be62" />


## License

MIT

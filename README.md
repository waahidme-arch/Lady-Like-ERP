# Lady Like ERP — Phase 1 (working starter)

A runnable local web app with: initial admin setup, secure password hashing, login, session handling, role-restricted branch and user creation, Bangla/English navigation, branch selector, dashboard KPI placeholders, user-specific customizable card order and visibility, and a **read-only illustrative** VAT preview.

## Requirements
- Node.js **20 or newer** and npm
- Windows, macOS, or Linux

## Installation
1. Extract the ZIP into a folder.
2. Open Terminal / PowerShell in that folder.
3. Run `npm install`.
4. Run `npm start`.
5. Open `http://localhost:3000` in Chrome.
6. On first run, create your Admin account and Main Branch. Use a unique strong password.

Data is stored in `data/erp.db` and sessions in `data/sessions.sqlite`. Keep backups of the `data/` directory **with the server stopped**. Do not delete it during updates.

## Included
- Initial admin registration (only available while no users exist)
- Password hashes using bcrypt
- Admin/manager/staff roles, admin-only branch/user management
- Branch selection (non-admin users restricted to their assigned branch)
- English/Bangla UI labels for dashboard/navigation
- Customize dashboard: hide/show/reorder 12 cards, saved per user
- SQLite starter database and session persistence
- VAT 15% inclusive preview (monthly totals, no submission yet)
- No invented sales data: empty transaction tables display zero and unavailable KPIs display dashes.

## Not yet included
Sales/POS, purchase entry, inventory, expenses, profit accounting, customer/supplier balances, month/year VAT submission/history, full Bangla translation, Excel/PDF exports, offline sync, deployment and production-grade multi-branch conflict resolution. These belong to later phases. The 15% VAT rate is a **planning assumption** subject to applicable Bangladesh tax rules.

## Important deployment notes
This is a **local development starter**, not production-ready ERP. Do not expose it to the public internet or store real business/financial data until security review, HTTPS, persistent session secret, CSRF protection, backups, audit and permission testing, accounting validations, migrations, and offline synchronization are implemented. For production, use PostgreSQL and a deployment-specific security configuration.

Set `SESSION_SECRET` to a long random string and use HTTPS before deployment. `NODE_ENV=production` enables secure session cookies (HTTPS required).

## Project structure
- `server.js`: Express API + SQLite tables
- `public/index.html`: responsive dashboard styles
- `public/app.js`: user interface and API calls
- `public/brand-reference.jpg`: brand color/logo reference image (not a cleaned transparent logo)

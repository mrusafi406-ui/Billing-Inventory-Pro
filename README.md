# Billing & Inventory Pro — starter v0.1

A clean new project foundation for an Android + web billing and inventory app. This is not a finished production app.

## Current starter capabilities
- Responsive Android-friendly web shell and navigation
- Dashboard summary based on recorded demo/cloud sales
- Sales entry with validation for quantity, rate, discount, paid, net total and due
- Browser-only demo storage when Firebase is not configured
- Firebase Auth sign-in integration and Firestore sales create/read integration when configured
- New package ID: `com.billinginventory.pro`

## Important safety notes
- The starter intentionally does not reuse the previous Firebase project.
- Create a new Firebase project and replace `src/firebase-config.js` values.
- Enable Email/Password Authentication and create authorized accounts in Firebase Console.
- Review and deploy `firestore.rules` only after completing role-based authorization. The provided rules are a restrictive bootstrap, not final production authorization.
- Never commit service-account keys, private keys, or user passwords.
- Product, stock, credit/debit, commission, targets, import, reporting, role provisioning, PDF and Bluetooth printing are not complete yet.

## Run locally
1. Install Node.js 20+.
2. Run `npm install`.
3. Configure Firebase if cloud login is needed.
4. Run `npm run dev`.

## Android build direction
1. `npm run build`
2. `npx cap add android` (only once)
3. `npx cap sync android`
4. Open `android/` in Android Studio or build with Gradle.

For GitHub Actions, use a workflow_dispatch build and configure release signing separately before distributing a release APK.

## Planned implementation sequence
1. Validate and import Products, Shops, Routes, Officers, Targets and DSR data from the supplied workbook.
2. Implement role-based authorization and audit logs.
3. Implement order/memo, product catalog, inventory ledger, stock receipt, damage and return.
4. Implement customer ledger, payments, commission and credit/debit.
5. Implement officer performance, target calculations and dashboard reports.
6. Test duplicate submissions, offline/retry behavior, concurrency, permissions, and financial calculations.

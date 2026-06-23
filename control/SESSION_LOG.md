# SESSION LOG — WenMar Digital / All Projects
*Append only. Most recent entry at top.*
*Format: ## YYYY-MM-DD — [Project(s)] — [Summary]*

---

## 2026-06-21 — AMBER Personal — Email notification popup ported from Business
- Ollama check: latest stable v0.30.10 (June 17). Holding at v0.30.4 — no change.
- Ran full project health check — all apps and deployed sites confirmed working.
- Bank statement analyser root URL 404 (no index.html) — not urgent, noted.
- Ported email notification warning popup from AMBER Business to AMBER Personal.
- Fixed nav bug — "Set up now" was pointing to 'settings' (does not exist in Personal), corrected to 'users'.
- Committed to AMBER-Personal repo (f155ff5).

**Next session priorities:**
- Email alert end-to-end test with real SMTP (both apps)
- Clean install full test before Lauren demo
- "Don't show this again" on Ollama version modal
- Add index.html to bank statement analyser repo (low priority)

---

## 2026-06-21 — ALL PROJECTS — Master control files created
- Ollama check: latest stable v0.30.8 (June 12). Holding at v0.30.4 — no change.
- Discussed encryption at rest for AMBER suite. Not legally required for Green tier. FileVault + local storage defensible. Revisit for Red tier during legal sign-off.
- Cleared old DocVault/Clinical era entries from manual memory (was full at 30 entries). Freed 16 slots.
- Fixed localStorage corruption bug in SNK (snk-fleet.html). Pushed to Game-Trackers repo.
- Created PROJECT_CONTROL.md and SESSION_LOG.md in AMBER-personal repo (personal project only — limitation identified).
- Identified gap: no master control file covering all projects. Mark expressed frustration with repeated context loss and workflow violations across sessions.
- **Created this master PROJECT_CONTROL.md and SESSION_LOG.md to cover ALL active projects.**
- These files to be placed in a central location accessible across all sessions.

**Next session priorities:**
- Email alert end-to-end test with real SMTP (AMBER Personal/Business)
- Clean install full test before Lauren demo
- "Don't show again" on Ollama version modal

---

## 2026-06-21 — SNK — Service sticker print function
- Added printable service sticker modal to snk-fleet.html (Brother QL-820NWB, 62mm roll).
- Fields: rego (auto-filled), service date, odometer, technician, work performed, next service date, next service odometer. Engine type toggle.
- Git push initially wiped 20 files from repo (local folder only had snk-fleet.html, not full clone). Reverted and re-pushed correctly.
- Deployed page blank after push — session ended. To be fixed next SNK session.

---

## Earlier sessions (summary)
- AMBER Personal and Business feature-complete for Green tier launch demo.
- 10 industry templates built in Business.
- Onboarding wizards, emergency access, Ollama version checker, Help & Guide, duplicate detection UI built in both apps.
- Parsing accuracy ~18/18 on GP Practice test docs.
- Landing page live. Repos renamed to AMBER-Personal and AMBER-Business.
- Pricing confirmed with Wendy: Basic $4.99 / Pro $19, no free tier.
- AMBER branding finalised (navy, amber/gold, vault door logo).
- OMS Wilton and DocVault Wilton deployed to London via TeamViewer.
- Bank statement analyser tools deployed.
- WenMar_Handover.docx produced as platform-agnostic context document.

## 2026-06-21 — CLOSING NOTE
- SNK: service sticker print function still has blank page issue. Client to test current HTML as-is before any permanent build is considered.
- WenMar Digital: all projects at standstill pending in-person meeting with Wendy this week.
- Master PROJECT_CONTROL.md and SESSION_LOG.md created and committed to wenmardigital/control/.

## 2026-06-23 — AMBER Care — Initial build
- Ollama check: latest stable v0.30.10 (June 17). Holding at v0.30.4 — llava:13b confirmed issue not resolved in 0.30.x release notes.
- Market gap research session — identified two new product opportunities: AMBER Care (NDIS/aged care worker credential wallet) and AMBER Club (community sports club admin tool).
- Produced three partner docs for Wendy: Tier Framework Brief, Market Opportunities Brief, Business Roadmap v5.
- Data protection position confirmed: WenMar stores nothing, liability sits with users. T&Cs are critical pre-launch task — 4 specific clauses required.
- GP Practice tier decision: legal case for moving to Green is strong, commercial case for caution is valid. Decision deferred to partner meeting.
- AMBER Care built from scratch as separate product (not folded into Personal):
  - Copied AMBER-personal to ~/Desktop/WenMar/AMBER-care
  - Removed git history, fresh init
  - package.json: name=amber-care, appId=com.wenmardigital.ambercare, productName=AMBER Care
  - main.js: DB renamed to amber-care.db, emergency index label updated
  - public/index.html: title updated to AMBER Care
  - src/utils.js: BUSINESS_CATEGORIES replaced with 7 care worker credential categories, DOC_FIELDS replaced with 19 care credential types, Ollama prompt replaced with care-specific rules
  - src/components/Sidebar.js: categories replaced, ICONS block restored after line-number shift, "Personal" → "Care", "Personal Vault" → "Credential Wallet"
  - src/components/LoginScreen.js: "AMBER Personal" → "AMBER Care", "Personal Vault" → "Credential Wallet", username colour fixed, "Add New Vault" → "Add New Wallet"
  - src/components/OnboardingWizard.js: subtitle and step 3 tiles updated to care worker credentials
  - src/components/SnapshotModal.js: AMBER Personal → AMBER Care
  - src/pages/Dashboard.js: "Vault Health" → "Wallet Health", empty state text updated
  - src/pages/UserManagement.js: "Wipe My Vault" → "Wipe My Wallet", "Delete My Vault" → "Delete My Wallet"
  - src/pages/Help.js: all AMBER Personal references updated
  - npm install run clean after copy
  - Initial commit: abbf1b0
- Outstanding for next AMBER Care session:
  - Clean repo of old Personal test docs, DocVault files, old control files
  - Create GitHub remote repo and push (Smitty412430/AMBER-Care)
  - Fix Personal Documents icon (showing 📇, should be ID card — 🪪 Unicode causing issues)
  - Test bulk upload with real care worker credential PDFs
  - Test Ollama parsing against NDIS Worker Screening Check, Police Check, First Aid cert
  - Snapshot PIN saving issue (existed in Personal too — investigate)
  - "Vault Health" → check if any other vault references remain in app
  - Consider care-specific Help & Guide content
  - Consider care-specific empty state icon (replace padlock)
- WenMar roadmap v5 produced — GP Practice tier decision and new products added
- WenMar financial tools section updated: Xero stays for ATO compliance only, internal tracker to be built by Mark for pre-revenue tracking

## 2026-06-23 — AMBER Care + Personal — PIN fix and repo cleanup
- Cleaned AMBER Care repo — removed old Personal test docs, DocVault files, old control files, build artifacts (commit a6a79a4)
- Fixed snapshot PIN regex bug in both AMBER Care and AMBER Personal:
  - Bug: /D/g only stripped letter "D" instead of all non-digits
  - Fix: /\D/g now correctly strips all non-digit characters
  - PIN was actually saving correctly — bug was in input filtering only
  - Care: also updated PIN section title to say "credential wallet snapshot" (commit 269e051)
  - Personal: regex fix only (commit 87d1ca5)
- AMBER Care still needs GitHub remote repo created and pushed
- Outstanding for next AMBER Care session: create GitHub repo Smitty412430/AMBER-Care, push, test Ollama parsing with real care worker credential PDFs

## 2026-06-23 — Wenmar-Demos — AMBER Care demo update
- Updated All Items popup to include Snapshot export explanation (commit 5bdfbba)
- Snapshot popup retained on dashboard stat card as secondary entry point

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

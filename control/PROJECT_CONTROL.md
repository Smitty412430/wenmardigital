# PROJECT CONTROL — WenMar Digital / All Active Projects
*Master source of truth. Read this at the start of every session before touching anything.*
*If this file conflicts with chat memory, THIS FILE WINS.*

---

## People

| Person | Role |
|--------|------|
| **Mark Schmidt** | Technical co-founder, WenMar Digital. All development via AI-assisted terminal workflow. Not a programmer. Based in Adelaide, caring for elderly father. |
| **Wendy Pearse** | Co-founder, GP practice manager. Domain knowledge, client relationships, sales. 50/50 partnership. |
| **Shane** | External contact, beta tester, HVAC contact. Currently away ~2 weeks from 2026-06-21. |
| **Lauren** | GP Practice demo contact. Wendy to schedule AMBER Business demo. |

---

## Active Projects

### 1. AMBER Personal
- **Local path:** `~/Desktop/WenMar/AMBER-personal`
- **Repo:** `github.com/Smitty412430/AMBER-Personal` (private)
- **DB:** `~/Library/Application Support/docvault-personal/docvault-business.db`
- **Stack:** Electron / React / SQLite / Ollama
- **Status:** Feature-complete for Green tier demo launch
- **What it is:** Personal document vault for individuals. Expiry tracking, bulk upload, AI parsing, emergency access, onboarding wizard, Help & Guide page, duplicate detection UI, Ollama version checker.

### 2. AMBER Business
- **Local path:** `~/Desktop/WenMar/AMBER-business`
- **Repo:** `github.com/Smitty412430/AMBER-Business` (private)
- **DB:** `~/Library/Application Support/docvault-business/docvault-business.db`
- **Stack:** Electron / React / SQLite / Ollama
- **Status:** Feature-complete for Green tier demo launch
- **What it is:** Compliance document management for businesses. 10 industry templates. Staff credentials, email alerts, onboarding wizard, Help & Guide page, Ollama version checker.

### 3. AMBER Personal Freemium (parked)
- **Local path:** `~/Desktop/WenMar/amber-personal-freemium`
- **Status:** Built but parked — pricing confirmed as paid-only (no free tier)
- **Notes:** 20 doc free tier, bulk upload and snapshot locked. Not current priority.

### 4. Landing Page
- **Local path:** `~/Desktop/WenMar/wenmardigital/index.html`
- **Live:** `smitty412430.github.io/wenmardigital`
- **Status:** Live. Password/login language pending Wendy sign-off (Mark prefers Option C).

### 5. DocVault Wilton (London client)
- **Stack:** Electron / React / SQLite
- **Theme:** Saudi green
- **Status:** Deployed to London via TeamViewer (Windows)
- **What it is:** Staff document/credentials manager for a London household client. NOT part of AMBER rebrand.
- **Notes:** `skipDedup` flag added to bulk upload. Claude upgraded to Sonnet for parsing.

### 6. OMS Wilton (London client)
- **DB:** `~/Library/Application Support/oms-wilton/oms-wilton.db`
- **Stack:** Electron / React / SQLite
- **Status:** Deployed to London via TeamViewer (Windows)
- **What it is:** Household expenditure and office management system. NOT part of AMBER rebrand.
- **Notes:** AI engine toggle (Claude/Ollama), Office Documents module, Saudi emblem in sidebar.

### 7. Sweep N Kleen (SNK)
- **File:** `smitty412430.github.io/Game-Trackers/snk-fleet.html`
- **Repo:** `github.com/Smitty412430/Game-Trackers` (public)
- **Local path:** `~/Desktop/Game-Trackers/snk-fleet.html`
- **Status:** Active. localStorage corruption bug fixed 2026-06-21.
- **What it is:** Standalone single-file HTML fleet maintenance log for a road sweeper fleet operator. Dark theme, red/black branding. Vehicle register, job sheets, CSV export, service status badges, service sticker print function (Brother QL-820NWB, 62mm roll).
- **NOT part of WenMar Digital.**

### 8. Bank Statement Analysers
- **Repo:** `github.com/Smitty412430/amber-statement-analyser`
- **Live:** `smitty412430.github.io/amber-statement-analyser`
- **What they are:** Four standalone HTML tools — generic personal, Shane's personalised ANZ version, AMBER Business version, Wilton Expense Analyser (UK).
- **Status:** Deployed. Shane's ANZ version has a parked "What If" mortgage insight feature — build when Shane returns.

### 9. Game Trackers
- **Live:** `smitty412430.github.io/Game-Trackers`
- **Repo:** `github.com/Smitty412430/Game-Trackers` (public)
- **Status:** Live. Six personalised pokie machines. Future PWA opportunity post-AMBER launch.

---

## Branding (AMBER Suite Only)

| Element | Value |
|---------|-------|
| Background | `#0a1628` (dark navy) |
| Accent | `#EF9F27` (amber/gold) |
| Logo | Vault door SVG, traffic light bolt dots, AMBER wordmark in amber, red/amber/green bar |
| Tagline | `DOCUMENT CONTROL` (spaced grey caps) |
| Personal logo | Circular vault door |
| Business logo | Square vault door |

---

## Industry Tiers (AMBER Business)

| Tier | Industries |
|------|------------|
| **Green — launch first** | Construction, Mining/Heavy Vehicle, Transport & Logistics, Hospitality, Civil & Bitumen, Real Estate, Labour Hire, Security, General Business |
| **Amber — after legal review** | Childcare, Education |
| **Red — formal legal advice required** | GP Practice, Healthcare, Aged Care |

---

## Pricing (Locked In)
- **AMBER Personal:** Basic ~$4.99 / Pro ~$19 AUD one-off. No free tier. No trial. Features-only differentiation. No document limit on either tier.
- **Multi-industry licences:** Phase 2 only. Package framing: Solo, Business 1–2, Business 2–4. No discount language.

---

## Ollama Configuration
- **Pinned at v0.30.4 — DO NOT UPGRADE.** llama3.2-vision broken in newer versions.
- Text/bulk model: `llama3:latest`
- Image model: `llava:13b`
- Stability env vars in `~/.zshrc`: `OLLAMA_MAX_LOADED_MODELS=1` and `OLLAMA_NUM_PARALLEL=1`
- Restart command: `pkill -f ollama && sleep 2 && ollama serve &`
- Version Gist: `https://gist.github.com/Smitty412430/41c07724a7764e855d4b388d57c9341b`
- **Latest stable as of 2026-06-23: v0.30.10 — holding at v0.30.4, no change.**

---

## Absolute Dev Rules
1. **Never bluff.** If unsure, say so. No exceptions.
2. **All file edits via Node.js patch scripts** saved to `/tmp/` and run with `node`. Never `node -e` inline. Never Python for file edits.
3. **Always `grep -n` or `sed -n` before editing.** Always verify after patching.
4. **One command at a time.** Wait for Mark to paste terminal output before providing the next step. Never pre-emptively give the next command.
5. `npm run dev` — not `npm start`.
6. **Commit to GitHub after each completed feature.**
7. Windows builds: `npm run build && npx electron-builder --win`
8. No `!` characters inside patch script string content.
9. **Check Ollama releases at start of every WenMar dev session** and report version vs v0.30.4.
10. **Read PROJECT_CONTROL.md and SESSION_LOG.md at the start of every session** before doing anything else. These files win over chat memory.
11. **Warn before context limit** and produce carry-over prompt proactively — before the chat fills, not after.
12. **Never suggest browser console fixes.** Always patch script workflow.
13. **Before any git push involving a local folder,** confirm the local folder is a full clone of the repo — not just a single file — to avoid wiping other repo contents.

---

## Wendy Chat List (Priority Order)
1. Pricing — AGREED: Basic $4.99, Pro $19, no free tier, no trial, features-only
2. Landing page password/login language — Option C pending sign-off
3. Full critique list — expected, not yet received
4. GP Practice template sign-off — her domain
5. Lauren demo (AMBER Business, GP Practice template) — Wendy to schedule
6. "Scan Confirm Save" tagline — discuss placement
7. Help page highlight — leave on permanently or fade? Wendy's call
8. Multi-industry licences Phase 2 — package framing only
9. AMBER OPS — future standalone product concept, not current
10. App Store / pre-commercial checklist — park until 3 weeks before launch

---

## Current Sprint Status

### Next dev items (unblocked):
- Email alert end-to-end test with real SMTP
- Clean install full test before Lauren demo
- "Don't show again" option on Ollama version modal

### Blocked on Wendy:
- Full critique list
- GP Practice template sign-off
- Lauren demo scheduling
- "Scan Confirm Save" tagline placement decision
- Help page highlight permanence decision
- Landing page password language (Option C)

### Parked (waiting on Shane):
- "What If" mortgage insight panel for Shane's ANZ statement analyser

---

## Session Log Location
`SESSION_LOG.md` lives alongside this file. Check it for what was done last session.

---

*Last updated: 2026-06-21*

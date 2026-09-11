# IFT UNILORIN · Huawei ICT Competition 2026–2027 Practice Team Command Center

A single-file, offline-friendly dashboard for the IFT UNILORIN Huawei ICT Competition Practice Team. Built for the 11 September 2026 pre-school runway and the school-term that follows.

## What this is

`index.html` is a self-contained web app — HTML, CSS and JavaScript in one file, no build step, no backend, no login. Open it and everything works: a 14-quest roadmap across 9 preparation phases, Network/Cloud/Computing/Cybersecurity track pages, a 5-level lab progression tracker, 5 mock exams with a readiness score, a Mistake Bank, a curated resource library, a Competition Radar with honestly-labelled confirmed/unconfirmed facts, team member scoring, and a Team Lead Console.

It is **not** the official Huawei team-selection tool, and it doesn't replace the real Huawei ICT Competition Learning Space — it's the internal layer that turns that material into a weekly plan your team will actually follow.

## How to open it

Double-click `index.html`, or drag it into any modern browser (Chrome, Edge, Firefox, Safari — desktop or Android). No internet connection is required except to follow external resource links. It works fully offline once loaded.

To share it with the team, either:
- send the file directly (e.g. via WhatsApp/Drive) and have each person open their own local copy, or
- upload it to any static host (GitHub Pages, Netlify) if you want one shared URL — note that in that case, everyone's *progress data* still stays local to their own browser (see below).

## How data storage works (important)

All progress — quest statuses, evidence notes, team scores, mock results, mistakes, console notes — is saved in your browser's **localStorage**, tied to that specific browser on that specific device. That means:

- Data is **not** shared automatically between team members or between devices.
- Clearing your browser's site data/cache, or opening the file in a different browser, will lose your saved progress.
- Nothing is sent anywhere. There is no server, no analytics, no account.

**This is why the Settings page has Export/Import.** Recommended pattern:
1. One person (e.g. the Team Lead) keeps the "master" copy of the file and its data.
2. After each team session, go to **Settings → Export backup (.json)** and save the file somewhere safe (Drive, USB, email to yourself).
3. If you switch devices, or someone else needs to pick up the file, use **Settings → Import backup** to load that `.json` back in.
4. Do this weekly at minimum — more often before big data-entry sessions (e.g. after everyone completes the baseline assessment).

## How to edit team members

Go to **Team**. Each member is a card with an editable name, track dropdown, and baseline/current score fields. Scroll down and click **+ Add member** to add a new person, or **Remove** on a card to delete one. All 7 baseline categories (Networking, Computing/Linux, Cloud/AI, Cybersecurity, Problem solving, Practical troubleshooting, Learning discipline) are weighted automatically — see `DATA.md` for the weights — and the Team page shows the team's average and its current strongest/weakest area.

The dashboard ships with 10 placeholder members ("Member 1" … "Member 10") — rename them to your actual team on first use.

## How to update competition dates

Go to **Settings**:
- **School resumption date** drives the "Days to school resumption" counter on the Command Center and the Phase 0→1 transition logic.
- **Competition info last verified** is a self-reported date so the team knows how fresh the Competition Radar data is.

Go to **Competition Radar** for competition-specific fields:
- A **Last verified by this team** date and a free-text **Nigeria / UNILORIN status note** — update this the moment you get confirmed information from Huawei, your ICT Academy coordinator, or the official Learning Space.

No competition date in this dashboard was invented. Where Nigeria-specific 2026–2027 dates are not publicly confirmed, the Radar says so explicitly rather than guessing — check the official links there periodically.

## How to add resources

Resources currently live in the JavaScript data (`seedResources()` near the top of the `<script>` block in `index.html`), not in a settings UI — this keeps the file simple and avoids a half-built resource editor. To add one:

1. Open `index.html` in a text editor.
2. Find `function seedResources(){` and add a new object to the array, following the existing pattern:
   ```js
   {t:'Resource title', p:'Provider', type:'Network', track:'network', diff:'Foundation', why:'Why it matters', url:'https://example.com'}
   ```
   - `type` should be one of: Official Huawei, Network, Cloud, Computing, Cybersecurity, Linux, YouTube, Past Questions, Labs, Reference (these drive the filter pills).
   - `track` should be one of: network, cloud, computing, security, cross.
3. Save the file and reload it in the browser. See `DATA.md` for the full current list and more detail.

If your team is comfortable with browser dev tools instead, you can also just inspect and copy an existing resource card's pattern — no build tooling is needed.

## How to back up progress

Covered above under "How data storage works" — use **Settings → Export backup (.json)** regularly, and **Import backup** to restore. The exported file is human-readable JSON if you ever need to inspect or manually patch it.

## Limitations

- **Single-device data.** No sync between team members' browsers — this is a deliberate no-backend, no-login design choice per the brief. Use exports to consolidate.
- **Manual scoring.** Baseline, mock, and lab scores are entered by hand — there's no auto-grading.
- **Resource list is curated, not exhaustive**, and edited by hand in the source file (see above).
- **YouTube links point to search queries, not specific videos**, deliberately — specific videos go stale or get removed; search links stay useful.
- **Competition facts reflect what could be verified as of 11 September 2026.** Huawei's official Learning Space and Talent Portal remain the source of truth — this dashboard should never be treated as more current than those.
- No print/PDF export is built in; use your browser's print function if needed.

## How to verify Huawei announcements yourself

Don't take this dashboard's word for anything date- or eligibility-related. Check directly:

- **Huawei Talent Portal** (account & registration): https://e.huawei.com/en/talent/portal/#/
- **Huawei ICT Competition Learning Space**: https://talent.shixizhi.huawei.com/center/privateCenter.htm
- **Huawei ICT Academy**: https://e.huawei.com/en/talent/ict-academy
- **Huawei ICT Competition — official page**: https://e.huawei.com/en/talent/ict-academy/ict-competition

If your university has a designated Huawei ICT Academy coordinator or lecturer contact, they are usually the fastest route to Nigeria-specific confirmation — official portals sometimes lag behind what coordinators already know.

---

*This is an internal University of Ilorin practice-team tool, built to prepare a talent pool for the Huawei ICT Competition 2026–2027. It is not an official Huawei product and carries no affiliation beyond using Huawei's publicly published competition structure as its curriculum spine.*

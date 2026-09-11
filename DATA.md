# DATA.md — Curriculum & Resource Configuration Reference

Human-readable mirror of the data seeded inside `index.html`. Edit the corresponding JavaScript objects in the `<script>` block (search for the function names below) if you want to change any of this — this file is documentation, not the live source.

---

## 1. Preparation phases (`PHASES`)

| # | Phase | Timing | Focus |
|---|-------|--------|-------|
| 0 | Orientation & Setup | Week 1 | Accounts, competition structure, baseline assessment, study environment |
| 1 | Networking Foundations | Weeks 1–3 | OSI/TCP-IP, IPv4/IPv6, subnetting, routing/switching basics, VLANs, WLAN |
| 2 | Huawei Network Track | Weeks 3–6 | VRP CLI, VLAN/trunk config, static & dynamic routing, OSPF, ACL, NAT, DHCP, WLAN, troubleshooting |
| 3 | Cloud Fundamentals | Weeks 5–8 | IaaS/PaaS/SaaS, virtualization, containers, cloud security, big data, Huawei Cloud |
| 4 | Computing Foundations | Weeks 7–10 | Linux CLI, SQL, openEuler, openGauss, Kunpeng |
| 5 | Cybersecurity for Competitors | Woven through 1–4 | CIA triad, common attacks, ACLs, segmentation — competition-relevant only |
| 6 | Huawei Exam Intelligence | Week 8 onward | Past-question analysis, timed quizzes, Mistake Bank |
| 7 | Practical Lab Training | Week 9 onward | 5-level lab progression, timed scenarios |
| 8 | Mock Competition | Week 10 onward | 5 mock exams, readiness tracking |

Target commitment: **60–120 min/day, 5–6 days/week** pre-school (Phase 0–1 window); **5–8 focused hrs/week** once School Mode is on.

---

## 2. Quests (`seedQuests()`)

| Code | Title | Phase | Track | Difficulty | Default status |
|---|---|---|---|---|---|
| Q01 | Decode the Competition | Phase 0 | cross | Foundation | Available |
| Q02 | Think Like a Network | Phase 1 | network | Foundation | Available |
| Q03 | Subnetting Under Fire | Phase 1 | network | Intermediate | Available |
| Q04 | Build the LAN | Phase 2 | network | Intermediate | Locked |
| Q05 | Route the World | Phase 2 | network | Intermediate | Locked |
| Q06 | Secure the Network | Phase 5 | security | Intermediate | Locked |
| Q07 | Huawei VRP | Phase 2 | network | Intermediate | Locked |
| Q08 | Cloud Native | Phase 3 | cloud | Intermediate | Locked |
| Q09 | Compute | Phase 4 | computing | Intermediate | Locked |
| Q10 | Break It | Phase 7 | network | Competition | Locked |
| Q11 | Speed Run | Phase 6 | cross | Competition | Locked |
| Q12 | Mock National | Phase 8 | cross | Competition | Locked |
| Q13 | Lab Boss | Phase 7 | network | Advanced | Locked |
| Q14 | Competition Mode | Phase 8 | cross | Advanced | Locked |

Each quest object carries: objective, estimated time, prerequisites, resource links, practical task, deliverable, 2–3 self-check questions, and an editable `evidence` field (filled in by the student inside the app, saved to localStorage).

Q01–Q03 are unlocked by default so the first four weeks are immediately actionable. Unlock the rest manually (open the quest → change Status) as your team progresses — the app does not auto-lock/unlock based on prerequisites, by design, so a coach can adapt the order.

---

## 3. Baseline scoring weights

Used in the Team page and Command Center "team baseline average":

| Category | Weight |
|---|---|
| Networking | 25% |
| Computing/Linux | 15% |
| Cloud/AI | 15% |
| Cybersecurity | 10% |
| Problem solving | 15% |
| Practical troubleshooting | 10% |
| Learning discipline | 10% |

A member's weighted average only counts categories that have been scored — an all-blank member is excluded from the team average until at least one field is filled in.

---

## 4. Lab levels (`state.labs`)

1. Basic configuration
2. Multi-device configuration
3. Troubleshooting
4. Timed scenario
5. Competition simulation

Each level has an editable status (Locked/Available/In Progress/Completed/Needs Review) and a free-text notes field.

---

## 5. Mock exams (`state.mocks`)

Mock 1 (Foundation) → Mock 2 (Intermediate) → Mock 3 (National-style) → Mock 4 (Advanced) → Mock 5 (Full competition simulation). Each has: score %, time, accuracy %, unanswered count, and weak topics. **Readiness %** shown on the Mock Exams page and Command Center is the average of all entered mock scores.

---

## 6. Resource library (`seedResources()`)

23 seed resources. Categories used for the filter pills: Official Huawei, Network, Cloud, Computing, Cybersecurity, Linux, YouTube, Past Questions, Labs, Reference.

**Official Huawei sources included:**
- Huawei ICT Competition — official page: `https://e.huawei.com/en/talent/ict-academy/ict-competition`
- Huawei ICT Competition Learning Space: `https://talent.shixizhi.huawei.com/center/privateCenter.htm`
- Huawei Talent Portal: `https://e.huawei.com/en/talent/portal/#/`
- Huawei ICT Academy: `https://e.huawei.com/en/talent/ict-academy`
- Huawei Talent (home): `https://e.huawei.com/en/talent/`
- Huawei.com: `https://www.huawei.com/`
- Huawei Cloud: `https://www.huaweicloud.com/intl/en-us/`
- Huawei Cloud documentation: `https://support.huaweicloud.com/intl/en-us/`
- Kunpeng: `https://www.hikunpeng.com/en`

**Huawei-backed open-source projects:**
- openEuler: `https://www.openeuler.org/en/`
- openGauss: `https://opengauss.org/en/`

**Historical reference (2025–2026 cycle, clearly labelled — not current-cycle fact):**
- 10th Huawei ICT Competition Global Final recap (Huawei Newsroom, June 2026): `https://www.huawei.com/en/news/2026/6/ict-competition-global`
- Huawei ICT Competition 2025–2026 Global Final minisite: `https://www.huawei.com/minisite/ict-competition-2025-2026-global/en/index.html`

**YouTube resources are search-query links, not specific videos**, to avoid linking to content that goes stale or gets taken down. Topics covered: subnetting drills, OSI model, Huawei VRP CLI basics, OSPF fundamentals, VLAN configuration, ACL basics, eNSP tutorials, network troubleshooting, and a general "Huawei ICT Competition 2026 2027" query for recent public commentary.

**Reference (non-Huawei, for context):**
- Wikipedia — Huawei ICT Competition: `https://en.wikipedia.org/wiki/Huawei_ICT_Competition`

To add a resource, see the "How to add resources" section of `README.md`.

---

## 7. Weekly cadence template (`state.cadence`)

| Day | Default focus |
|---|---|
| Monday | Concept learning |
| Tuesday | Concept + quiz |
| Wednesday | Lab |
| Thursday | Revision |
| Friday | Light study / video / Huawei ecosystem update |
| Saturday | Deep technical session / mock |
| Sunday | Rest + weekly review |

Fully editable in-app (Roadmap page) — the table above is just the shipped default.

---

## 8. Competition facts — verification status (as of 11 September 2026)

| Fact | Status | Source |
|---|---|---|
| 2026–2027 cycle is live | **Confirmed** | Huawei ICT Competition 2025–2026 Global Final minisite banner: "Huawei ICT Competition 2026-2027 is now in full swing" |
| Practice tracks are Network / Cloud / Computing (+ Ascend AI, China-only) | **Confirmed** | Huawei official competition material, multiple national Huawei ICT Academy announcements |
| Progression is National Preliminary → National Final → Regional Final → Global Final | **Confirmed** | Huawei ICT Competition manual/brochure |
| 10th edition Global Final was held in Shenzhen, 9 June 2026 | **Confirmed (historical — 2025–2026 cycle)** | Huawei Newsroom, 9 June 2026 |
| Nigeria participated and won awards in 2025–2026 | **Confirmed (historical)** | Huawei Newsroom; Technology Times (Nigeria), 18 June 2026 |
| University of Ilorin's participation/registration status for 2026–2027 | **Unconfirmed** | Not found in any public source as of last verification |
| Nigeria-specific 2026–2027 registration dates | **Unconfirmed** | Not found in any public source as of last verification |

Update this table (and the in-app Competition Radar) the moment your team gets confirmed information — don't let the dashboard's copy go stale.

# Amra Pashe — MVP Planning Document (Shareable)
**Version:** v0.1 (from team call notes)  
**Date:** 2026-01-04  
**Scope:** Dhaka pilot, medical-focused urgent help network

---

## 1) Summary
**Working name:** Amra Pashe  
**One-liner (refined):** A trusted alert network that connects people in Bangladesh to nearby volunteers for urgent help.  

**6-month “win”:**
- A working MVP (web + mobile-friendly), ops/admin workflows ready
- Non-tech groundwork ready (partners + verification process)
- A small group of credible “verified publishers” actively using it

**Product approach:** Do one thing extremely well first (medical-focused urgent help), then expand.

---

## 2) Problem & Focus (Decisions)
**Primary problem we solve first:**  
1) **Finding donors / helpers fast (A)**  
Then: 2) Discovery/coverage (C) → 3) Coordination (D) → 4) Trust/verification improvements (B)

**Why existing solutions fail today (Bangladesh reality):**
- Mostly scattered Facebook/WhatsApp/group chats → fragmented, noisy, hard to trust, hard to target nearby helpers.

**Unit of value (North Star concept):**
- **End-to-end fulfilled case:** verified alert created → delivered to nearby people → responders engage → request fulfilled.

---

## 3) MVP Use Cases (Decisions)
### 3.1 MVP Categories (Recommended for “one thing 100%”)
✅ **MVP categories:**
- **Blood donation requests**
- **Medical supplies requests** (medical-only supplies)

🚫 **Phase 2 (recommended):**
- Missing persons (high safety + legal + moderation complexity; needs separate design)

> Note: Team initially listed Missing Persons too. Recommend keeping it Phase 2 to keep MVP safe and shippable.

### 3.2 Key MVP Promise
- Regular users can sign up quickly and receive relevant nearby alerts.
- Only **verified** people/orgs can create/publish alerts.

---

## 4) Target Users & Personas (Decisions)
### Persona A — General Public (Responders)
- **Role:** anyone willing to donate/help
- **Location:** Dhaka (MVP)
- **Device/Internet:** must work on low-end Android + slow/unstable internet
- **Motivation:** community-driven help; recent events highlight need for unified system
- **Concerns:** privacy, scams, harassment

### Persona B — Verified Individuals / Verified Publishers
- **Role:** trusted people who can publish alerts (doctors, hospital staff, NGO reps, blood group admins, community leaders)
- **Motivation:** coordinate help fast and reduce chaos of social media posts
- **Concerns:** urgency, reliability, preventing spam, safety

---

## 5) Roles, Permissions & Trust (RBAC) (Decisions)
### Roles
1) **Unverified user**
   - Can browse alerts (as allowed), respond, join case chat after intent
2) **Verified user (identity-verified responder)**
   - Same, but has trust badge (helps beneficiary decide)
3) **Verified Publisher — Individual**
   - Can create/publish/edit alerts; mark fulfilled
4) **Verified Publisher — Organization** (optional in MVP or early Phase 2)
   - Same, may later support multiple staff accounts
5) **Admin / Moderator (internal)**
   - Verify/revoke publishers, remove alerts, review reports, audit logs

### Verified Publisher Verification (Decision)
**Verification methods (combined):**
- Partner/org approval (when possible)
- Manual internal admin review
- ID check + photos
- In-person if needed (not required for MVP)

**Verification validity:** 2 years, renewal required.

**Security requirements (Decision):**
- 2FA for verified publishers
- Device binding
- Strong password
- Admin approval for new devices

**Revocation (Decision):**
- Admin panel: revoke immediately; publish disabled; audit log kept.

---

## 6) Signup & Identity (Decisions)
### Regular users
- **Minimum signup:** phone number + basic details
- **Email:** required to add; email verification optional for trust
- **Phone OTP:** recommended; allow limited access without OTP but mark user as unverified
- **Responder identity verification:** not required to respond, but improves trust

**Important policy stance (Decision):**
- Beneficiary/verified publisher must do final identity validation (ID matching in person).  
- We must clearly state this in **Terms/Privacy** (“we connect people; do your due diligence”).

---

## 7) Alerts: Data Model & Fields (MVP-ready)
### 7.1 Blood Donation Alert (MVP)
**Mandatory fields**
- Blood group
- Units needed
- Hospital/clinic name
- Area (thana/ward)
- Needed-by time
- Contact method (call/chat) revealed only after “I can help”

**Optional fields**
- Exact address (revealed after intent)
- Structured “notes” (dropdowns only; no free text)
- Proof photo (restricted visibility; see Open Questions)

### 7.2 Medical Supplies Alert (MVP)
**Mandatory fields**
- Supply type (catalog dropdown)
- Quantity
- Hospital/clinic name
- Area (thana/ward)
- Needed-by time

**Optional**
- Proof photo (restricted visibility)

### 7.3 Free Text (Decision)
- **No free-text in MVP** (reduces abuse/misinformation risk)
- Use structured fields + controlled dropdowns

### 7.4 Photos / Documents (Decision)
- Only **verified publishers** can upload proof photos to support requests.
- Storage of medical documents: **No** (MVP). Only minimal proof images if needed.

---

## 8) Alert Lifecycle & Rules (Decisions)
### Lifecycle
Draft → Published → Updated → Fulfilled → Expired → Removed

### Publishing
- **No approval required** before publishing once publisher is verified.

### Expiry
- Default: **6 hours**
- Editable: up to **7 days max**

### Editing
- Allowed after publish
- **Edit history visible** (transparency)

### Fulfillment
- Marked by **publisher** + optionally confirmed by admin
- Require both sides to indicate who helped (donor + beneficiary confirmation)

### Duplicates
- Allowed, but we aim to keep publisher accounts limited per hospital/team.

---

## 9) Location & Privacy Model (Decisions + Implementation Guidance)
### “Nearby” definition (Team intent)
- “Nearby” ~ **20 minutes walking** and/or **same thana**

### Location input
- Prefer GPS if user allows
- Fallback: user-entered address at signup (no apartment number; only building/street/area)

### What is shown publicly on alerts (Decision)
- Request details + **coarse area**
- Verified publisher identity
- Clickable publisher profile with prior requests history

### Recommendation (to reduce stalking/harassment)
- Public feed shows **coarse location**
- Exact address + phone number shown **only after “I can help”**

---

## 10) Notifications & Channels (Decisions + Risks)
### Channels (Team preference)
- Push + WhatsApp share + **SMS priority**

### Trigger rules (Decision)
- Notify users within nearby range.

### Frequency caps & quiet hours (Team said “none”)
- Team stated:
  - No caps
  - No quiet hours
- **Risk:** spam/fatigue + abuse + SMS cost explosion

**Recommended minimal guardrails (strongly suggested even for MVP):**
- Cap active alerts per publisher per hour (e.g., 3–5)
- Per-user SMS cap/day (configurable)
- User preference: “Mute SMS at night” (default ON for non-critical updates)

> If you keep “no limits,” define a budget + operational plan immediately.

---

## 11) Response Flow (Decisions)
### Respond actions
- User taps **“I can help”**
- Only then:
  - See requester contact details
  - Join a case chat (shared chat where new helpers can be added)
- Beneficiary can remove people from chat.

### Outcome tracking (Decision)
Track:
- Fulfilled/unfulfilled
- # responders
- Time to first response
- Which donor/helper fulfilled the request (publisher + donor confirmation)

---

## 12) Abuse, Safety & Moderation (Partially defined)
### Top risks (Team confirmed)
- Fake alerts to scam money
- Harassment/stalking via location
- Doxxing phone numbers
- Political misuse/misinformation
- Spam floods
- Impersonation of hospitals/officials

### Enforcement ladder (Decision)
Warn → Restrict → Ban (thresholds TBD)

### Life-threatening situations (Decision)
- Treat as life-threatening and do as much as possible
- Still show disclaimer: “Not emergency services”

### Logging for investigations (Needs tightening)
Team said “everything as needed.”  
**Recommendation:** define exact logs to avoid excessive PII:
- user ID, role, verification status, timestamps, coarse geo, alert changes, reports, moderation actions, device/account security events.

---

## 13) Operations (MVP reality)
### Who runs verification & moderation?
- For now: **internal team**
- Tools needed:
  - **RBAC admin panel**
  - verify/revoke users
  - remove alerts
  - view reports
  - audit logs

### Escalation
- Contact partner org/hospital admin as needed.

---

## 14) Metrics (minimal for MVP)
Team requested minimal metrics for MVP, but agreed on:
- **% of alerts fulfilled**
- **Median time to first responder**
- **# of verified alerts published**

---

## 15) Platforms & Tech (Decisions)
### Platform
- Web app first, mobile-friendly
- Use **Ionic** to wrap into mobile apps as needed

### Team skills
- Strong in React + Node

### Maps
- Google Maps (iframes OK to start)

### Push notifications provider
- TBD (Firebase likely)

### Performance requirement
- Should work on slow connections (2G/3G) and older Android devices.

---

# 16) MVP “Must Have” Features (Max 6)
1) **Phone-first signup + profile**
   - blood group, coarse area, optional email verification
2) **Verified Publisher onboarding + verification**
   - manual review + partner approvals + ID/photos
3) **Structured alert creation**
   - blood + medical supplies only; no free text
4) **Alert targeting + delivery**
   - nearby matching + SMS sending + basic delivery tracking
5) **Respond flow + case chat**
   - “I can help” → contact reveal → join chat → outcome tracking
6) **RBAC Admin Panel**
   - verification, revoke, moderation, audit logs

---

# 17) Nice Later (Backlog Recommendations)
- Missing persons module (Phase 2) with specialized safety design
- Push notifications via native wrapper + notification inbox
- Smarter matching: blood group, availability, donor eligibility timing, reliability score
- Reputation system (publisher/responder)
- Map-based feed + routing
- Partner org dashboard + multi-staff accounts
- Disaster mode with strict controls
- Donation/funding/CSR options (if needed later)
- Advanced localization (Bangla-first, transliteration search)

---

# 18) Open Questions (Need answers to finalize PRD + architecture)
1) **SMS cost model**
   - Who pays? Budget/month? Max SMS/day/user?
2) **Definition of “nearby”**
   - Choose one primary: same thana / radius km / “20-min walking” via maps API
3) **Chat approach for MVP**
   - In-app chat vs WhatsApp deep link vs hybrid?
4) **Proof photo visibility**
   - Admin only? Admin + verified responders? Anyone who taps “I can help”?
5) **No-limits notification stance**
   - Keep “no limits” OR adopt minimal caps to prevent abuse/cost blowups?
6) **Organization accounts in MVP**
   - Needed now or Phase 2?

---

# 19) Next Steps (Suggested execution order)
### Step 1 — Lock MVP scope (1 session)
- Confirm: “Blood + medical supplies only” (Missing persons = Phase 2)
- Confirm: exact “nearby” definition
- Confirm: SMS budget + caps

### Step 2 — Produce PRD + Wireframes
- PRD draft (requirements + acceptance criteria)
- Wireframes for:
  - signup
  - alert create (verified)
  - feed + alert detail
  - “I can help” + contact reveal
  - case chat
  - admin panel basics

### Step 3 — Architecture & Data model
- Define entities: User, VerificationProfile, Alert, AlertUpdate, Response, ChatThread, Report, AuditLog
- Define APIs + permissions matrix
- Define notification fanout approach (especially SMS)

### Step 4 — Ops runbook
- Verification checklist + renewal policy
- Moderation queue + SLAs + enforcement thresholds
- Incident response process

---

## Appendix A — Partner Candidates for Dhaka Pilot (starting list)
- BADHAN (voluntary blood donors)
- Sandhani (medical students’ donation network)
- Bangladesh Red Crescent blood services
- Major Dhaka hospitals’ blood banks (select 3–5)

(Team to finalize shortlist of 3–10.)

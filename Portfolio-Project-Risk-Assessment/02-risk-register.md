# 02 — Risk Register (assessed and treated)

Ten risks from the register extract, assessed on the 5×5 scales in [01-methodology.md](01-methodology.md). Each entry: description → **business impact** → scores → treatment decision → refined controls → target residual band.

---

## R1 — Unprotected cloud backup data (AWS) · **Critical (20)** · I5 × L4 · Treat: Mitigate
Server backup data in AWS is not configured with immutability/locking. An attacker who compromises the AWS account could alter or delete backups, defeating restoration.
**Business impact:** if backups are destroyed during a ransomware event, Nordvale loses its recovery path — potentially days of order data and its ability to restore operations, directly hitting revenue, customer trust and contractual SLAs.
**Controls (priority order):**
1. Enable backup immutability / object lock and MFA-delete on backup storage *(largest single risk reduction)*
2. Least-privilege, role-based access to backup infrastructure; time-bound elevated access
3. Encrypt backups at rest; separate backup account/blast radius from production
4. Alerting on backup deletion/modification attempts
5. Periodic restoration testing — a backup is only real once it has been restored
**Target residual:** Minor (I5 × L1 = 5–10)

## R2 — Outdated endpoint security software on ~60% of corporate devices · **Severe (16)** · I4 × L4 · Treat: Mitigate
A majority of devices run an outdated secure web gateway agent, weakening threat detection and exposing known vulnerabilities.
**Business impact:** the endpoint estate is the front door for ransomware and credential theft; degraded protection across 60% of devices materially raises breach likelihood and could interrupt trading operations.
**Controls:** enforce automatic agent updates; monthly patch-compliance policy with dashboard reporting of non-compliant devices; conditional access blocking non-compliant devices from corporate resources; user communications on why updates matter.
**Target residual:** Minor (I4 × L2 = 8)

## R3 — Phishing simulation failures (French market, 10% credential entry) · **Significant (12)** · I3 × L4 · Treat: Mitigate
10% of employees in one market entered credentials on a simulated phishing page.
**Business impact:** a 10% credential-compromise rate makes account takeover *likely* within the year; if any of those accounts carry privileged or finance access, the consequence escalates to fraud, data exposure or lateral movement.
**Note on scoring:** originally scored Minor (9); rescored to Significant (I3 × L4 = 12) on review — with observed enabling conditions the likelihood is 4, and privileged-account escalation keeps the impact at 3+. See [08-lessons-learned.md](08-lessons-learned.md).
**Controls:** MFA everywhere (limits what a stolen password buys); targeted refresher training + continued simulations with trend tracking; email filtering hardening; SPF/DKIM/DMARC enforcement; conditional-access rules for risky sign-ins.
**Target residual:** Minor (I3 × L2 = 6)

## R4 — Shared vendor-portal accounts in the Sales team · **Significant (12)** · I4 × L3 · Treat: Mitigate
Sales staff share a single login per vendor portal.
**Business impact:** shared credentials destroy accountability — no audit trail per person, no revocation on leavers, and one leaked password exposes every vendor relationship. This is an **identity risk**: audit failures, insider misuse without attribution, and breach of vendor contract terms.
**Controls:** individual named accounts per user (raise with vendors where portals don't support it); MFA on all portal access; joiner-mover-leaver process so access is revoked promptly; periodic access reviews; credential vaulting where individual accounts are genuinely impossible, with per-use checkout logging.
**Target residual:** Minor (I4 × L2 = 8)

## R5 — Insecure session cookie handling on SaaS platform · **Significant (12)** · I3 × L4 · Treat: Mitigate
Session cookies lack Secure/HttpOnly flags and encryption.
**Business impact:** session hijacking lets an attacker impersonate logged-in users without ever stealing a password — exposing customer data and enabling fraudulent orders on a revenue-generating platform.
**Controls:** set Secure + HttpOnly (and SameSite) flags; enforce HTTPS end-to-end; short session expiry and re-authentication for sensitive actions; MFA so a hijacked session has limited blast radius.
**Target residual:** Insignificant–Minor (I3 × L1–2)

## R6 — Government-related data in a public collaboration channel · **Critical (20)** · I5 × L4 · Treat: Mitigate (immediate)
Government-related data was stored in a publicly accessible SharePoint channel.
**Business impact:** exposure of government-related data threatens contract termination, debarment from future government work, regulatory action and severe reputational damage — plausibly the single most expensive event on this register.
**Controls (priority order):**
1. Immediate: restrict the channel, move data to a private, access-controlled location, and assess exposure window (who accessed what, when)
2. Sensitivity labelling + DLP policies preventing labelled data in public locations
3. Access logging and monitoring for the new location
4. Targeted training for teams handling government-related data
5. Recurring automated scans for sensitive data in public channels
**Target residual:** Minor (I5 × L1 = 5–10)

## R7 — Unvetted third-party hosting for subsidiary e-commerce · **Minor (6)** · I3 × L2 · Treat: Mitigate + Transfer
A subsidiary's e-commerce platform is hosted by a third party that failed security standards.
**Business impact:** a breach at the host becomes Nordvale's breach in the eyes of customers and regulators; the subsidiary's revenue and the group's brand carry the consequence.
**Controls:** security due-diligence questionnaire and remediation plan with the vendor; contractual security clauses (right to audit, breach notification SLAs, minimum control standards); independent penetration test of the platform; **transfer** a portion of residual risk via cyber insurance.
**Target residual:** Insignificant (I3 × L1 = 3)

## R8 — Managed service provider transmitting credentials in plaintext email · **Minor (9)** · I3 × L3 · Treat: Mitigate
An MSP sends passwords via unencrypted email.
**Business impact:** intercepted or mailbox-resident plaintext credentials give attackers a quiet path into systems the MSP manages — and signal a weak security culture at a supplier with privileged access.
**Controls:** reset all credentials previously sent in plaintext; **contractual enforcement** — update the SLA/contract to prohibit insecure transmission and require a secure sharing mechanism (password vault link, S/MIME); internal policy banning credential transmission by email; TLS enforcement for mail in transit.
**Target residual:** Insignificant (I3 × L1 = 3)

## R9 — Unmonitored warehouse network infrastructure · **Significant (12)** · I4 × L3 · Treat: Mitigate
Networks deployed across warehouse sites without Technology-department oversight — invisible to internal teams and support partners.
**Business impact:** shadow infrastructure is unpatchable, unmonitorable and un-defendable; a compromise could halt warehouse operations (order fulfilment = revenue) and provide a bridge into corporate IT. You can't protect what you can't see.
**Controls:** discover and inventory all warehouse network assets with owners; segment warehouse networks from corporate IT; Network Access Control to block unknown devices; firewall rule review and closure of unneeded ports; scheduled vulnerability scanning; a policy requiring Technology sign-off for new network deployments *(governance fix so the problem doesn't regrow)*.
**Target residual:** Minor (I4 × L2 = 8)

## R10 — Unapproved AI tool usage across the business · **Minor (6)** · I2 × L3 · Treat: Mitigate (govern, don't just block)
Web-gateway reporting shows growing use of unapproved AI tools.
**Business impact:** sensitive data pasted into consumer AI tools leaves the organisation's control — a data-leak and confidentiality risk that grows silently with adoption.
**Controls:** **governance first** — an AI acceptable-use policy with approved tools and use cases (an approved enterprise tool with SSO/MFA gives staff a sanctioned path; blocking alone drives shadow IT); DLP rules blocking sensitive-data uploads to unapproved AI domains; gateway blocking of high-risk tools; awareness training on what must never be pasted; ongoing review of gateway/DLP reports for trends.
**Target residual:** Insignificant (I2 × L2 = 4)

---

## Register summary

| ID | Risk | I | L | Score | Rating | Treatment | Target residual |
|---|---|---|---|---|---|---|---|
| R1 | Unprotected cloud backups | 5 | 4 | 20 | **Critical** | Mitigate | Minor |
| R6 | Gov-related data in public channel | 5 | 4 | 20 | **Critical** | Mitigate (immediate) | Minor |
| R2 | Outdated endpoint security agent | 4 | 4 | 16 | **Severe** | Mitigate | Minor |
| R3 | Phishing failures (10% credential entry) | 3 | 4 | 12 | **Significant** | Mitigate | Minor |
| R4 | Shared vendor accounts | 4 | 3 | 12 | **Significant** | Mitigate | Minor |
| R5 | Insecure session cookies | 3 | 4 | 12 | **Significant** | Mitigate | Minor |
| R9 | Unmonitored warehouse networks | 4 | 3 | 12 | **Significant** | Mitigate | Minor |
| R8 | MSP plaintext credentials | 3 | 3 | 9 | Minor | Mitigate | Insignificant |
| R7 | Unvetted third-party hosting | 3 | 2 | 6 | Minor | Mitigate + Transfer | Insignificant |
| R10 | Unapproved AI tools | 2 | 3 | 6 | Minor | Mitigate (govern) | Insignificant |

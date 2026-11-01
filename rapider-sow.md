<!-- Rapider Official App SOW & Specification | App #167: Digital Credential & Certificate Issuance (digital-credential-and-certificate-issuance) | Domain: EDU -->

# #167 Digital Credential & Certificate Issuance (`digital-credential-and-certificate-issuance`) — Scope of Work (SOW)

- **App Number & Name:** `#167` — Digital Credential & Certificate Issuance
- **Proposed App Key:** `digital-credential-and-certificate-issuance`
- **Suite / Domain Key & Model Prefix:** `EDU` (`Edu*`)
- **Representative Product (`P1`):** Accredible
- **Combined Feature Catalog:** [../combined-features/167-digital-credential-and-certificate-issuance-features.md](../combined-features/167-digital-credential-and-certificate-issuance-features.md)
- **Target Release Posture:** Open Badges 3.0 & W3C Verifiable Credential Issuer Studio, Lifelong Learner Wallet, Stackable Pathways, CEU Recertification & Public Verification Microapplication

---

## 1. Executive Outcome & Target Audience

### 1.1 Business Problem Solved
Static emailed PDF certificates are trivially forged in image editors, impossible to revoke when professional licenses lapse, invisible to labor-market skill searches, and disconnected from institutional alumni growth. While Rapider's `LRN` suite defines internal `LrnCredential` completions, universities, professional licensing boards, customer academies, and training providers need cryptographic external portability. **Rapider Digital Credential & Certificate Issuance (`digital-credential-and-certificate-issuance`)** extends canonical `LrnCredential` records with a dual PDF/SVG visual studio, automatic 1EdTech **Open Badges 3.0** and **W3C Verifiable Credentials (`did:web`)** cryptographic signing, stackable micro-credential pathways, CEU recertification workflows, an external-importable lifelong learner wallet, and an instant public verification portal.

### 1.2 Target Personas & Progressive Disclosure
- **SME Fast-Path Defaults (Customer Academies, Bootcamps, Professional Associations):** Pick an `LrnCredential`, choose a branded certificate + badge artwork template, auto-issue signed Open Badges 3.0 assertions whenever learners complete an `LrnCourse` or `#164` exam, and let graduates share 1-click verifiable badges to LinkedIn.
- **Enterprise Progressive Disclosure (University Registrars, National Licensing Boards, Global Enterprises):** Unlock multi-department `did:web` issuer authorities, dual-control Registrar/Dean batch sign-off via Home `WorkItem`s, 1EdTech Comprehensive Learner Record (CLR v2.0) bundles, ACE credit portability (`Decimal128`), W3C `StatusList2021` revocation bitmaps, `<rapider-kanban>` CEU recertification audits, external third-party Open Badges 3.0 wallet ingestion synced to `HrEmployee` compliance, and *Spotlight* certified directories.

### 1.3 Measurable Business Outcomes
- **100% Tamper-Evident Verification in `< 200ms`:** Every credential carries a `did:web` Ed25519/ECDSA cryptographic proof and live `StatusList2021` revocation check—eliminating manual registrar phone/fax degree verifications.
- **2.5x Higher Organic Program Referral Reach:** 1-click LinkedIn profile embeds and branded verification landing pages turn every shared graduate badge into an attributed `MktCampaign` enrollment channel.
- **Automated License & CEU Compliance:** 90/30-day expiry triggers and structured CEU evidence audits keep certified practitioners and `HrEmployee` staff continuously compliant.

### 1.4 Benchmark Summary (`P1`–`P6`)
Synthesizes the dual visual studio, automatic Open Badges 3.0 / W3C VC conversion, ACE extensions, and LinkedIn referral analytics of **`P1` Accredible**, the skill taxonomy mapping, stackable pathways, and CEU renewals of **`P2` Credly**, the registrar diploma governance and CLR v2.0 portability of **`P3` Parchment / Canvas Credentials**, the high-velocity QR templates of **`P4` Certifier**, the `did:web` and `StatusList2021` cryptography of **`P5` Microsoft Entra Verified ID**, and the unified learner-to-`HrEmployee` wallet of **`P6` Workday**.

---

## 2. In-Scope, Out-of-Scope & Suite Ownership Boundaries

### 2.1 In-Scope Capabilities
1. Verified issuing authority profiles (`EduCredentialIssuer`) with `did:web` Decentralized Identifier metadata, co-signers, and signing key bindings.
2. Visual print/PDF diploma + SVG/PNG badge templates (`EduCredentialArtwork`) extending canonical `LrnCredential` definitions with dynamic merge tokens and QR verification codes.
3. Event-driven single and cohort batch issuance (`EduIssuanceBatch`), cryptographically signed Open Badges 3.0 / W3C VC assertions (`EduVerifiableAssertion`), and `StatusList2021` revocation/name-change superseding.
4. Stackable micro-credential pathways (`EduCredentialPathway`) and `<rapider-kanban>` CEU recertification/renewal reviews (`EduRenewalSubmission`).
5. Lifelong learner credential wallet supporting privacy toggles (`PUBLIC`, `UNLISTED_LINK_ONLY`, `PRIVATE`), lifelong personal email binding, and third-party Open Badges 3.0 import.
6. Zero-trust public verification portal (`EduVerificationLog`), opt-in *Spotlight* certified directory, and social referral attribution analytics.

### 2.2 Out-of-Scope Capabilities (Delegated to Adjacent Rapider Apps)
- **Internal LMS course modules, SCORM playback, and base `LrnCredential` / `LrnSkillDefinition` catalog definitions:** Owned by `LRN` (`online-learning`, `learning-experience-skills`) — **extended via `lrnCredentialId`, never duplicated**.
- **Academic course gradebooks, GPA calculation, and degree-audit credit rules:** Owned by `#161 Student Information System (SIS)`.
- **Proctored licensing exam delivery and psychometric item analysis:** Owned by `#164 Online Examination & Assessment`.
- **Payment gateway processing and invoice accounting for duplicate print orders:** Owned by `FIN` (`billing`, `payments`).

### 2.3 Cross-Suite Ownership & Integration Contract

| Domain / App | Owns (Canonical Models) | Integration Contract with `digital-credential-and-certificate-issuance` |
| :--- | :--- | :--- |
| **`digital-credential-and-certificate-issuance` (`#167` — This App)** | `EduCredentialIssuer`, `EduCredentialArtwork`, `EduIssuanceBatch`, `EduVerifiableAssertion`, `EduCredentialPathway`, `EduRenewalSubmission`, `EduVerificationLog` | Signs, delivers, wallets, renews, revokes, and publicly verifies Open Badges 3.0 / W3C VC credentials and diplomas. |
| **`LRN` Suite (`learning-experience-skills`, `online-learning`)** | `LrnCredential`, `LrnSkillDefinition`, `LrnCourse`, `LrnEnrollment` | `#167` binds `EduCredentialArtwork` to `LrnCredential.id`, embeds `LrnSkillDefinition` URIs inside OB 3.0 JSON-LD, and consumes `lrn.credential.earned.v1`. |
| **`#161 Student Information System` (`EDU`)** | `EduStudentProfile`, `EduTranscriptRecord`, `EduAcademicProgram` | Consumes `edu.student.graduated.v1` to stage degree/diploma assertions; respects `ferpaDirectoryOptOut` on the *Spotlight* public directory. |
| **`#164 Online Examination` (`EDU`)** | `EduExamSession`, `EduExamAttempt` | Consumes `edu.exam.certificationPassed.v1` to mint time-bounded professional certification assertions. |
| **`HR` Suite (`employees`)** | `HrEmployee` | Syncs earned, renewed, and verified imported external credentials onto `HrEmployee` talent/compliance records. |
| **`MKT` & `FIN` Suites (`email`, `social`, `campaigns`, `billing`)** | `MktEmailMessage`, `MktSocialPost`, `MktCampaign`, `FinInvoice` | `MKT` delivers claim emails and tracks verification-page referral conversions; `FIN` invoices paid duplicate diploma/apostille requests (`Decimal128`). |
| **Rapider Platform Services** | Identity/RBAC, KMS/Secrets, Files/Drive, Home `WorkItem`, `projectChannelMessage` | Signs VCs via platform KMS keys (zero hardcoded keys!), stores PDF/SVG renders in Drive, and routes batch sign-offs, revocations & CEU audits via Home `WorkItem`s. |

---

## 3. Primary Web Pages & Sidebar Navigation Architecture (13 Pages)

Every visible sidebar section strictly enforces the **Minimum 3 Items Rule (`>= 3` items with `displayOnMenu: true`)**: `Issuance & Studio` (3 items), `Pathways & Wallet` (3 items), and `Verification & Governance` (3 items) = 9 visible items + 4 hidden detail/drawer routes (`displayOnMenu: false`).

| # | Route | Page Title | Sidebar Section | Menu Visible | Key Components & UX |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | `credentials-pulse` | Credential & Impact Pulse | `Issuance & Studio` | `true` (Order 1) | KPI cards (`countSWR`): Total Active Assertions, Claim Rate %, LinkedIn Shares, Public Verifications (30d), Expiring Licenses (90d), Attributed Program Clicks. |
| 2 | `artwork-templates` | Certificate & Badge Studio | `Issuance & Studio` | `true` (Order 2) | `EduCredentialArtwork` catalog (`findSWR`) linked to `LrnCredential`, `#activeFilterTagsBar` (Issuer, Format, ACE Credits), clickable Template Name -> `artwork-template-detail`, icon+text Edit, icon-only Delete. |
| 3 | `issuance-batches` | Issuance Batches & Ledger | `Issuance & Studio` | `true` (Order 3) | `EduIssuanceBatch` & `EduVerifiableAssertion` explorer with `#activeFilterTagsBar` (Status, Source `#161`/`#164`/`LRN`, Bounce Flag), clickable Assertion Serial -> `assertion-verify-detail`. |
| 4 | `stackable-pathways` | Stackable Pathways & CLR | `Pathways & Wallet` | `true` (Order 1) | Configure `EduCredentialPathway` prerequisite milestone rules and 1EdTech CLR v2.0 achievement bundle definitions. |
| 5 | `ceu-renewals` | CEU & Recertification Board | `Pathways & Wallet` | `true` (Order 2) | `<rapider-kanban>` board of `EduRenewalSubmission` cards (`SUBMITTED` -> `UNDER_AUDIT` -> `NEEDS_EVIDENCE` -> `RENEWED`) + list toggle, AI CEU Pre-Auditor badge (`CRD-020`). |
| 6 | `learner-wallet` | Lifelong Credential Wallet | `Pathways & Wallet` | `true` (Order 3) | Earner view of owned & imported external OB 3.0 / W3C VC credentials with PDF/SVG/JSON-LD download, visibility selector, 1-click LinkedIn add, and Import External VC action. |
| 7 | `public-verifier` | Public Verification & Spotlight | `Verification & Governance` | `true` (Order 1) | Live 5-step cryptographic inspector (URL/Serial/JSON-LD dropzone) + opt-in *Spotlight* Certified Directory respecting `ferpaDirectoryOptOut`. |
| 8 | `issuer-authorities` | Issuer Profiles & `did:web` | `Verification & Governance` | `true` (Order 2) | Manage `EduCredentialIssuer` authorities, `did:web` status, co-signer titles, `<rapider-phone-input>` registrar verification desk contacts, and `StatusList2021` health. |
| 9 | `verification-analytics` | Verification & Viral ROI | `Verification & Governance` | `true` (Order 3) | `EduVerificationLog` audit ledger, employer lookup geographies, `MktCampaign` referral funnel metrics, and anomaly alerts (`CRD-022`). |
| 10 | `assertion-verify-detail` | Assertion & Cryptographic Proof | *(Hidden)* | `false` | Detailed `EduVerifiableAssertion` view (`#/assertion-verify-detail?id=...`) showing rendered diploma/badge, W3C VC JSON-LD proof, `LrnSkillDefinition` pills, Revoke / Re-issue Name Change controls, and `Back to list`. |
| 11 | `artwork-template-detail` | Studio Template & Merge Preview | *(Hidden)* | `false` | Detailed `EduCredentialArtwork` preview (`#/artwork-template-detail?id=...`) with PDF + SVG badge tabs, QR placement, AI Skill Mapper (`CRD-019`), and issued count. |
| 12 | `batch-issue-drawer` | Stage Cohort / Single Issuance | *(Hidden)* | `false` | Sliding drawer to stage `EduIssuanceBatch` or single assertion, run pre-flight validation, submit Registrar `WorkItem` sign-off, `finally` button reset, and `closePageDrawer()`. |
| 13 | `issuer-renewal-drawer` | Issuer / CEU Renewal Drawer | *(Hidden)* | `false` | Sliding drawer to configure `EduCredentialIssuer` (`<rapider-phone-input>`) or submit/audit `EduRenewalSubmission` (`Decimal128` CEUs) with `closePageDrawer()`. |

**Mandatory Rapider UI Standards Enforced Across All 13 Pages:**
- **SWR & Soft-Delete Hygiene:** Initial loads exclusively call `window.rapiderApi.findSWR` / `countSWR` with zero manual `isDeleted` filter clauses and filter `item.isDeleted !== true` in memory.
- **Table Actions & Navigation:** Zero standalone "View" buttons in `Actions`; primary identifiers navigate to `#/assertion-verify-detail?id=...` or `#/artwork-template-detail?id=...`; Edit uses icon + text; Delete uses icon-only with `title="Delete"` and `aria-label="Delete"`.
- **Contrast & Dialog Ban:** Primary and danger buttons enforce `#ffffff !important` white text; native `alert`/`confirm`/`prompt` are strictly banned.

---

## 4. Canonical Data Models (`Edu*` — 7 Models)

All models use platform-generated UUID `id` (`00000000-xxxx-xxxx-xxxx-xxxxxxxxxxxx` in sample seeds), omit `projectId`, enforce optimistic `version`, never store private cryptographic keys in database rows (referencing platform KMS key aliases only), and use `Decimal128` for ACE credits, CEU hours, and fulfillment fees.

| Model Name | Key Fields & Types | Relationships & External Refs | Invariants & Lifecycle |
| :--- | :--- | :--- | :--- |
| **`EduCredentialIssuer`** | `id` (UUID), `name` (string), `didWebIdentifier` (string, e.g., `did:web:credentials.example.edu:registrar`), `kmsSigningKeyAlias` (string), `signatoryName` (string), `signatoryTitle` (string), `verificationDeskPhoneE164` (string), `supportEmail` (string), `statusListUri` (string), `status` (`ACTIVE`, `SUSPENDED`), `version` (int) | `departmentId` -> `HrDepartment.id` (optional) | Private signing keys reside strictly in platform KMS (`kmsSigningKeyAlias`); public key JWK remains permanently resolvable so historical assertions stay verifiable even if rotated. |
| **`EduCredentialArtwork`** | `id` (UUID), `name` (string), `credentialCategory` (`MICRO_BADGE`, `COURSE_CERTIFICATE`, `PROFESSIONAL_LICENSE`, `ACADEMIC_DIPLOMA`, `CLR_BUNDLE`), `pdfLayoutJson` (JSON), `svgBadgeTemplate` (string), `aceRecommendedCredits` (`Decimal128`), `validityMonths` (int, nullable for lifetime), `requiredRenewalCeus` (`Decimal128`), `requiresDualControlSignOff` (boolean), `duplicatePrintFeeAmount` (`Decimal128`), `currency` (string), `status` (`DRAFT`, `PUBLISHED`, `RETIRED`), `version` (int) | `lrnCredentialId` -> `LrnCredential.id`, `issuerId` -> `EduCredentialIssuer.id`, `skillIds` -> `LrnSkillDefinition.id[]` | Extends canonical `LrnCredential` 1-to-1 per issuer branding; `ACADEMIC_DIPLOMA` and `PROFESSIONAL_LICENSE` enforce `requiresDualControlSignOff = true`. |
| **`EduIssuanceBatch`** | `id` (UUID), `batchCode` (string), `sourceTrigger` (`SIS_GRADUATION`, `EXAM_PASSED`, `LRN_COURSE`, `MANUAL_COHORT`), `candidateCount` (int), `bouncedEmailCount` (int), `status` (`DRAFT`, `PREFLIGHT_VALIDATED`, `PENDING_REGISTRAR_SIGN_OFF`, `SIGNING_IN_PROGRESS`, `ISSUED`), `issuedAt` (Date), `version` (int) | `artworkId` -> `EduCredentialArtwork.id`, `issuerId` -> `EduCredentialIssuer.id`, `approvedByEmployeeId` -> `HrEmployee.id` | Batches with `requiresDualControlSignOff = true` cannot transition to `SIGNING_IN_PROGRESS` without an approved Home `WorkItem` from a distinct user than the batch creator. |
| **`EduVerifiableAssertion`** | `id` (UUID), `publicSerialCode` (string, unique), `isExternalImported` (boolean), `externalIssuerDid` (string), `recipientFullName` (string), `recipientInstitutionalEmail` (string), `recipientPersonalEmail` (string), `issuedAt` (Date), `expiresAt` (Date), `w3cVcJsonLd` (JSON, signed OB 3.0 / W3C VC proof), `pdfDriveFileId` (string), `bakedBadgeDriveFileId` (string), `statusListIndex` (int), `assertionStatus` (`ACTIVE_VALID`, `EXPIRING_SOON`, `EXPIRED`, `REVOKED`, `SUPERSEDED_NAME_CHANGE`), `revocationReasonCode` (string), `walletVisibility` (`PUBLIC`, `UNLISTED_LINK_ONLY`, `PRIVATE`), `claimedAt` (Date), `version` (int) | `batchId` -> `EduIssuanceBatch.id` (optional), `artworkId` -> `EduCredentialArtwork.id`, `lrnCredentialId` -> `LrnCredential.id`, `studentId` -> `EduStudentProfile.id` (optional), `hrEmployeeId` -> `HrEmployee.id` (optional), `supersededByAssertionId` -> `EduVerifiableAssertion.id` (optional) | Signed `w3cVcJsonLd` payload is strictly immutable after issuance; revoking flips the `StatusList2021` bit at `statusListIndex` and sets `assertionStatus = REVOKED`; legal name changes issue a new assertion pointing back via `supersededByAssertionId`. |
| **`EduCredentialPathway`** | `id` (UUID), `name` (string), `description` (string), `requiredArtworkIds` (UUID[]), `electiveArtworkIds` (UUID[]), `minElectiveCount` (int), `capstoneArtworkId` (UUID), `autoIssueCapstone` (boolean), `status` (`ACTIVE`, `ARCHIVED`), `version` (int) | `capstoneLrnCredentialId` -> `LrnCredential.id` | Graph must be a Directed Acyclic Graph (DAG) — circular pathway dependencies are deterministically rejected on save. |
| **`EduRenewalSubmission`** | `id` (UUID), `claimedCeuCredits` (`Decimal128`), `verifiedCeuCredits` (`Decimal128`), `evidenceDriveFileIds` (string[]), `activitySummary` (string), `stage` (`SUBMITTED`, `UNDER_AUDIT`, `NEEDS_EVIDENCE`, `RENEWED`, `DECLINED`), `auditedAt` (Date), `version` (int) | `assertionId` -> `EduVerifiableAssertion.id`, `auditorEmployeeId` -> `HrEmployee.id`, `renewalFeeInvoiceId` -> `FinInvoice.id` (optional) | Transitioning to `RENEWED` requires `verifiedCeuCredits >= artwork.requiredRenewalCeus` and mints/extends the renewed assertion window cleanly. |
| **`EduVerificationLog`** | `id` (UUID), `checkedSerialCode` (string), `verificationOutcome` (`VALID`, `EXPIRED`, `REVOKED`, `INVALID_SIGNATURE`, `NOT_FOUND`), `verifierRegionCountry` (string), `referralSource` (`DIRECT_QR`, `LINKEDIN`, `SPOTLIGHT_DIRECTORY`, `JSON_UPLOAD`), `clickedProgramCta` (boolean), `anomalyFlagged` (boolean), `verifiedAt` (Date) | `assertionId` -> `EduVerifiableAssertion.id` (optional), `attributedCampaignId` -> `MktCampaign.id` (optional) | Append-only audit telemetry; stores zero PII about anonymous employer verifiers (country-level geo only for GDPR compliance). |

---

## 5. Core End-to-End User Journeys

### 5.1 Journey 1: SME Academy Fast-Path — Course Completion -> Automatic Open Badges 3.0 & LinkedIn Share
1. Academy Admin opens `artwork-templates`, links `LrnCredential` *"Rapider Certified Cloud Builder"* to a certificate + SVG badge design (`EduCredentialArtwork`, `requiresDualControlSignOff = false`), and publishes it.
2. When a learner completes the mapped `LrnCourse` (or passes `#164` exam), `#167` consumes `lrn.credential.earned.v1`, signs the Open Badges 3.0 / W3C VC JSON-LD via platform KMS, renders the QR-embedded PDF + baked PNG badge to Files/Drive, and emails the claim link via `MKT`.
3. Learner opens `learner-wallet`, attaches a permanent personal Gmail address, clicks **Add to LinkedIn Profile**, and shares to social—driving tracked employer verifications and `MktCampaign` program clicks.

### 5.2 Journey 2: University Graduation Cohort -> Dual-Control Registrar `WorkItem` Sign-Off
1. `#161 SIS` emits `edu.student.graduated.v1` for 320 Bachelor of Science graduates, staging `EduIssuanceBatch` `2026-SPRING-BS` (`requiresDualControlSignOff = true`).
2. Pre-flight check validates 320 names, honors Latin distinctions, `Decimal128` GPAs, and `ferpaDirectoryOptOut` privacy defaults (auto-setting `walletVisibility = UNLISTED_LINK_ONLY` for FERPA-restricted graduates), then routes a Rapider Home `WorkItem` to the University Registrar.
3. Registrar approves the `WorkItem`; `credentialBatchSigningAndDeliveryWorkflow` cryptographically signs all 320 `EduVerifiableAssertion`s idempotently.

### 5.3 Journey 3: Stackable Micro-Credential Auto-Capstone Award
1. An earner already holds *Data Engineering I* and *Streaming Pipelines* badges and earns *Cloud Governance* (the 3rd milestone in `EduCredentialPathway`).
2. `stackablePathwayEvaluationWorkflow` detects 100% DAG completion and automatically issues the capstone *Master Data Architect* W3C VC without manual admin intervention.

### 5.4 Journey 4: Zero-Trust Employer QR Verification & `StatusList2021` Revocation Check
1. An employer scans the QR code on a candidate's PDF certificate, opening `public-verifier`.
2. `#167` verifies the Ed25519 signature against `did:web`, checks `expiresAt`, and inspects bit `statusListIndex` on `StatusList2021` in `< 200ms`—returning a green **Cryptographically Verified & Active** seal (or red **Revoked on [Date]** banner if revoked via Home `WorkItem`).

### 5.5 Journey 5: CEU Recertification Audit (`<rapider-kanban>`) & `HrEmployee` Sync
1. 60 days before a 2-year safety license expires, the holder uploads 20.00 `Decimal128` CEU hours on `ceu-renewals` (`EduRenewalSubmission`).
2. Grounded AI CEU Pre-Auditor (`CRD-020`) summarizes the uploaded certificates in `projectChannelMessage`; Auditor verifies `20.00 >= 20.00` required CEUs and drags the card to `RENEWED`, updating the credential and syncing compliance status to `HrEmployee`.

### 5.6 Journey 6: Click-Through Navigation & `#activeFilterTagsBar` State Restoration
1. Registrar filters `issuance-batches` assertions by `Status: "ACTIVE_VALID"` and searches `"Kowalski"`, displaying `#activeFilterTagsBar` chips.
2. Clicking serial **CRD-2026-00941** transitions smoothly to `#/assertion-verify-detail?id=...` without `<base href>` 404 diversion, displays the W3C VC proof, and **Back to list** restores the exact filtered state.

---

## 6. Consolidated Feature Priorities & Work Packages

### `P0` Foundation Work Packages (Must-Have Core Release)
- **WP-P0-1 — `did:web` Issuers & Certificate/Badge Studio (`CRD-001`, `CRD-002`, `CRD-003`):** Deliver `EduCredentialIssuer` (platform KMS signing), `EduCredentialArtwork` extending `LrnCredential`, and Open Badges 3.0 / W3C VC JSON-LD cryptographic signing.
- **WP-P0-2 — Event/Batch Issuance, Dual-Control Sign-Off & Revocation (`CRD-005`, `CRD-006`, `CRD-007`):** Build `#161`/`#164`/`LRN` event triggers, `EduIssuanceBatch` pre-flight + Registrar Home `WorkItem` dual-control, `StatusList2021` revocation, and legal name-change superseding.
- **WP-P0-3 — Stackable Pathways, CEU Kanban, Learner Wallet & Public Verifier (`CRD-010`, `CRD-011`, `CRD-013`, `CRD-016`):** Deliver DAG `EduCredentialPathway` engine, `<rapider-kanban>` `ceu-renewals`, `learner-wallet` privacy controls, and `< 200ms` `public-verifier`.

### `P1` Enterprise Scale Work Packages
- **WP-P1-1 — CLR v2.0 Bundles, Bounce Recovery, Paid Duplicates & `HR` Sync (`CRD-004`, `CRD-008`, `CRD-009`, `CRD-012`):** Add 1EdTech CLR v2.0 achievement graphs, `MKT` email bounce recovery, `FIN` `FinInvoice` duplicate diploma orders (`Decimal128`), and `HrEmployee` talent/license sync.
- **WP-P1-2 — External OB 3.0 Import, LinkedIn Embeds, Spotlight Directory & Viral Analytics (`CRD-014`, `CRD-015`, `CRD-017`, `CRD-018`):** Add third-party VC signature verification on wallet import, 1-click LinkedIn/email embeds, FERPA-safe *Spotlight* public directory, and `MktCampaign` attribution analytics.

### `P2` Adjacent & Grounded AI Work Packages
- **WP-P2-1 — Grounded AI Skill Mapper, CEU Pre-Auditor, Pathway Advisor & Fraud Radar (`CRD-019`, `CRD-020`, `CRD-021`, `CRD-022`):** Deliver `LrnSkillDefinition` syllabus alignment suggestions, `projectChannelMessage` CEU document pre-audits, stackable next-badge recommendations, and `EduVerificationLog` enumeration/forgery detection.

---

## 7. Roles, Permissions & Field-Level Governance

| Role | Permitted Actions | Restricted / Field-Level Boundaries |
| :--- | :--- | :--- |
| **Credential Earner / Alumni** | Claim credentials, link lifelong personal email, set `walletVisibility` (`PUBLIC`, `UNLISTED_LINK_ONLY`, `PRIVATE`), download PDF/PNG/JSON-LD, import external OB 3.0 VCs, submit `EduRenewalSubmission` CEUs, and request legal name-change re-issuance. | Cannot edit signed achievement fields, alter `issuedAt`/`expiresAt`, or appear in *Spotlight* if `walletVisibility != PUBLIC` or `#161` `ferpaDirectoryOptOut = true`. |
| **Anonymous Public Verifier** | Verify any `UNLISTED_LINK_ONLY` or `PUBLIC` credential via direct URL/QR/JSON-LD dropzone and browse opt-in `PUBLIC` *Spotlight* directory entries. | Zero access to `PRIVATE` credentials, `recipientInstitutionalEmail`/`recipientPersonalEmail`, or bulk enumeration APIs. |
| **Program Coordinator / Designer** | Design `EduCredentialArtwork`, define `EduCredentialPathway` DAGs, stage `EduIssuanceBatch` drafts, and audit `EduRenewalSubmission` CEU queues. | Cannot unilaterally sign `requiresDualControlSignOff = true` degree/license batches or revoke high-stakes diplomas without Registrar `WorkItem` approval. |
| **Registrar / Chief Credential Officer** | Manage `EduCredentialIssuer` authorities, approve dual-control batch sign-off `WorkItem`s, execute audited `StatusList2021` revocations, and approve legal name-change re-issuances. | Never accesses raw private cryptographic keys (enforced inside KMS); cannot silently mutate an already-signed `w3cVcJsonLd` document. |

---

## 8. Technical APIs, Guarded Commands, Events & `requiredWorkflows`

### 8.1 Guarded Domain Commands
Every state-mutating API enforces `idempotencyKey`, `correlationId`, and `expectedVersion`:
- `edu.credentials.stageAndValidateBatch` — Validates recipient emails, dynamic merge fields, and `#161` FERPA flags; routes dual-control `WorkItem` when `requiresDualControlSignOff = true`.
- `edu.credentials.signAndIssueAssertions` — Invokes platform KMS (`kmsSigningKeyAlias`) to generate W3C VC / Open Badges 3.0 proofs, allocates `statusListIndex`, renders PDF/SVG assets, and emits claim notifications.
- `edu.credentials.revokeOrSupersedeAssertion` — Updates `StatusList2021` bitstring and sets `REVOKED` (or mints a replacement assertion on legal name change linked via `supersededByAssertionId`).
- `edu.credentials.importExternalOpenBadge` — Cryptographically verifies third-party issuer `did:web` / OB 3.0 public key before storing `isExternalImported = true` in the wallet.
- `edu.credentials.approveCeuRenewal` — Verifies `verifiedCeuCredits >= requiredRenewalCeus` (`Decimal128`), extends/re-issues the assertion, and syncs `HrEmployee`.

### 8.2 Domain Events Published & Consumed (Kafka)
- **Published:** `edu.credential.assertionIssued.v1`, `edu.credential.assertionClaimed.v1`, `edu.credential.assertionRevoked.v1`, `edu.credential.pathwayCapstoneEarned.v1`, `edu.credential.renewed.v1`.
- **Consumed:** `lrn.credential.earned.v1` (from `LRN`), `edu.student.graduated.v1` (from `#161 SIS`), `edu.exam.certificationPassed.v1` (from `#164`), `fin.payment.succeeded.v1` (fulfills paid duplicate print/renewal fees).

### 8.3 `requiredWorkflows` (Declared in `app.manifest.json`)
1. `credentialBatchSigningAndDeliveryWorkflow` — Executes KMS JSON-LD signing, PDF/baked-PNG rendering, `MKT` claim dispatch, and bounce monitoring.
2. `stackablePathwayEvaluationWorkflow` — Evaluates `EduCredentialPathway` DAG completion on every `edu.credential.assertionIssued.v1` event to auto-issue capstones.
3. `credentialExpiryAndCeuReminderWorkflow` — Sends 90/60/30-day renewal reminders, transitions overdue licenses to `EXPIRED`, and updates `HrEmployee` compliance flags.
4. `statusList2021PublicationWorkflow` — Compresses and publishes signed W3C `StatusList2021` revocation bitstrings without leaking holder list sizes or PII.

### 8.4 Grounded Rapider AI Rules
- AI Skill Mapper (`CRD-019`), CEU Pre-Auditor (`CRD-020`), and Pathway Advisor (`CRD-021`) MUST cite canonical `LrnSkillDefinition`, `LrnCourse`, and uploaded Drive evidence files.
- AI NEVER signs credentials, approves CEU audits, or revokes licenses autonomously—all issuance, renewal, and revocation commands require deterministic rules or explicit human confirmation.

---

## 9. Security, Privacy, Compliance & Non-Functional Requirements

- **Zero Hardcoded Keys & Cryptographic Standards:** Strictly adheres to 1EdTech Open Badges 3.0, W3C Verifiable Credentials Data Model, `did:web`, and `StatusList2021`. Private keys NEVER touch source code, `.env` exports in client bundles, or MongoDB rows—signing occurs exclusively via platform KMS.
- **GDPR Right to Privacy, FERPA & Selective Disclosure:** Public verification pages never expose recipient email addresses or student IDs; `ferpaDirectoryOptOut = true` from `#161 SIS` defaults assertions to `UNLISTED_LINK_ONLY` and excludes them from *Spotlight* search; earners can switch any credential to `PRIVATE` at any time.
- **Exact `Decimal128` Precision:** ACE credit recommendations (e.g., `3.00` credits), CEU hours (`12.50` CEUs), and duplicate-diploma fulfillment fees (e.g., `\$35.00`) strictly use `Decimal128`.
- **Accessibility & Responsive UX:** Full WCAG 2.2 AA compliance (accessible HTML/text alternative alongside visual diploma/badge graphics, ARIA labels on icon-only Delete buttons, `#ffffff !important` primary/danger button contrast across light and dark modes) across `390px`, `768px`, and `1440px`.

---

## 10. Deterministic Acceptance Criteria

1. **Sidebar 3-Item Section Rule:** `app.manifest.json` defines 3 visible sidebar sections (`Issuance & Studio`, `Pathways & Wallet`, `Verification & Governance`), each containing 3 visible items (`displayOnMenu: true`), while all 4 detail/drawer pages set `displayOnMenu: false`.
2. **SWR & Soft-Delete Query Hygiene:** Initial loads across all pages invoke `findSWR` / `countSWR` with zero manual `isDeleted` filter clauses and filter `item.isDeleted !== true` in memory.
3. **Search, `#activeFilterTagsBar` & Clear All:** Filtering `artwork-templates`, `issuance-batches`, `ceu-renewals`, or `public-verifier` displays HTML-escaped chips in `#activeFilterTagsBar` with `[Clear all]`, restoring the full dataset in one click.
4. **Table Action Standard:** Zero standalone "View" buttons appear in `Actions`; primary identifiers navigate to `#/assertion-verify-detail?id=...` or `#/artwork-template-detail?id=...`; Edit uses icon + text and Delete uses icon-only with `title="Delete"` and `aria-label="Delete"`.
5. **Custom Elements Adoption:** Issuer verification desk contacts in `issuer-authorities` and `issuer-renewal-drawer` use `<rapider-phone-input>`, and `ceu-renewals` uses `<rapider-kanban>`.
6. **Optimistic Lifecycle & Drawer Auto-Close:** Saving `batch-issue-drawer` or `issuer-renewal-drawer` resets button state in a `finally` block, invokes `closePageDrawer()`, clears SWR cache, broadcasts events, and refreshes parent views; deletions use `#rapiderConfirmOkBtn` with zero native `alert`/`confirm`/`prompt`.
7. **Canonical `LRN` Reuse & Dual-Control Gate:** `EduCredentialArtwork` references `LrnCredential.id` without duplicating LMS course tables, and `requiresDualControlSignOff = true` batches block signing until a Rapider Home `WorkItem` is approved by a second authorized officer.
8. **Immutable W3C VC Proof & `StatusList2021` Revocation:** Direct edits to `EduVerifiableAssertion.w3cVcJsonLd` after issuance are rejected; revoking an assertion flips its `StatusList2021` bit so `public-verifier` immediately reports `REVOKED`, while tampered JSON-LD uploads report `INVALID_SIGNATURE`.
9. **DAG Stackable Pathway Invariant:** Saving a cyclic `EduCredentialPathway` is rejected; completing all prerequisite badges in an active DAG automatically issues the capstone credential.
10. **FERPA & Wallet Privacy Enforcement:** Assertions with `walletVisibility = PRIVATE` return `NOT_FOUND` / private notice to unauthenticated verifiers, and `#161` `ferpaDirectoryOptOut = true` learners never appear in *Spotlight* directory queries.
11. **Click-Through Navigation & Theme Compliance:** Clicking a serial in `issuance-batches` navigates cleanly to `#/assertion-verify-detail?id=...` without `<base href>` 404 diversion, `Back to list` restores filters, all pages pass `validate_theme` in dark/light modes with `#ffffff !important` primary/danger buttons, and zero schemas contain `projectId`.

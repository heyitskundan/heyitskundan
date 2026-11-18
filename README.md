<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Kundan Sinha · Engineering lead, healthcare interoperability" src="assets/header-light.svg" width="100%">
</picture>

<p align="left">
  <a href="https://heyitskundan.com"><img src="https://img.shields.io/badge/Portfolio-heyitskundan.com-2DD4BF?style=flat-square&labelColor=0B0F14" alt="Portfolio"></a>
  <a href="https://linkedin.com/in/heyitskundan"><img src="https://img.shields.io/badge/LinkedIn-heyitskundan-2DD4BF?style=flat-square&labelColor=0B0F14&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:heyitskundan.dev@gmail.com"><img src="https://img.shields.io/badge/Email-heyitskundan.dev%40gmail.com-2DD4BF?style=flat-square&labelColor=0B0F14&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Status-open_to_Lead%2FStaff_roles-2DD4BF?style=flat-square&labelColor=0B0F14" alt="Open to roles">
</p>

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-about-dark.svg">
  <img alt="About" src="assets/section-about-light.svg" width="100%">
</picture>

I build the plumbing between clinical systems and the products that need their data: FHIR R4, HL7v2, C-CDA, SMART-on-FHIR and Epic, with HIPAA in mind from the first commit.

As **founding engineer at Visilant**, I took a healthcare product from nothing to **5 live hospital deployments in 2 years**, wired it into **Epic over SMART-on-FHIR**, and carried it through a **HIPAA audit**. Its eye-screening pipeline has reached **50,000+ patients**. At the same time I was **engineering lead at Ziplyne**, running a **16-person team** that shipped an enterprise platform to **150K+ users**, 30K of them at **Johns Hopkins**, through **SOC 2**.

I'm based in Hyderabad and work US hours. I'm looking for Lead or Staff roles at healthtech, EHR and interoperability companies.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/impact-dark.svg">
  <img alt="5 hospitals on Epic SMART-on-FHIR · 50K+ patients screened · 150K+ users · HIPAA + SOC 2" src="assets/impact-light.svg" width="100%">
</picture>

<br><br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-work-dark.svg">
  <img alt="Selected work" src="assets/section-work-light.svg" width="100%">
</picture>

### 🏥 Epic integration across 5 hospitals · *Visilant*

**Problem.** Hospital customers needed screening results to land in the patient's Epic chart, with no re-typing and no CSV exports.<br>
**What I built.** A SMART-on-FHIR backend client that reads and writes Patient, Observation, DiagnosticReport, ImagingStudy, Media and ServiceRequest. It authenticates by JWT client assertion against an RS384-signed JWKS. I also built multi-tenant isolation: tenant-scoped request context, JWT tenant checks and tenant-scoped caching.<br>
**Outcome.** Live in 5 hospitals within 2 years. HIPAA audit passed, with audit-trail tables and ABHA health-ID handling.

```mermaid
flowchart LR
  A[Visilant app] -->|JWT client assertion<br/>RS384 / JWKS| B(Epic auth server)
  B -->|access token| A
  A -->|FHIR R4 read/write| C[(Epic FHIR API)]
  C --- D["Patient · Observation<br/>DiagnosticReport<br/>ImagingStudy · Media<br/>ServiceRequest"]
```

### 👁️ Seeker: ML-assisted eye screening · *Visilant*

**What I built.** APIs that send captured eye images to a production ML diagnosis model, and the clinician view that shows the suggested diagnosis next to the patient record.<br>
**Outcome.** **50,000+ patients** screened in production with partners including Aravind Eye Hospital and Dr. Shroff's Charity Eye Hospital.

### 🧭 URL+: page identification for 150K users · *Ziplyne*

**Problem.** In-app guides have to know exactly which screen a user is on, across enterprise apps whose URLs change all the time.<br>
**What I built.** Per-platform adapters that resolve those URLs to one canonical page, and a selector engine that finds targets through iframes and shadow DOM. It covers ServiceNow, SAP (Fiori, Portal, ESS), SuccessFactors, Microsoft Dynamics, Coupa and Workday.<br>
**Outcome.** Serves **150K+ users**, including 30K at Johns Hopkins.

### 🔐 Enterprise identity and HR sync · *Ziplyne*

- **Workday HR sync:** RaaS report ingestion, user upsert and group reconciliation as a BullMQ job. Grew from **50K to 120K** records.
- **SSO for 5 enterprise customers:** SAML (Okta, IBM Security Verify, Shibboleth) and Coupa OAuth2, with automatic user and role setup on first login.
- **SOC 2:** owned the AWS database controls, covering encryption at rest and in transit, and backups.

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-oss-dark.svg">
  <img alt="Open source" src="assets/section-oss-light.svg" width="100%">
</picture>

Most healthcare data still moves as HL7v2 pipes and C-CDA XML. I write the libraries that turn it into FHIR without dropping fields, and that let you trace every output field back to its source.

<p>
  <a href="https://github.com/heyitskundan/interop-gateway"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-interop-gateway-dark.svg"><img src="assets/oss-interop-gateway-light.svg" alt="interop-gateway" width="32%"></picture></a>
  <a href="https://github.com/heyitskundan/hl7-fhir-translator"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-hl7-fhir-translator-dark.svg"><img src="assets/oss-hl7-fhir-translator-light.svg" alt="hl7-fhir-translator" width="32%"></picture></a>
  <a href="https://github.com/heyitskundan/cda-fhir-translator"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-cda-fhir-translator-dark.svg"><img src="assets/oss-cda-fhir-translator-light.svg" alt="cda-fhir-translator" width="32%"></picture></a>
</p>

> **For AI-in-healthcare teams:** `interop-gateway` ships an **MCP server**, so an AI agent can query a live EHR through 15 tools. Every call is scope-checked and audit-logged before it touches the system.

**Side projects:** [whispr](https://github.com/heyitskundan/whispr) (on-device push-to-talk speech-to-text) · [daylog](https://github.com/heyitskundan/daylog) (local-first activity tracker with on-device OCR)

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-journey-dark.svg">
  <img alt="Journey" src="assets/section-journey-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/timeline-dark.svg">
  <img alt="Intelehealth 2018 to 2020 · Ziplyne 2020 to 2026 · Visilant 2021 to 2026 · MSc Cardiff 2021 to 2023" src="assets/timeline-light.svg" width="100%">
</picture>

<details>
<summary><b>Visilant</b> · Founding Engineer · Aug 2021 to Jun 2026 · remote</summary>
<br>

- Only full-stack engineer on a team of 5; owned the backend and the React front end
- Took the product from scratch to 5 hospital deployments in 2 years
- Built the Epic SMART-on-FHIR integration, the Seeker ML screening pipeline, the multi-tenant migration and the HIPAA technical controls
</details>

<details>
<summary><b>Ziplyne</b> · Software Engineering Lead · Oct 2020 to Jul 2026 · remote</summary>
<br>

- Joined as a full-stack engineer and was promoted to lead in Jan 2022
- Technical lead of 16 people: 5 engineers, 4 QA, 3 designers, 2 customer success and 1 PM
- Built URL+, the Workday HR sync and SSO for 5 enterprise customers, and owned the SOC 2 database controls
</details>

<details>
<summary><b>Intelehealth</b> · Full Stack Developer · Jul 2018 to Sep 2020 · Thane</summary>
<br>

- Built the Angular front end of the [doctor web app](https://github.com/Intelehealth/intelehealth-doctor-webapp) (16★, 29 forks) for a telehealth platform on OpenMRS
- Built the Node.js image upload and retrieval API
</details>

<details>
<summary><b>Cardiff University</b> · MSc Advanced Computer Science · 2021 to 2023</summary>
<br>

- Thesis: *Creating a User Interface for Virtual Assistants*, a COVID-advisory chatbot on IBM Watson Assistant and Cloudant
</details>

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-stack-dark.svg">
  <img alt="Toolkit" src="assets/section-stack-light.svg" width="100%">
</picture>

| Area | Tools |
|---|---|
| **Interoperability** | ![FHIR R4](https://img.shields.io/badge/FHIR_R4-0B0F14?style=flat-square&logo=fhir&logoColor=2DD4BF) ![HL7v2](https://img.shields.io/badge/HL7v2-0B0F14?style=flat-square) ![C-CDA](https://img.shields.io/badge/C--CDA-0B0F14?style=flat-square) ![SMART-on-FHIR](https://img.shields.io/badge/SMART--on--FHIR-0B0F14?style=flat-square) ![Epic](https://img.shields.io/badge/Epic-0B0F14?style=flat-square) ![OpenMRS](https://img.shields.io/badge/OpenMRS-0B0F14?style=flat-square) ![ABHA](https://img.shields.io/badge/ABHA-0B0F14?style=flat-square) |
| **Compliance** | ![HIPAA](https://img.shields.io/badge/HIPAA-0B0F14?style=flat-square) ![SOC 2](https://img.shields.io/badge/SOC_2-0B0F14?style=flat-square) |
| **Languages & frameworks** | ![TypeScript](https://img.shields.io/badge/TypeScript-0B0F14?style=flat-square&logo=typescript&logoColor=2DD4BF) ![Node.js](https://img.shields.io/badge/Node.js-0B0F14?style=flat-square&logo=nodedotjs&logoColor=2DD4BF) ![React](https://img.shields.io/badge/React-0B0F14?style=flat-square&logo=react&logoColor=2DD4BF) ![Angular](https://img.shields.io/badge/Angular-0B0F14?style=flat-square&logo=angular&logoColor=2DD4BF) ![SQL](https://img.shields.io/badge/SQL-0B0F14?style=flat-square) |
| **Infrastructure** | ![AWS](https://img.shields.io/badge/AWS-0B0F14?style=flat-square&logo=amazonwebservices&logoColor=2DD4BF) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0B0F14?style=flat-square&logo=postgresql&logoColor=2DD4BF) ![MySQL](https://img.shields.io/badge/MySQL-0B0F14?style=flat-square&logo=mysql&logoColor=2DD4BF) ![Redis](https://img.shields.io/badge/Redis-0B0F14?style=flat-square&logo=redis&logoColor=2DD4BF) ![BullMQ](https://img.shields.io/badge/BullMQ-0B0F14?style=flat-square) |
| **Identity** | ![SAML SSO](https://img.shields.io/badge/SAML_SSO-0B0F14?style=flat-square) ![OAuth2](https://img.shields.io/badge/OAuth2-0B0F14?style=flat-square) ![JWT/JWKS](https://img.shields.io/badge/JWT_%2F_JWKS-0B0F14?style=flat-square) ![Okta](https://img.shields.io/badge/Okta-0B0F14?style=flat-square&logo=okta&logoColor=2DD4BF) |
| **AI tooling** | ![MCP](https://img.shields.io/badge/MCP_servers-0B0F14?style=flat-square) ![Claude Code](https://img.shields.io/badge/Claude_Code-0B0F14?style=flat-square&logo=anthropic&logoColor=2DD4BF) |

<br>

---

<p align="center">
  <sub>Building on FHIR and need someone who has shipped it into real hospitals? <a href="mailto:heyitskundan.dev@gmail.com"><b>Let's talk.</b></a></sub>
</p>

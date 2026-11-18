<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Kundan Sinha · Full-stack engineering lead" src="assets/header-light.svg" width="100%">
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

I'm a full-stack engineer with 8+ years of building products end to end: React and Angular front ends, Node.js and TypeScript back ends, AWS infrastructure, and the integrations that tie it all together. I've been the first engineer on a product and the tech lead of a 16-person team, often both at once.

Along the way I've worked across very different problems:

- **Enterprise SaaS:** a Chrome-extension platform serving **150K+ users**, 30K of them at **Johns Hopkins**, across ServiceNow, SAP, Workday and more
- **Identity and data:** SAML/OAuth2 SSO for enterprise customers and an HR data sync that scaled to **120K records**
- **Healthcare:** a product taken from zero to **5 live hospitals in 2 years**, with an Epic integration and an ML screening pipeline that has seen **50,000+ patients**
- **Compliance:** owned the engineering side of **HIPAA** and **SOC 2** audits
- **AI tooling:** MCP servers, on-device speech-to-text, and local-first apps on the side

I'm based in Hyderabad and work US hours. I'm open to Lead, Staff and senior full-stack roles, in any domain where the problems are interesting.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/impact-dark.svg">
  <img alt="150K+ users · 16-person team · 5 hospitals · 50K+ patients screened" src="assets/impact-light.svg" width="100%">
</picture>

<br><br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-work-dark.svg">
  <img alt="Selected work" src="assets/section-work-light.svg" width="100%">
</picture>

### 🧭 URL+: an enterprise Chrome-extension platform for 150K users · *Ziplyne*

**Problem.** Ziplyne's in-app guides run as a browser extension (Manifest V2/V3) on top of other companies' enterprise apps. They have to know exactly which screen a user is on, even though those apps' URLs change all the time.<br>
**What I built.** Per-platform adapters that resolve those URLs to one canonical page, and a selector engine that finds targets through iframes and shadow DOM. It covers ServiceNow, SAP (Fiori, Portal, ESS), SuccessFactors, Microsoft Dynamics, Coupa and Workday.<br>
**Outcome.** Serves **150K+ users**, including 30K at Johns Hopkins.

### 🔐 Enterprise identity and HR sync · *Ziplyne*

- **Workday HR sync:** RaaS report ingestion, user upsert and group reconciliation as a BullMQ job. Grew from **50K to 120K** records.
- **SSO for 5 enterprise customers:** SAML (Okta, IBM Security Verify, Shibboleth) and Coupa OAuth2, with automatic user and role setup on first login.
- **SOC 2:** owned the AWS database controls, covering encryption at rest and in transit, and backups.

### 🏥 A healthcare product from zero to 5 hospitals · *Visilant*

**Context.** I was the only full-stack engineer, owning the React front end and the Node.js back end. Hospital customers needed results to land in the patient's Epic chart, with no re-typing and no CSV exports.<br>
**What I built.** The product itself, plus a SMART-on-FHIR backend client that reads and writes Patient, Observation, DiagnosticReport, ImagingStudy, Media and ServiceRequest. It authenticates by JWT client assertion against an RS384-signed JWKS. I also built multi-tenant isolation: tenant-scoped request context, JWT tenant checks and tenant-scoped caching.<br>
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

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-oss-dark.svg">
  <img alt="Open source" src="assets/section-oss-light.svg" width="100%">
</picture>

Three TypeScript libraries published on npm that turn legacy healthcare formats (HL7v2, C-CDA) into FHIR without dropping fields, plus a couple of local-first tools I built for myself.

<p>
  <a href="https://github.com/heyitskundan/interop-gateway"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-interop-gateway-dark.svg"><img src="assets/oss-interop-gateway-light.svg" alt="interop-gateway" width="32%"></picture></a>
  <a href="https://github.com/heyitskundan/hl7-fhir-translator"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-hl7-fhir-translator-dark.svg"><img src="assets/oss-hl7-fhir-translator-light.svg" alt="hl7-fhir-translator" width="32%"></picture></a>
  <a href="https://github.com/heyitskundan/cda-fhir-translator"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/oss-cda-fhir-translator-dark.svg"><img src="assets/oss-cda-fhir-translator-light.svg" alt="cda-fhir-translator" width="32%"></picture></a>
</p>

> **MCP server:** `interop-gateway` ships an **MCP server** that lets an AI agent use a live system through 15 tools, with every call scope-checked and audit-logged first.

**Side projects (Python):**
- [whispr](https://github.com/heyitskundan/whispr): on-device push-to-talk speech-to-text. Hold a key, speak, and the text is pasted into whatever app you're in.
- [daylog](https://github.com/heyitskundan/daylog): a local-first activity tracker that turns your day into a timeline of tasks and screenshots, using on-device OCR and SQLite.

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
| **Languages** | ![TypeScript](https://img.shields.io/badge/TypeScript-0B0F14?style=flat-square&logo=typescript&logoColor=2DD4BF) ![JavaScript](https://img.shields.io/badge/JavaScript-0B0F14?style=flat-square&logo=javascript&logoColor=2DD4BF) ![Python](https://img.shields.io/badge/Python-0B0F14?style=flat-square&logo=python&logoColor=2DD4BF) ![SQL](https://img.shields.io/badge/SQL-0B0F14?style=flat-square) |
| **Front end** | ![React](https://img.shields.io/badge/React-0B0F14?style=flat-square&logo=react&logoColor=2DD4BF) ![Angular](https://img.shields.io/badge/Angular-0B0F14?style=flat-square&logo=angular&logoColor=2DD4BF) ![Chrome Extensions](https://img.shields.io/badge/Chrome_Extensions_(MV2%2FMV3)-0B0F14?style=flat-square&logo=googlechrome&logoColor=2DD4BF) ![Angular Material](https://img.shields.io/badge/Angular_Material-0B0F14?style=flat-square) ![Bootstrap](https://img.shields.io/badge/Bootstrap-0B0F14?style=flat-square&logo=bootstrap&logoColor=2DD4BF) |
| **Back end** | ![Node.js](https://img.shields.io/badge/Node.js-0B0F14?style=flat-square&logo=nodedotjs&logoColor=2DD4BF) ![REST APIs](https://img.shields.io/badge/REST_APIs-0B0F14?style=flat-square) ![BullMQ](https://img.shields.io/badge/BullMQ-0B0F14?style=flat-square) ![Multi-tenant SaaS](https://img.shields.io/badge/Multi--tenant_SaaS-0B0F14?style=flat-square) |
| **Data & infra** | ![AWS](https://img.shields.io/badge/AWS-0B0F14?style=flat-square&logo=amazonwebservices&logoColor=2DD4BF) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0B0F14?style=flat-square&logo=postgresql&logoColor=2DD4BF) ![MySQL](https://img.shields.io/badge/MySQL-0B0F14?style=flat-square&logo=mysql&logoColor=2DD4BF) ![Redis](https://img.shields.io/badge/Redis-0B0F14?style=flat-square&logo=redis&logoColor=2DD4BF) ![SQLite](https://img.shields.io/badge/SQLite-0B0F14?style=flat-square&logo=sqlite&logoColor=2DD4BF) |
| **Identity & security** | ![SAML SSO](https://img.shields.io/badge/SAML_SSO-0B0F14?style=flat-square) ![OAuth2](https://img.shields.io/badge/OAuth2-0B0F14?style=flat-square) ![JWT/JWKS](https://img.shields.io/badge/JWT_%2F_JWKS-0B0F14?style=flat-square) ![Okta](https://img.shields.io/badge/Okta-0B0F14?style=flat-square&logo=okta&logoColor=2DD4BF) ![SOC 2](https://img.shields.io/badge/SOC_2-0B0F14?style=flat-square) ![HIPAA](https://img.shields.io/badge/HIPAA-0B0F14?style=flat-square) |
| **Integrations** | ![Workday](https://img.shields.io/badge/Workday-0B0F14?style=flat-square) ![ServiceNow](https://img.shields.io/badge/ServiceNow-0B0F14?style=flat-square) ![SAP](https://img.shields.io/badge/SAP-0B0F14?style=flat-square&logo=sap&logoColor=2DD4BF) ![Epic](https://img.shields.io/badge/Epic_EHR-0B0F14?style=flat-square) ![FHIR R4](https://img.shields.io/badge/FHIR_R4-0B0F14?style=flat-square) ![HL7v2](https://img.shields.io/badge/HL7v2-0B0F14?style=flat-square) ![C-CDA](https://img.shields.io/badge/C--CDA-0B0F14?style=flat-square) |
| **AI** | ![MCP](https://img.shields.io/badge/MCP_servers-0B0F14?style=flat-square) ![ML model integration](https://img.shields.io/badge/ML_model_integration-0B0F14?style=flat-square) ![Whisper](https://img.shields.io/badge/faster--whisper-0B0F14?style=flat-square) ![Claude Code](https://img.shields.io/badge/Claude_Code-0B0F14?style=flat-square&logo=anthropic&logoColor=2DD4BF) |

<br>

---

<p align="center">
  <sub>Need someone who can own a product from the first commit to production? <a href="mailto:heyitskundan.dev@gmail.com"><b>Let's talk.</b></a></sub>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Kundan Sinha · Full-stack engineering lead · 8+ years · Open to Lead / Staff roles" src="assets/header-light.svg" width="100%">
</picture>

<p>
  <a href="https://heyitskundan.com"><img src="https://img.shields.io/badge/Portfolio-24292F?style=flat&logo=googlechrome&logoColor=white" alt="Portfolio"></a>
  <a href="https://linkedin.com/in/heyitskundan"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:heyitskundan.dev@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

## About

I'm a full-stack engineer with 8+ years of building products end to end: React and Angular front ends, Node.js and TypeScript back ends, AWS infrastructure, and the integrations that tie it all together. I've been the first engineer on a product and the tech lead of a 16-person team, often both at once.

- **Enterprise SaaS:** a Chrome-extension platform serving **150K+ users**, 30K of them at **Johns Hopkins**, across ServiceNow, SAP, Workday and more
- **Identity and data:** SAML/OAuth2 SSO for 5 enterprise customers, and an HR data sync that scaled to **120K records**
- **Healthcare:** a product taken from zero to **5 live hospitals in 2 years**, with an Epic integration and an ML screening pipeline that has seen **50,000+ patients**
- **Compliance:** owned the engineering side of **HIPAA** and **SOC 2** audits
- **AI tooling:** MCP servers, on-device speech-to-text and local-first apps

I'm open to Lead, Staff and senior full-stack roles, in any domain where the problems are interesting.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/impact-dark.svg">
  <img alt="150K+ users · 16-person team · 5 hospitals · 50K+ patients screened" src="assets/impact-light.svg" width="100%">
</picture>

## Selected work

### Ziplyne: in-app guidance for enterprise apps, as a browser extension

Ziplyne puts step-by-step guides on top of other companies' enterprise apps. The hard part is knowing exactly which screen a user is on, when apps like SAP and ServiceNow change their URLs all the time and bury content in iframes and shadow DOM. I led the team that built it and wrote the core engines.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/ziplyne-architecture-dark.svg">
  <img alt="Ziplyne architecture: the Chrome extension's content script runs URL+ page identification and the selector engine, then shows the guide overlay. The extension background syncs guides with a Node.js API on AWS, signs users in through SAML or OAuth2 identity providers, and BullMQ workers sync Workday users into the database." src="assets/ziplyne-architecture-light.svg" width="100%">
</picture>

- **URL+ page identification:** per-platform adapters resolve volatile URLs to one canonical page, so the right guide shows on the right screen for **150K+ users** (30K+ at Johns Hopkins)
- **Selector engine:** finds guide targets inside iframes and shadow DOM across six enterprise platforms
- **Workday HR sync:** RaaS report ingestion, user upsert by email and group reconciliation as a BullMQ background job, from **50K to 120K** records
- **SSO for 5 enterprise customers:** SAML (Okta, IBM Security Verify, Shibboleth) and Coupa OAuth2, with automatic user and role setup on first login
- **SOC 2:** owned the AWS database controls, covering encryption at rest and in transit, and backups
- **Team:** tech lead of 16 people (5 engineers, 4 QA, 3 designers, 2 customer success, 1 PM)

<sub>Simplified view of the architecture.</sub>

### Visilant: a healthcare product from zero to 5 hospitals

I was the only full-stack engineer on a team of 5, owning the React front end and the Node.js back end. Hospital customers needed results to land straight in the patient's Epic chart.

```mermaid
flowchart LR
  A["Visilant app<br/>React + Node.js"] -->|"JWT client assertion<br/>RS384 / JWKS"| B("Epic auth server")
  B -->|"access token"| A
  A -->|"FHIR R4 read / write"| C[("Epic FHIR API")]
  C --- D["Patient · Observation<br/>DiagnosticReport<br/>ImagingStudy · Media<br/>ServiceRequest"]
  A -->|"eye images"| M["Production ML model"]
  M -->|"suggested diagnosis"| A
```

- **Epic integration:** a SMART-on-FHIR backend client covering six FHIR resources, live in **5 hospitals within 2 years**
- **Seeker screening pipeline:** sends captured eye images to a production ML model and shows the suggested diagnosis to clinicians. **50,000+ patients** screened with partners including Aravind Eye Hospital and Dr. Shroff's Charity Eye Hospital
- **Multi-tenant migration:** tenant-scoped request context, JWT tenant checks and tenant-scoped caching
- **HIPAA audit passed:** owned the technical controls, audit-trail tables and ABHA health-ID handling

## Open source and side projects

- **[interop-gateway](https://github.com/heyitskundan/interop-gateway)**, **[hl7-fhir-translator](https://github.com/heyitskundan/hl7-fhir-translator)** and **[cda-fhir-translator](https://github.com/heyitskundan/cda-fhir-translator)**: TypeScript libraries on npm that convert HL7v2 and C-CDA to FHIR R4 and back without losing fields
- **[whispr](https://github.com/heyitskundan/whispr)**: on-device push-to-talk speech-to-text in Python
- **[daylog](https://github.com/heyitskundan/daylog)**: a local-first activity tracker with on-device OCR

All of them are pinned below.

`interop-gateway` also ships an **MCP server**, so an AI agent can work with a live system through 15 tools, with every call scope-checked and audit-logged first.

## Experience

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/timeline-dark.svg">
  <img alt="Intelehealth 2018 to 2020 · Ziplyne 2020 to 2026 · Visilant 2021 to 2026 · MSc Cardiff 2021 to 2023" src="assets/timeline-light.svg" width="100%">
</picture>

<details>
<summary><b>Ziplyne</b> · Software Engineering Lead · Oct 2020 to Jul 2026 · remote</summary>
<br>

- Joined as a full-stack engineer and was promoted to lead in Jan 2022
- Tech lead of 16 people; owned technical direction and architecture
- Built URL+, the selector engine, the Workday HR sync and SSO for 5 enterprise customers; owned the SOC 2 database controls
</details>

<details>
<summary><b>Visilant</b> · Founding Engineer · Aug 2021 to Jun 2026 · remote</summary>
<br>

- Only full-stack engineer on a team of 5; owned the backend and the React front end
- Took the product from scratch to 5 hospital deployments in 2 years
- Built the Epic integration, the Seeker ML pipeline, the multi-tenant migration and the HIPAA technical controls
</details>

<details>
<summary><b>Intelehealth</b> · Full Stack Developer · Jul 2018 to Sep 2020 · Thane</summary>
<br>

- Built the Angular front end of a telehealth doctor web app on OpenMRS, from scratch
- Built the Node.js image upload and retrieval API
</details>

<details>
<summary><b>Cardiff University</b> · MSc Advanced Computer Science · 2021 to 2023</summary>
<br>

- Thesis: *Creating a User Interface for Virtual Assistants*, a COVID-advisory chatbot on IBM Watson Assistant and Cloudant
</details>

## Tech stack

**Languages**<br>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" title="TypeScript" alt="TypeScript" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" title="Python" alt="Python" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" title="HTML5" alt="HTML5" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" title="CSS3" alt="CSS3" width="28" height="28">

**Front end**<br>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" title="React" alt="React" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/angular/angular-original.svg" title="Angular" alt="Angular" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/chrome/chrome-original.svg" title="Chrome Extensions (MV2 / MV3)" alt="Chrome Extensions" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original.svg" title="Bootstrap" alt="Bootstrap" width="28" height="28">

**Back end and data**<br>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg" title="Node.js" alt="Node.js" width="28" height="28">&nbsp;
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/amazonwebservices/amazonwebservices-plain.svg"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/amazonwebservices/amazonwebservices-original.svg" title="AWS" alt="AWS" width="28" height="28"></picture>&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" title="PostgreSQL" alt="PostgreSQL" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original.svg" title="MySQL" alt="MySQL" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original.svg" title="Redis" alt="Redis" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlite/sqlite-original.svg" title="SQLite" alt="SQLite" width="28" height="28">

**Identity, enterprise and AI**<br>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/okta/okta-original.svg" title="Okta (SAML SSO)" alt="Okta" width="28" height="28">&nbsp;
<img src="https://cdn.simpleicons.org/sap" title="SAP" alt="SAP" width="28" height="28">&nbsp;
<img src="https://cdn.simpleicons.org/openid" title="OAuth2 / OpenID" alt="OAuth2" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/claude/claude-original.svg" title="Claude Code / MCP" alt="Claude" width="28" height="28">&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" title="Git" alt="Git" width="28" height="28">

**Also:** SAML SSO · OAuth2 · JWT/JWKS · BullMQ · Workday · ServiceNow · Coupa · Microsoft Dynamics · FHIR R4 · HL7v2 · C-CDA · SMART-on-FHIR · Epic · OpenMRS · SOC 2 · HIPAA

---

<p align="center">Need someone who can own a product from the first commit to production? <a href="mailto:heyitskundan.dev@gmail.com"><b>Let's talk.</b></a></p>

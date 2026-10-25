# Casevia — AI-Assisted Legal Case File Platform

**An interactive Next.js prototype demonstrating the full journey from a legal concern to a lawyer connection.**

Casevia helps people organize the facts and evidence of a legal issue, prepare a structured case file, and request review from a lawyer. This demo starts with the **Netherlands** and illustrates the client, lawyer, and admin experiences using fictional data.

> **Prototype only:** No real AI, legal advice, lawyer outreach, secure document storage, or production authentication is implemented.

## Features

### Client workspace
- View cases and their statuses in a dashboard
- Start a case by selecting country and legal area
- Complete a guided, multi-step questionnaire
- Attach evidence **filenames** (files are not uploaded)
- Review a structured case summary
- Export an HTML case file, printable to PDF using the browser
- Select a lawyer and explicitly consent before simulated sharing
- Follow request status through lawyer acceptance or decline

### Lawyer workspace
- Review simulated incoming case requests
- Accept or decline requests
- View accepted cases in a dedicated workspace

### Admin workspace
- Overview of case activity and user roles
- Preview lawyer verification and audit activity

### Experience
- Responsive layout for desktop and mobile
- English/Dutch interface preview
- Workspace role switcher for demonstrations
- Browser `localStorage` for demo case and status persistence

## Tech stack

- **Next.js 15** (App Router)
- **React 19**
- **TypeScript**
- **CSS**
- **Lucide React** icons

No API keys or external services are needed for the demo.

## Getting started

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

To check a production build locally:

```bash
npm run build
npm start
```

## Demo walkthrough

1. Enter the **Client** workspace and choose **Create a case**.
2. Provide case details, answer guided questions, and add evidence filenames.
3. Review and create the case file.
4. Select a lawyer and explicitly approve simulated sharing.
5. Switch to the **Lawyer** workspace to accept or decline the request.
6. Switch to **Admin** to explore the administrative overview.

All identities, cases, lawyers, and interactions are fictional. The role switcher is for UI demonstration only and does not enforce permissions.

## AI safety approach for a production release

The current demo uses **fixed questions and simulated workflows**, not a live language model. A production implementation should:

1. Use a curated, legally reviewed, **versioned Dutch legal source collection**.
2. Ground any legal-information response in retrieved source passages and provide verifiable citations.
3. Require the system to **abstain** when sources do not support an answer; never fabricate laws, citations, or success probabilities.
4. Separate factual case-file preparation from legal advice and require expert review of jurisdiction-specific interview flows.
5. Validate generated structured data and retain traceability to the user's actual statements and evidence.
6. Keep LLM providers swappable without relaxing the same safety and evaluation requirements.

These controls reduce risk but cannot guarantee that a language model will never hallucinate; testing and human oversight remain essential.

## Privacy and security requirements before production

- Authenticated client, lawyer, and admin accounts with **server-enforced** authorization and access-control tests
- PostgreSQL database and audited API endpoints
- Private, encrypted document storage with signed access and retention/deletion policies
- Explicit, recorded consent before sharing any case details
- Controlled contact exchange after lawyer acceptance
- Tamper-resistant audit logs and GDPR-aware data subject workflows
- Transactional email, real PDF generation, and accessibility/security testing

**Do not enter real sensitive legal information into this demo.** Data is stored in browser `localStorage`, and the current interface is not a GDPR-compliant production service.

## Suggested roadmap

1. Confirm the Netherlands-first legal area and legally reviewed questions.
2. Implement authentication, database schema, access rules, and secure uploads.
3. Build the case-file and lawyer-request workflow with recorded consent.
4. Add source-grounded AI assistance, Dutch localization, and provider abstraction.
5. Integrate email, PDF generation, audit logging, and automated tests.
6. Perform privacy/security review and deploy staging before production.

## License

Prototype prepared for demonstration. Confirm ownership and licensing terms before redistribution or commercial use.

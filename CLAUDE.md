# CLAUDE.md — Work Showcase Page

## Before You Start

Read `/mnt/skills/public/frontend-design/SKILL.md` before writing any code.

---

## What This Is

A single-page HTML file that Paula Hershko can share directly with a specific person — the Deputy CEO of DataMap, a Geospatial/Engineering data company — to show three automation projects she has built.

This is not a portfolio or a freelancer website. It is a professional work document — the digital equivalent of handing someone a well-prepared case study. The tone is: "here is what I built and how it worked," not "hire me."

---

## Delivery Format

Single `index.html` file with a sibling `screenshots/` folder. No build step, no framework, no server required. The file must open correctly when double-clicked locally. All fonts and styles load from CDN.

---

## Design Direction

Clean, minimal, document-like. Think of a well-formatted internal report or a consulting brief. The quality comes from clear typography, generous spacing, and structured content — not from visual effects.

No dark theme. No gradients. No decorative elements. The page should feel like it was made by someone who knew exactly what they wanted to say.

One accent color is enough. Typography should feel slightly editorial — not like a developer's personal site.

The page has no navigation bar. It is a single scroll from top to bottom.

---

## Page Sections (in order)

### 1. Header

Paula's name, her role title, and a one-line description of what she does. Below that, two plain links: her email and her LinkedIn profile.

Email: hershko.paula@gmail.com
LinkedIn: https://www.linkedin.com/in/paula-h-75512621a/

Keep this section short. It introduces, it does not sell.

### 2. Projects

A section heading followed by three project cards stacked vertically. Each card contains:

- A project number and a small descriptive tag (right-aligned)
- Project title and a one-line subtitle
- A 2–3 sentence summary of what was built and why
- A screenshot image, if a file exists at the expected path (see Screenshot Handling below)
- An expandable phases section — clicking "Phases" reveals the phase breakdown inline; only one card's phases can be open at a time
- A row of tool/stack labels
- A single outcome line at the bottom of the card, clearly distinguished from the rest

### 3. Tools (one line)

A single brief line listing the tools Paula works with. Not a section — just a quiet reference between the projects and the footer.

### 4. Footer

A closing line, the email and LinkedIn links again, and a copyright line. Centered, small.

---

## Project Content

Use the following content verbatim. Do not paraphrase or summarize.

---

### Project 01

Number: 01
Title: CRM × Billing Automation
Subtitle: Airtable + SUMIT — 3-Phase Revenue Workflow
Tag: Human-in-the-loop
Screenshot file: screenshots/project-01.png

Summary:
Built a multi-phase integration between an Airtable CRM and SUMIT (Israeli billing system) to fully automate the customer lifecycle from lead to invoice — eliminating manual data entry and billing delays.

Phase 1 — Sync:
Established real-time data synchronization between Airtable and SUMIT. Any record change in either system propagated instantly to the other, maintaining a single source of truth.

Phase 2 — Auto-Create Customer on Status Change:
Triggered automatic customer creation in SUMIT when a lead reached "Active Client" status in Airtable. Eliminated a manual step.

Phase 3 — Automated Billing with Human-in-the-Loop:
Built a full billing workflow using code nodes. Invoices are generated and queued automatically, but require explicit owner approval before dispatch — preserving business control over financial outputs.

Stack: n8n, Airtable, SUMIT API, Webhooks

Outcome: End-to-end billing automation with human approval gate — zero manual data entry, full audit trail.

---

### Project 02

Number: 02
Title: Nesah Tabo → Sales Agreement
Subtitle: PDF Intelligence Pipeline — Structured Document Extraction
Tag: PDF → Document
Screenshot file: screenshots/project-02.png

Summary:
Built a pipeline that ingests an Israeli property registry document (Nesah Tabo PDF), extracts structured data fields using AI, and generates a formatted draft sales agreement — turning a manual task into a 20-30 second automated output.

Phase 1 — n8n POC:
Prototyped the extraction and document generation workflow in n8n, validating the data model and output format with a real document before committing to code.

Phase 2 — Converted to Code:
Migrated the validated logic into a Node.js application using Claude Code, giving it production reliability and full control over edge cases.

Phase 3 — Client-Facing UI:
Added a React frontend — drag-and-drop PDF upload, extraction preview, and one-click .docx download. The tool is now fully usable by a non-technical client with no manual steps.

Stack: Claude Code, Node.js, React, Vercel, OpenAI, docxtemplater, n8n (POC)

Outcome: Complex legal PDF → structured extraction → sales agreement draft document output. Live on Vercel.

---

### Project 03

Number: 03
Title: Timeframe
Subtitle: AI-Assisted Time Intelligence on Google Calendar
Tag: Live Tool
Screenshot file: screenshots/project-03.png

Summary:
Designed and built Timeframe: a system that uses Google Calendar as a structured data source, processes time allocation across projects and phases and surfaces it through a clear interface — enabling personal awareness and client-shareable phase-based reporting.

Concept — Calendar as a Data Layer:
Recognized that Google Calendar, when used with consistent event naming conventions, becomes a rich structured dataset. Designed an event taxonomy (project / stage / type) that feeds downstream analytics.

Processing — AI-Assisted Classification:
Built logic that parses calendar events, classifies them by project and phase using AI, and computes time distribution — surfacing where hours actually go.

Output — Reporting Interface:
Built a dashboard view: per-project summaries, phase breakdowns and exportable client reports — turning raw calendar data into professional deliverables.

Stack: Google Calendar API, Claude Code

Outcome: Raw calendar data → structured time intelligence dashboard with client-shareable phase reports.

---

### Project 04

Number: 04
Title: Insurance PDF → E-Signature Pipeline
Subtitle: Automated Signature Placement on Hebrew Insurance Forms
Tag: Python Pipeline
Screenshot file: screenshots/project-04.png
Summary:
Built a Python pipeline as a POC for an insurance client that automatically locates signature fields in Hebrew PDF forms, injects EasyDoc-compatible placeholders and triggers the e-signature flow via API — replacing a fully manual process.
Module 1 — PDF Processing:
Used PyMuPDF to scan the insurance form, locate every signature anchor (the Hebrew text marking where signatures are required), and inject an invisible placeholder at each location. The modified PDF preserves the original layout exactly.
Module 2 — API Integration:
Authenticated with the EasyDoc API, created a signing form, assigned the recipient and uploaded the modified PDF. EasyDoc detects the placeholders, converts them into interactive signature fields, and returns a unique signing URL sent directly to the signer.
Stack: Python, PyMuPDF, EasyDoc API, watchdog
Outcome: End-to-end pipeline — Hebrew insurance PDF in, signing link out. Zero manual steps, zero visible artifacts in the final document.

---

## Screenshot Handling

Create a `screenshots/` folder next to `index.html`. Expected filenames are listed in each project above.

If a screenshot file is missing or fails to load, hide the image container silently — no broken image icon should appear.

---

## Tools Line Content

n8n · Make · Claude Code · React · Node.js · Airtable · Vercel · Google APIs 

---

## Technical Requirements

- Single `index.html` file, everything inline (styles in a `<style>` block, script at the bottom)
- Fonts and Tailwind loaded from CDN only
- Vanilla JavaScript for accordion interaction — no JS framework
- Page title: `Paula Hershko — AI & Automation`
- Must include charset and viewport meta tags
- Must render correctly at desktop (1200px) and mobile (375px) widths
- The file must open correctly by double-clicking, without a local server

---

## Accordion Behavior

Each project card has a "Phases" toggle. Clicking it expands the phase breakdown for that card. If another card's phases are already open, they close first. Clicking the same toggle again closes it.

---

## What Not to Include

- No navigation bar
- No hero image or banner
- No animations or scroll effects
- No dark mode
- No calls to action beyond the contact links
- No branding or business pitch language
- No lorem ipsum or placeholder text of any kind

---

## Pre-Send Checklist

Before considering the file done:

- Phases accordion works correctly — opens, closes, only one open at a time
- Missing screenshots are hidden cleanly
- All three outcome lines are visible without expanding phases
- Email link uses mailto:
- LinkedIn URL is correct: https://www.linkedin.com/in/paula-h-75512621a/
- "Nesah Tabo" is spelled correctly everywhere it appears
- No placeholder text anywhere
- File opens by double-clicking without a server

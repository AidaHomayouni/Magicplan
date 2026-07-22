# Falkenweg Plan Handoff

**magicplan Product Design Challenge**

**Author:** Aida Homayouni
**Estimated reading time:** ~6 minutes

---

## Live Prototype

- **Prototype:** [aidahomayouni.github.io/Magicplan](https://aidahomayouni.github.io/Magicplan/)
- **GitHub Repository:** [github.com/AidaHomayouni/Magicplan](https://github.com/AidaHomayouni/Magicplan)

---

## People in the Story

**In the scenario:**

- **Marek** — Crew lead, Berlin site. Discovers the mismatch and captures evidence.
- **Ines** — Remote expert, Munich. Reviews the evidence and publishes the corrected plan.

**Reviewing this challenge:**

- **Konstantin** — Product Design, my point of contact for this challenge.
- **Bernd** — CPO.
- **Finn** — Product Owner.
- **Loïc** — Engineering.

---

## Overview

This challenge initially appears to be about reporting a floor plan issue.

After reviewing the scenario, personas, timeline, and supporting materials, I concluded that the real challenge is different: the goal is not simply to report an issue, but to help a remote expert understand enough to confidently correct the floor plan before leaving at **15:00** — without requiring a phone or video call.

This insight shaped every design decision. Instead of building another reporting form, I designed a structured evidence handoff between the construction site and the remote expert.

---

## The Solution

The prototype follows the complete journey from discovering a mismatch on-site to publishing a corrected floor plan, across three roles:

- **Marek** — captures structured evidence on-site.
- **Office** — validates priority and assigns the ticket.
- **Ines** — reviews the evidence, updates the plan, and publishes the corrected version.

Rather than exchanging unstructured messages, the workflow focuses on delivering exactly the information needed to make a confident decision.

This case study itself follows a similar handoff logic: Konstantin briefed me on the challenge, and Bernd, Finn, and Loïc are reviewing this submission from their respective CPO, Product, and Engineering perspectives — so the writeup below speaks to all three.

---

## Key Design Decisions

### Separate Responsibilities

Each user has a different responsibility:

- Marek captures reality.
- The office validates urgency.
- Ines corrects the official floor plan.

Separating these responsibilities reduces cognitive load, avoids accidental edits, and reflects how these teams already work.

### Structured Evidence Instead of Communication

The workflow is based on one simple principle:

> One wall. One measurement. One reference photo.

Every piece of evidence belongs to a specific location, making the information easy to understand without additional clarification.

### Design Around Time

Time is one of the most important constraints. Since Ines leaves at **15:00**, the interface always communicates:

- Remaining time
- Current ticket status
- Current owner
- Next action

The goal is to keep the workflow moving without unnecessary delays.

### Offline First

Poor connectivity is part of the working environment. Reports are saved locally before uploading, so users receive immediate confirmation that their work is safe, while synchronization happens automatically once a connection is available.

This allows Marek to return to his crew immediately instead of waiting for the network.

---

## What I Deliberately Left Out

To keep the solution focused, I intentionally excluded features that do not improve this workflow:

- Video calls
- Chat
- AI-generated corrections
- AR or LiDAR scanning
- Authentication
- Project management features
- Cost estimation
- Permit management

While these features may exist in a larger product, they do not help solve the problem presented in this challenge.

---

## One Idea That Didn't Survive

I initially explored using a video walkthrough. Although it seemed useful, it introduced several problems:

- Large uploads over weak connections
- Longer review times
- Difficult navigation
- Unstructured information

Replacing video with structured evidence made the review process faster, clearer, and more reliable.

---

## Development Process

My process focused on understanding the problem before designing the interface:

1. Reviewed the challenge materials, personas, timeline, and research insights.
2. Defined the core problem and success criteria.
3. Mapped the complete workflow from discovery to resolution.
4. Explored multiple concepts before selecting the structured evidence approach.
5. Designed role-specific interfaces for Marek, the Office, and Ines.
6. Built an interactive prototype to validate the workflow.

---

## AI Usage

AI supported my workflow during the design process. I used AI to:

- Review UX flows
- Challenge assumptions
- Explore alternative solutions
- Improve microcopy
- Identify edge cases
- Review accessibility
- Speed up implementation

All product decisions, prioritisation, interaction design, and final solutions were made by me.

---

## What I Would Test

Before shipping, I would validate:

- Can Marek complete a report in under two minutes?
- Can Ines resolve the issue without additional clarification?
- Does structured evidence reduce follow-up questions?
- Does offline synchronization work reliably?
- Do users understand the difference between requested and confirmed P1 priority?

Success would be measured through:

- Report completion time
- Time to resolution
- Clarification requests
- First-time resolution rate
- User confidence

---

## Tech Stack

- React
- TypeScript
- Tailwind CSS
- Framer Motion
- Lucide Icons
- Local React State
- Mock Data

---

## Run Locally

```bash
npm install
npm run dev
```

---

## Final Reflection

This challenge is not about reporting a floor plan issue. It is about reducing uncertainty between people working in different environments under time pressure.

Marek needs speed. Ines needs clarity. The office needs visibility.

The product succeeds when the right evidence reaches the right expert early enough for a confident decision to be made before time runs out.

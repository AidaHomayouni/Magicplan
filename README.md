# Falkenweg Plan Handoff

**magicplan Product Design Challenge**

**Author:** Aida Homayouni

🌐 **Live Prototype:** https://aidahomayouni.github.io/Magicplan/

💻 **GitHub Repository:** https://github.com/AidaHomayouni/Magicplan

⏱ **Estimated reading time:** 8 minutes

---

# Overview

At first glance, this challenge looks like a floor plan reporting problem.

After reviewing the ticket, voice note, personas, and timeline, I realised that the real challenge is different.

The goal is not to report an issue.

The goal is to help a remote expert understand enough to confidently update the floor plan before leaving at **15:00**, despite poor connectivity and time pressure.

This insight shaped every design decision.

Instead of designing another issue reporting tool, I created an **Offline-First Structured Evidence Handoff** that helps the right information reach the right person at the right time.

---

# Understanding the Challenge

The scenario connects two completely different working environments.

### Construction Site

- Weak cellular connection
- Dusty environment
- Workers wearing gloves
- Limited time
- Crew waiting
- Owner on site

### Technical Office

- Desktop environment
- High information density
- Precise floor plan editing
- Need for reliable evidence
- Fixed deadline

The challenge is to bridge these two environments without relying on phone calls or long conversations.

---

# Solution

The solution focuses on structured evidence instead of communication.

Every report contains:

- Selected wall
- Verified measurement
- Difference from the original plan
- Reference photo
- Priority
- Timestamp

Instead of asking users to explain the problem, the workflow provides everything needed to make a confident decision.

---

# Workflow

```text
Issue Detected
      │
      ▼
Marek Captures Evidence
      │
      ▼
Offline Queue
      │
      ▼
Office Review
      │
      ▼
Assigned to Ines
      │
      ▼
Review Evidence
      │
      ▼
Update Floor Plan
      │
      ▼
Publish
      │
      ▼
Site Verification
      │
      ├───────────────┐
      ▼               ▼
Verified       Still Incorrect
      │               │
      ▼               ▼
Close Ticket   Reopen Ticket
                      │
                      ▼
             Specialist Review
```

---

# Stakeholders

Although only a few users interact directly with the interface, several stakeholders influenced the design.

| Stakeholder | Role |
|-------------|------|
| 👷 Marek | Captures structured evidence and verifies the updated plan on site. |
| 🏢 Office | Confirms ticket priority, assigns experts, and coordinates escalations. |
| 📐 Ines | Reviews evidence, updates the floor plan, and requests additional information when necessary. |
| 👨‍🔧 Technical Specialist | Reviews complex cases that require additional expertise. |
| 🎨 Konstantin | Represents usability, accessibility, and workflow clarity. |
| ⚙️ Loïc | Represents technical feasibility, offline synchronization, and reliability. |
| 📊 Finn | Represents business goals, prioritisation, and measurable product outcomes. |
| 🎯 Bernd | Represents long-term product strategy and operational efficiency. |

---

# Key Design Decisions

### Separate Responsibilities

Every role has one clear responsibility.

- Marek captures reality.
- Office coordinates the workflow.
- Ines updates the official floor plan.

This reduces cognitive load and prevents accidental changes.

### Structured Evidence

Instead of free-form communication, every report is built around one wall, one verified measurement, and one reference photo.

This reduces ambiguity and speeds up expert review.

### Offline First

Weak connectivity is expected rather than treated as an exception.

Reports are saved locally before uploading, allowing Marek to continue working while synchronization happens in the background.

### Time Awareness

Time is one of the most important constraints.

The interface always communicates:

- Remaining time
- Current ticket owner
- Ticket status
- Next action

This helps users prioritise instead of simply displaying a countdown.

---

# Validation & Escalation

Publishing a corrected floor plan does not automatically complete the workflow.

The final validation happens on site.

After receiving the updated plan, Marek verifies whether it matches reality.

Possible outcomes include:

- ✅ The correction is verified and the ticket is closed.
- 📷 Additional evidence is required, allowing Ines to request one specific measurement or photo.
- 🔄 The correction is still incorrect, so the existing ticket is reopened and reassigned to the same expert or another specialist while preserving the complete history.

This creates a resilient workflow instead of assuming every issue is solved on the first attempt.

---

# Edge Cases

The prototype considers several real-world situations, including:

- Weak connectivity
- Offline reporting
- Interrupted uploads
- Missing or unclear evidence
- Ticket reopening
- Specialist review
- Expert unavailable
- Shift changes

---

# What I Left Out

To keep the solution focused, I intentionally excluded:

- Chat
- Video calls
- AI-generated corrections
- AR / LiDAR scanning
- Authentication
- Project management
- Cost estimation
- Permit management

These features increase complexity without improving the core workflow.

---

# One Idea That Didn't Survive

Initially, I explored using video walkthroughs.

Although they seemed useful, they created larger uploads, slower reviews, and unstructured information.

Replacing video with structured evidence resulted in a faster, simpler, and more reliable workflow.

---

# Development Process

My process focused on understanding the problem before designing the interface.

1. Reviewed the challenge material and identified the operational constraints.
2. Defined the success criteria.
3. Mapped the complete workflow.
4. Explored multiple concepts.
5. Designed role-specific interfaces.
6. Built an interactive prototype.
7. Refined the experience by considering failure paths, validation, and ticket reopening.

---

# AI Usage

AI supported my workflow by helping me review UX flows, challenge assumptions, explore alternative solutions, improve microcopy, identify edge cases, and speed up implementation.

All product decisions, prioritisation, interaction design, and final solutions were made by me.

---

# Success Metrics

If this solution were implemented, I would measure:

- Report completion time
- Time to expert understanding
- Time to resolution
- First-time resolution rate
- Ticket reopen rate
- Clarification requests
- Phone calls avoided
- User confidence

---

# Tech Stack

- React
- TypeScript
- Tailwind CSS
- Framer Motion
- Lucide Icons
- Local React State
- Mock Data

---

# Run Locally

```bash
npm install
npm run dev
```

---

# Final Reflection

This challenge is not simply about reporting a floor plan issue.

It is about reducing uncertainty between people working in different environments under significant time pressure.

By designing an offline-first workflow, structuring evidence, defining clear responsibilities, and supporting validation, reassignment, and ticket reopening, I aimed to create a solution that reflects how construction teams actually work.

The workflow is only complete when the updated plan has been verified on site and everyone can move forward with confidence.

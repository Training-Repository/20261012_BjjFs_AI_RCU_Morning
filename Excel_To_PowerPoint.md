# AI at Work – Participant Workbook

**The 9-Step Copilot Flow — from a raw file to a leadership-ready deck**

**Course:** AI Enablement — Copilot for Reviews & Decks
**Tool:** Microsoft Copilot (+ PowerPoint agent)
**Companion data:** *your file for today's session.*

> **The one thing that changes is the file.**
> The same nine steps take *any* document — a report, a register, a tracker, a dataset — and turn it into an **analysis**, a **document**, and a **leadership deck**. Learn the flow once; run it on your own file the same afternoon.

---

## What you'll be able to do after this

Take any work file, turn it into a sound analysis, a Word document, and a leadership deck — using a repeatable 9-step method you can run on your own data the same afternoon.

## The method at a glance

The flow lives in **three separate chats** on purpose. Keep them separate — it's what keeps the output clean.

| | Chat | Steps | Why separate |
|---|---|---|---|
| **A** | Discovery | 1–4 | Exploring is messy. Let it be messy here. |
| **B** | Execution | 5–8 | Run the real work in a clean context. |
| **C** | PowerPoint agent | 9 | Deck generation is its own tool. |

Two moments you **adapt to the room** — **Step 3** and **Step 7** — because the same file makes a different meeting depending on whose desk it lands on.

---

# CHAT A — Discovery & Framing

> You never produce the final deliverable here. This chat is for understanding and deciding.

## Step 1 — Read & validate comprehension

**Do:** Attach the file. Ask Copilot to tell you what's in it — *before* you trust any analysis.

**Type this:**
> Read the attached file. Tell me exactly what it contains — the columns or sections, the time periods covered, the key categories or entities, and any totals or status fields. List anything that looks incomplete, ambiguous, or inconsistent.

**Check:** Did Copilot pick up every column/section that matters, all periods, and the key fields your review depends on? If it missed one, it will mis-analyse later. Fix understanding now.

**Why this matters:** Everything downstream inherits this reading. Ten seconds of validation saves a wrong analysis.

---

## Step 2 — Diverge: what analysis is possible?

**Do:** Ask for the full menu of analyses — to cross-check your own idea *and* find ones you hadn't thought of.

**Type this:**
> Based on this file, list every meaningful analysis or review someone in my role could run. For each, give a one-line description of what it would reveal. Include the obvious checks *and* any less-obvious ones you can see in the data.

**Check:** Does the list include the analysis you already had in mind? Good — that's validation. What's on the list that you *didn't* think of? That's the value.

> **Note:** if your file is a document rather than a table, "analysis" becomes *review or extraction* — a completeness check, a status review, an obligation/clause pull, or a set of clarification questions.

---

## Step 3 — Prioritise for the room  ⟵ *adapt to your audience*

**Do:** Narrow to the 5 highest-impact analyses **for the specific person you're meeting.**

**Type this** (swap in your audience):
> From that list, pick the top 5 highest-impact analyses for a review meeting with **[the specific person I'm meeting]**. Prioritise what drives their decision — approve / proceed / escalate / clarify. Explain in one line why each earns a place.

**Adapt — same file, different top 5.** Ask yourself what kind of person you're walking in to:

| If they're… | They mostly want… |
|---|---|
| **The decision-maker / approver** | The headline and the ask — the call they have to make |
| **The numbers person** | Costs, utilisation, caps, variance |
| **The controls person** | Gaps, breaches, exposure, what could go wrong |
| **The delivery person** | Timelines, throughput, capacity, exceptions |
| **The evidence person** | Completeness, defensibility, what backs each claim |

**Your note — who am I meeting, and what do they care about?**
> _______________________________________________

---

## Step 4 — Meta-prompt: build the prompt for your chosen analysis

**Do:** Pick ONE analysis. Ask Copilot to *write the prompt* for it (this is the meta-prompt move).

**Type this:**
> Act as a prompt engineer. I want to run this analysis on my file: **"[name your chosen analysis]."** Write me a precise Copilot prompt that will produce a reviewer's note with a flags table and a clear recommendation. Use a **Role–Task–Context–Format–Tone (RTCFT)** structure.

**Result:** Copilot hands you a polished prompt. Copy it. **You're done with Chat A.**

---

# CHAT B — Execution & Productising

> Open a **new chat.** Clean context = clean output.

## Step 5 — Run the analysis

**Do:** Paste the prompt Copilot built in Step 4. Attach the file again.

**Check the output catches what you'd catch by hand.** Read it as the reviewer, not the operator: are the flags the ones *you* would have raised? Is anything obvious missing — an approaching deadline, a threshold breach, an adverse trend, a gap?

**If it misses one:** follow up plainly — *"You didn't flag [the specific thing] — check again against [the rule / threshold / expectation]."*

---

## Step 6 — Create the document

**Do:** Turn the analysis into a Word document — **Export to Word** (or **Edit in Pages** to collaborate).

**Polish prompt (optional):**
> Reformat this as a one-page reviewer's note: heading, a flags table, and a recommendation line. Formal tone.

**You now hold deliverable #1 — the review document.**

---

## Step 7 — Plan the deck for your time slot  ⟵ *adapt to your audience*

**Do:** Ask how to fit this into your actual meeting length and audience.

**Type this** (swap both):
> I have **[X minutes]** with **[the person I'm meeting]** to walk through this review. How many slides should I use, and what should each cover? Keep it decision-focused.

**Adapt:** 5 minutes → 3 slides, headline + ask. 15 minutes → 5–6 slides with the flags table. A working session → add an appendix slide.

---

## Step 8 — Generate the slide-by-slide outline

**Do:** Ask for the full outline with suggested visuals.

**Type this:**
> Generate a slide-by-slide outline based on that plan. For each slide: title, 3–4 bullet points, and a suggested visual (chart, table, or icon). Base it only on the analysis we produced — don't invent figures.

**You now hold deliverable #2 — the slide outline.**

---

# CHAT C — PowerPoint Agent

## Step 9 — Build the deck

**Do:** Paste the Step-8 outline into the **PowerPoint agent** (or use **Copilot inside PowerPoint**) to generate the deck. Then review every figure against your Step-6 document before you present.

**You now hold deliverable #3 — the presentation.**

---

# Applying the flow to documents (not just spreadsheets)

Most work files are Word or PDF, not Excel. The flow is the same — only **Step 2 changes meaning:** "analysis" becomes "review / extraction."

| Document type | Step 2 becomes… |
|---|---|
| Concept note / proposal | Completeness check + gaps + clarification questions |
| Status / progress report | Milestone-status review + risk flags |
| Request for approval / release | Trigger-by-trigger check + release recommendation |
| Contract / policy / circular | Obligation & clause extraction + compliance flags |
| Meeting or field notes | Structure into a clean record + action items |

Everything else — validate, prioritise for the room, meta-prompt, run in a clean chat, export to Word, plan and build the deck — is identical.

---

# Your turn — run the 9 steps on your own file

Fill this in during the session, then reuse it at your desk.

| Step | Your entry |
|---|---|
| 1. File I'm reading | ____________________ |
| 2. Analyses/reviews possible | ____________________ |
| 3. Who I'm meeting + their priority | ____________________ |
| 3. My top 5 → the one I pick | ____________________ |
| 4. Meta-prompt gave me this prompt | ____________________ |
| 5. Key findings from the run | ____________________ |
| 6. Document created? (Y/N) | ____________________ |
| 7. Time slot + slide count | ____________________ |
| 8. Outline ready? (Y/N) | ____________________ |
| 9. Deck built + figures re-checked? | ____________________ |

---

## The one rule that never changes

Copilot **reads, analyses, drafts, and builds.** You **validate every figure and own every decision** — approvals, escalations, disbursements, and what goes in front of leadership stay yours.

---

*AI at Work – Participant Workbook | Swap only the companion file per session; the 9-step method stays constant.*

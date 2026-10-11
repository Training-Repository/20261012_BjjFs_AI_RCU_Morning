# M365 Copilot Training — Risk Containment Unit & Risk/Compliance (Bajaj Finance Limited)

Training materials for a Microsoft 365 Copilot enablement session for the Bajaj Finance Limited (BFL) Risk Containment Unit (RCU) and Risk/Compliance teams, delivered by Technizer India under the **GenAI for Enterprise Teams** program.

The session covers prompt engineering (meta-prompting, RTCFT framework), Copilot in Excel (formulas, pivot tables), working with a policy PDF, the end-to-end flow from a raw data file to a leadership-ready deck, and using Copilot Notebooks to work across more files than the chat attachment limit.

## Contents

| File | Description |
|---|---|
| [`MetaPrompting_Guide_RCU_BFL.md`](MetaPrompting_Guide_RCU_BFL.md) | Introduces meta-prompting — asking Copilot to write your prompt for you. Includes ready-to-use meta-prompts for RCU work. |
| [`BFL_Risk_Compliance_Copilot_Participant_Handout.md`](BFL_Risk_Compliance_Copilot_Participant_Handout.md) | Half-day participant handout built around the **RTCFT** (Role–Task–Context–Format–Tone) framework, with five use cases: credit portfolio risk, fraud pattern identification, risk reporting, policy and compliance review, and risk monitoring / early warning. |
| [`BFL_RCU_CopilotExcel_Participant_Guide.md`](BFL_RCU_CopilotExcel_Participant_Guide.md) | Hands-on exercises for Copilot in Excel — formula columns (breach flag, risk score band, pending days, resolution category), explaining formulas, and pivot tables on RCU case data. |
| [`BFL_RCU_Alt_Copilot_Chat_Participant_Guide.md`](BFL_RCU_Alt_Copilot_Chat_Participant_Guide.md) | Same Excel exercises **without Excel Agent / Edit with Copilot** — for Copilot Chat (Basic) users, with a context-setting prompt, manual apply and expected results to verify. |
| [`Excel_To_PowerPoint.md`](Excel_To_PowerPoint.md) | "AI at Work" workbook describing a 9-step Copilot flow — across three chats (Discovery, Execution, PowerPoint agent) — for turning any file into an analysis, a Word document, and a leadership deck. |
| [`Copilot_Notebooks_Guide.md`](Copilot_Notebooks_Guide.md) | Using Copilot Notebooks as a persistent workspace — add all files once as references, set standing instructions, and query across the case log, fraud data, compliance tracker and RBI Directions without re-attaching. |
| [`copilot-pdf-playbook.md`](copilot-pdf-playbook.md) | Repeatable process for turning large content into a formatted PDF using Copilot and Word. |
| [`RBI_Policy.pdf`](RBI_Policy.pdf) | RBI (NBFC – Internal Ombudsman) Directions, 2026 — the policy document used in the Policy and Compliance exercises. |
| [`BFL_Risk_Compliance_Copilot_Dataset.xlsx`](BFL_Risk_Compliance_Copilot_Dataset.xlsx) | Practice dataset for the handout use cases. Sheets: Loan Portfolio Risk, Fraud Pattern Detection, Risk Reporting Dashboard, Policy Compliance Tracker, Risk Monitoring Signals. |
| [`BFL_RCU_Copilot_Demo.xlsx`](BFL_RCU_Copilot_Demo.xlsx) | Practice dataset for the Excel exercises — 25 RCU cases with columns left blank for participants to fill in using Copilot-generated formulas. |
| [`PDFs/`](PDFs) | PDF versions of the handout, the meta-prompting guide, the Excel guide and the playbook. |

## How to use this material

1. Start with `MetaPrompting_Guide_RCU_BFL.md` and `BFL_Risk_Compliance_Copilot_Participant_Handout.md` to learn the RTCFT framework and generate working prompts against `BFL_Risk_Compliance_Copilot_Dataset.xlsx`.
2. Move to `BFL_RCU_CopilotExcel_Participant_Guide.md` for hands-on formula and pivot table exercises using `BFL_RCU_Copilot_Demo.xlsx` (requires a Microsoft 365 Copilot licence).
   - **Basic licence / Copilot Chat only?** Use `BFL_RCU_Alt_Copilot_Chat_Participant_Guide.md` instead — same exercises, no Agent required.
3. Finish with `Excel_To_PowerPoint.md` to practice the full 9-step flow from raw file to analysis, document, and deck.
4. Use `Copilot_Notebooks_Guide.md` to move all of the above into a single Copilot Notebook — no re-attaching, no 3-file limit.

## Requirements

- Microsoft 365 Copilot (Copilot Chat and Copilot in Excel/PowerPoint) — **or**, for Basic licence users, Copilot Chat only (see `BFL_RCU_Alt_Copilot_Chat_Participant_Guide.md`)
- Access to Copilot Notebooks in the M365 Copilot app (for `Copilot_Notebooks_Guide.md`)
- Excel files and the policy PDF uploaded to OneDrive so they can be attached in Copilot Chat

---

*Delivered by Technizer India | GenAI for Enterprise Teams*

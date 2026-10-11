# Copilot Notebooks — Participant Guide
### One workspace, all your files, no re-attaching
**Bajaj Finance Limited | M365 Copilot Training — Risk Containment Unit (RCU) & Risk/Compliance**
**Files used:** `BFL_RCU_Copilot_Demo.xlsx`, `BFL_Risk_Compliance_Copilot_Dataset.xlsx`, `RBI_Policy.pdf`, and the guides in this repo

---

## Why Notebooks?

In a normal Copilot Chat, every new conversation starts from zero. You attach the file again, explain your role again and restate the format you want again. You are also limited to **3 attachments per prompt**.

A **Copilot Notebook** is a saved workspace for one piece of work. You add your files to it once, as **references**, and write your standing instructions once. After that, every chat you start inside the notebook is grounded on those references, and it stays that way across sessions and days.

| | Regular Copilot Chat | Copilot Notebook |
|---|---|---|
| Files | Attached per prompt (max **3** in BFL) | Added once as **references**, then available to every chat in the notebook |
| Context | Lost when you open a new chat | Kept in the notebook across chats and days |
| Instructions (role, tone, format) | Re-typed in every prompt (the RTCFT block) | Set once in the notebook's **Copilot instructions** |
| Grounding | Your prompt + attachments (+ wider M365 / web, depending on settings) | **Only** the references you added, so answers stay focused on your files |
| Outputs | Chat replies | Chat replies, saved pages, and (where enabled) Word / PowerPoint drafts, mind maps, study guides |

> 💡 **Rule of thumb:** use one notebook per piece of work, such as the June fraud-case review, a policy gap check or a Risk Committee pack. Don't create a new notebook for every question.

---

## ⭐ Going Beyond the 3-Attachment Limit

This is the most useful reason to use Notebooks at BFL.

- The 3-file limit applies to **attachments in a chat prompt**.
- Notebook **references** are added separately, through the notebook's *Add references* panel rather than the chat box. Copilot then grounds its answers on **all** of them together.
- According to Microsoft's documentation:
  - **Copilot Chat** users can add up to **50 references**, and all 50 are used for grounding.
  - **Microsoft 365 Copilot** (licensed) users can add more than 300 references. The first **300** are used for grounding.
- A **OneDrive or SharePoint folder** can be added as a single reference. Every file you put in that folder later is then available to the notebook without any extra steps.

**In practice:** you can ask one question that draws on the case log, the fraud transactions, the early-warning signals and the RBI Directions at once, without attaching anything to the prompt.

> ⚠️ **Check in your own tenant:** the 3-attachment cap is BFL's setting for chat. If references in your notebook also appear capped, report it to your trainer or IT, because the admin policy may be set differently. Exercise 2 below is a simple way to test this.

---

## Before You Begin

- [ ] You can sign in to the **M365 Copilot** app (desktop or web) with your BFL work account, and you see **Notebooks** in the left navigation.
- [ ] You have copied the files from this repo to your **OneDrive** (a folder such as `OneDrive › Copilot-Training-RCU`).
- [ ] You have made `.txt` copies of the three Markdown guides. Notebooks accept `.docx, .pptx, .xlsx, .pdf, .loop, .page, .txt, .rtf` and OneNote pages, but **not `.md`**. Download the guides, then rename them:

| Original in repo | Rename to |
|---|---|
| `MetaPrompting_Guide_RCU_BFL.md` | `MetaPrompting_Guide_RCU_BFL.txt` |
| `BFL_Risk_Compliance_Copilot_Participant_Handout.md` | `BFL_Risk_Compliance_Copilot_Participant_Handout.txt` |
| `Excel_To_PowerPoint.md` | `Excel_To_PowerPoint.txt` |

`RBI_Policy.pdf` needs no renaming, because PDFs are accepted as they are.

Your OneDrive folder should now contain **6 files**:

```
Copilot-Training-RCU/
├── BFL_RCU_Copilot_Demo.xlsx                  (25 RCU cases, RCU-001 to RCU-025)
├── BFL_Risk_Compliance_Copilot_Dataset.xlsx   (Loan Portfolio Risk, Fraud Pattern Detection,
│                                               Risk Reporting Dashboard, Policy Compliance Tracker,
│                                               Risk Monitoring Signals)
├── RBI_Policy.pdf                             (RBI NBFC Internal Ombudsman Directions, 2026)
├── MetaPrompting_Guide_RCU_BFL.txt
├── BFL_Risk_Compliance_Copilot_Participant_Handout.txt
└── Excel_To_PowerPoint.txt
```

That is already **twice the 3-attachment limit**, which is intentional for these exercises.

---

# Exercise 1 — Create Your Notebook
**Time:** ~5 minutes

### Step 1 — Create it
1. In the M365 Copilot app, select **Notebooks** → **New notebook**.
2. Name it: `BFL RCU — June FY26-27 Risk Review`

### Step 2 — Add references
1. Select **Add references** (at the top of the content pane in the Copilot app, or the **+** next to *References* in OneNote).
2. Choose **one** of these methods:
   - **Option A: files.** Select all 6 files from your OneDrive folder, or use **Upload** to add them from your computer.
   - **Option B: folder (recommended).** Select the `Copilot-Training-RCU` **folder** as a single reference.
3. Select **Add**.

> 💡 **Option B scales better.** When you drop next month's case log into the folder, the notebook can use it without any extra step.

### Step 3 — Set the Copilot instructions (your RTCFT Role, Format and Tone, written once)
Open the notebook's **Copilot instructions** and paste:

```
I work in the Risk Containment Unit (RCU) and Risk & Compliance teams at Bajaj Finance Limited (an NBFC).
Turnaround time (TAT) and benchmarks are in days unless a column says otherwise. Currency is ₹.
The RCU case log covers May–June 2026. The risk dataset (portfolio, fraud, compliance and early-warning
sheets) is dated FY2025-26 and June 2025. These are different periods, so always say which period a
number comes from.

When you answer:
- Use only the references in this notebook. Name the file and sheet (or the clause number, for the RBI
  document) for every number or rule you quote.
- If something is not in the references, say "not in the data" — do not estimate.
- Matching people or accounts across files by name is a lead, not proof. Say that it is a name match
  and list what should be verified.
- Lead with a 3-line summary, then a table, then recommendations with a suggested owner.
- Tone: formal, precise and risk-aware — suitable for the Head of Risk or the Risk Committee.
- Use Red / Amber / Green status where a benchmark, threshold or alert level exists.
```

### ✅ Check
Your notebook shows **6 references**, or 1 folder, and the instructions are saved.

---

# Exercise 2 — Validate the Notebook Can See Everything
**Time:** ~5 minutes

Before you rely on any analysis, confirm that Copilot has read every reference. This is the same idea as Step 1 of the 9-Step Flow.

Start a chat **inside the notebook** and type:

```
List every reference in this notebook. For each one, give:
- the file name
- what it contains (sheets / sections / chapters, row counts, periods covered)
- one fact from it that proves you have read it
Then tell me if any file looks incomplete or could not be read.
```

### ✅ Check
- [ ] All **6 files** are listed. This is more than you could attach to one chat prompt.
- [ ] For `BFL_Risk_Compliance_Copilot_Dataset.xlsx`, it names the five sheets (Loan Portfolio Risk, Fraud Pattern Detection, Risk Reporting Dashboard, Policy Compliance Tracker, Risk Monitoring Signals).
- [ ] For `BFL_RCU_Copilot_Demo.xlsx`, it mentions 25 cases (RCU-001 to RCU-025).
- [ ] For `RBI_Policy.pdf`, it identifies the Internal Ombudsman Directions, 2026 (dated 14 January 2026).

> If a file is missing, open **References**, confirm it is listed, and check that you have access to it in OneDrive.

---

# Exercise 3 — Ask Across Files (the payoff)
**Time:** ~15 minutes

Neither of these questions could be answered in one regular chat prompt without going past the 3-attachment limit. In the notebook, you don't attach anything.

### 3a — One risk theme, every source

```
Fraud appears in several places:
- RCU Case Log (BFL_RCU_Copilot_Demo.xlsx) — Case Type "Fraud Investigation"
- Fraud Pattern Detection (BFL_Risk_Compliance_Copilot_Dataset.xlsx) — by Investigation Status
- Risk Monitoring Signals (same workbook) — the fraud-related early-warning signal

Build a one-page view of fraud:
1. RCU fraud cases: how many, how many closed, how many breached the TAT benchmark, average TAT, status
2. Transactions: counts by Investigation Status, and which are Confirmed Fraud or Escalated to Legal
3. Early warning: the fraud signal, its trend, threshold and alert level
4. Link: which RCU applicants also appear in Fraud Pattern Detection (match on name),
   with the transaction status next to each RCU case status
Then tell me which RCU cases should be re-opened or re-checked, and why. Recommend 3 actions.
```

**What a good answer contains:**
- **RCU cases:** there are 6 Fraud Investigation cases (RCU-002, 006, 010, 013, 016, 021). 5 are closed and all 5 breached the 5-day benchmark, with an average TAT of 14.4 days. RCU-006 is still open. 4 of the 6 are Escalated.
- **Transactions:** of 25 transactions, 2 are Confirmed Fraud, 1 is Escalated to Legal, 6 are Under Investigation, 2 are Pending Review, 9 are Closed – False Positive and 5 are Closed – Genuine.
- **Early warning:** EWS-003 shows UPI fraud attempts at 186 cases against a threshold of under 100, rising, with a HIGH alert.
- **The link:** 20 transactions belong to 13 names that also appear as RCU applicants. Two RCU cases are **Cleared** although the same name has a **Confirmed Fraud** transaction: RCU-009 (Deepak Joshi, TXN250600016, ₹10,00,000) and RCU-005 (Vikram Singh, TXN250600009, ₹5,000). RCU-021 (Ravi Malhotra, Critical, Escalated) matches TXN250600013, which is Escalated to Legal.

> ⚠️ **Read this before you act on the link.** The case log is dated May–June 2026 and the fraud sheet June 2025, and the match is on name only. A good answer says so and treats the two Cleared cases as *"verify"*, not as proven fraud.

### 3b — Policy against practice

```
Compare the RBI Internal Ombudsman Directions, 2026 (RBI_Policy.pdf) with the
"Ombudsman Scheme - NBFC" row of the Policy Compliance Tracker.
1. What does the tracker say we must do and by when?
2. What do the Directions require, with clause numbers: the 30-day final decision,
   the escalation to the Internal Ombudsman, the decision categories, the rule on who may close a
   complaint, and the quarterly reporting?
3. List every requirement in the Directions that the tracker row does not mention.
4. Which clauses had a compliance deadline of 30 June 2026?
Give me a gap table (Requirement | Clause | In tracker? | Suggested action | Owner).
```

**What a good answer contains:**
- **Tracker:** the row is owned by Head – Customer Svc, with status WATCH, the gap "TAT breach in 3 cases" and the requirement "Grievance redressal within 30 days".
- **Directions:**
  - Clause 14(9): final decision to the complainant within 30 days.
  - Clause 14(1)(b): complaints that are partially resolved or wholly rejected are auto-escalated to the Internal Ombudsman within 20 days. Clause 14(1)(a) applies where an RBI, NPCI or card-network timeline exists.
  - Clause 14(2): only three decision categories, Fully Resolved, Partially Resolved and Wholly Rejected.
  - Clause 14(4): a complaint may not be closed by the same branch or unit.
  - Clause 7(2): quarterly reporting to the RBI.
- **Gap:** the tracker mentions only the 30-day rule. The 20-day escalation, the three categories, the same-unit rule and the quarterly reporting are not in it.
- **Deadline:** clauses 7(2), 14(2) and 14(4) were due by **30 June 2026**.

### ✅ Check
- [ ] The answer quotes figures with **file and sheet names** (and clause numbers for 3b), as your instructions asked.
- [ ] 3a draws on **both** workbooks and at least three sheets.
- [ ] 3b draws on the PDF **and** a workbook.
- [ ] You did **not** attach a single file.

> 💡 **Tip:** Copilot may paraphrase a clause. Open `RBI_Policy.pdf` and read the clause yourself before you quote it in a note or a report.

---

# Exercise 4 — Re-run the Five Risk Use Cases Without Re-attaching
**Time:** ~10 minutes

In `BFL_Risk_Compliance_Copilot_Participant_Handout.md`, every use case says to attach the Excel file in the chat before pasting the prompt. In the notebook, you skip the attach step.

Pick any two use cases and use the short versions below. The notebook instructions already supply the role, tone and format.

| Use Case | Prompt inside the notebook |
|---|---|
| 1 — Credit Portfolio Risk Analysis | `From Loan Portfolio Risk: a DPD bucket table (count, outstanding, provision), flag every loan at 91 DPD or more, and list the top 3 at-risk accounts with a recommended action.` |
| 2 — Fraud Pattern Identification | `From Fraud Pattern Detection: count transactions by Investigation Status and by Velocity Flag, list the Confirmed Fraud and Escalated to Legal items, and show the top 3 by Anomaly Score.` |
| 3 — Risk Reporting | `From Risk Reporting Dashboard: list every KPI with a WATCH status, show the change from the previous month, and write a 3-bullet summary for the Risk Committee.` |
| 4 — Policy and Compliance Review | `From Policy Compliance Tracker: list every item that is not COMPLIANT with its gap, owner, next review date and required action. Rank them by urgency.` |
| 5 — Risk Monitoring & Early Warning | `From Risk Monitoring Signals: group signals by Alert Level, list the HIGH ones with trend, current level, threshold and owner, and suggest which two need action first.` |

**Quick checks:**
- **Use case 4:** 3 of the 10 items are not COMPLIANT — Fair Practices Code (WATCH), DPDP Act (AT RISK) and the Ombudsman Scheme (WATCH).
- **Use case 5:** the 12 signals split into 4 HIGH, 4 MEDIUM and 4 LOW. The HIGH ones are EWS-001, EWS-003, EWS-008 and EWS-010.

### ✅ Check
Compare the output with the one you got in the regular chat earlier. The format and tone should be consistent **without** you retyping the RTCFT Role, Format and Tone, because the notebook instructions supply them.

---

# Exercise 5 — The 9-Step Flow, Inside One Notebook
**Time:** ~10 minutes

`Excel_To_PowerPoint.md` uses three separate chats (A: Discovery, B: Execution, C: PowerPoint) and asks you to **attach the file again** in Chat B. In a notebook:

1. Start **Chat A** in the notebook and run Steps 1–4 on a sheet of your choice, such as the RCU Case Log or Fraud Pattern Detection. Copy the Working Prompt from Step 4.
2. Start a new chat in the **same notebook** (Chat B) and paste the Working Prompt. The file is already there, so there is no re-attaching.
3. Save the useful output as a **page** in the notebook, so it doesn't sit only in a chat.
4. If your notebook shows **create options** (Word document / PowerPoint deck), generate the Step-6 document or the Step-9 deck from the notebook. Otherwise, continue with the PowerPoint agent as in the workbook.

> 💡 **Why this helps:** the chats stay separate, which keeps the output clean, while the files and instructions are shared. You get the benefit of the 3-chat method without the re-attaching.

---

## Optional Extras (if visible in your tenant)

Microsoft is rolling out Notebook features in stages, so some of these may not appear for you yet.

| Feature | Try this |
|---|---|
| **Mind map** | Create a mind map of the notebook to see how cases, transactions, signals and RBI clauses connect. |
| **Study guide** | Generate a quiz or flashcards from `MetaPrompting_Guide_RCU_BFL` to test yourself on RTCFT. |
| **Word / PowerPoint from notebook** | Turn your Exercise 3a output into a Word brief or a 5-slide Risk Committee deck. |
| **Share the notebook** | Share with a colleague so they work from the same references and instructions. |

---

## Efficiency Rules — Quick Reference

| Do | Avoid |
|---|---|
| One notebook per piece of work (e.g. "June fraud-case review", "Ombudsman policy gap check") | One giant notebook for everything, because the grounding gets noisy |
| Put role, period, units, tone and format in **Copilot instructions** | Re-typing the RTCFT block in every prompt |
| Add a **folder** reference when logs and reports keep arriving | Re-uploading each new version by hand |
| Remove outdated references (old policy versions, superseded logs) | Keeping v1, v2 and v3 of the same file, because Copilot may quote the wrong one |
| Ask Copilot to **name file + sheet or clause** for every number or rule | Accepting figures you can't trace |
| Treat cross-file name matches as leads and verify them | Acting on a match as if it were proof |
| Save good outputs as **pages** | Leaving key results only in chat history |
| Start a **new chat in the same notebook** for each new task | One endless chat, where earlier answers leak into later ones |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| `.md` file can't be added | Rename to `.txt`, or copy the content into a notebook page. |
| Copilot says it can't find a number | Check that the file is in **References** and that you can open it. Ask: *"Which sheet contains X?"* |
| Copilot mixes the 2026 case log with the 2025 risk data | Name the file and period in your prompt: *"Use only the RCU Case Log (May–June 2026)."* |
| A clause or figure looks wrong | Open the source file, check it yourself, then ask Copilot to quote the exact text. |
| Answer uses the wrong file version | Remove old versions from References. |
| Notebooks not in the left navigation | Your licence or tenant setting may not include Notebooks yet. Tell your trainer. |
| Folder reference returns partial results | Very large folders are ranked for relevance, so name the specific file in your prompt. |

---

## Further Reading

- [How Microsoft Copilot Notebooks works](https://support.microsoft.com/en-us/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works)
- [Add references to your Copilot Notebook](https://support.microsoft.com/en-us/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook)
- [Microsoft 365 Copilot release notes](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

## 📝 Notes

**What I would put in a notebook at work:**

&nbsp;

**My standing Copilot instructions:**

&nbsp;

---

*Bajaj Finance Limited | M365 Copilot Training — Risk Containment Unit & Risk/Compliance*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*

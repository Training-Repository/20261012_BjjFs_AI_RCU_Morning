# Excel with Copilot Chat — No Agent Required
### Formulas & Pivot Tables for the Risk Containment Unit (RCU), using Copilot Chat + Meta-Prompting
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_RCU_Copilot_Demo.xlsx`
**Companion guides:** `MetaPrompting_Guide_RCU_BFL.md` · `BFL_RCU_CopilotExcel_Participant_Guide.md` (Agent version)

---

## Who This Guide Is For

`BFL_RCU_CopilotExcel_Participant_Guide.md` uses **Edit with Copilot** in Excel, which used to be called Agent Mode. In that mode Copilot writes formulas into your cells and builds pivot tables for you, and it needs a **paid Microsoft 365 Copilot licence**.

This guide produces **the same eight results** with **Copilot Chat only**:

- **Copilot does the thinking.** It writes the formula, explains the logic and gives you the pivot layout.
- **You do the clicking.** You paste the formula and build the pivot in Excel yourself, which takes about 30 seconds per exercise.

### Which one do you have?

Check the label on Copilot in the Microsoft 365 app or in Excel:

| Label you see | What works for you |
|---|---|
| **Microsoft 365 Copilot (Premium / Pro)** | Either guide. The Agent guide is faster. |
| **Microsoft 365 Copilot (Basic)** | **This guide.** You can run the prompts in Copilot Chat **or** in the Copilot pane inside Excel, but Copilot will not edit the workbook for you. |
| **Copilot Chat (Basic)** | **This guide**, using Copilot Chat in the M365 Copilot app or at `m365copilot.com`. |

---

## How Every Exercise Works

```
Step 1 → Paste the Excel Meta Prompt with that exercise's TASK filled in
Step 2 → Read the Working Prompt Copilot generates
Step 3 → Attach BFL_RCU_Copilot_Demo.xlsx and run the Working Prompt
Step 4 → Apply Copilot's answer in Excel yourself (paste formula / build pivot)
Step 5 → Verify against the expected numbers in this guide
```

> 💡 **Why Step 5 matters:** without an agent, nobody checks the result but you. The expected numbers below let you spot a wrong formula in seconds.

---

## Before You Begin

1. Open `BFL_RCU_Copilot_Demo.xlsx` in **Excel** (desktop or web) and go to the **RCU Case Log** sheet.
2. Open **Copilot Chat** in a second window, either the M365 Copilot app or `m365copilot.com`.
3. Keep both windows side by side.

### What's in the file

- Row 1 is a title and **row 2 holds the headers**. **Data runs in rows 3–27** (25 cases, RCU-001 to RCU-025). Rows 28–29 are a blank row and a note.
- Columns **Q–T already have headers** (`➕ Breach Flag`, `➕ Risk Score Band`, `➕ Pending Days`, `➕ Resolution Category`) and empty cells below them. You will fill those cells.
- ⚠️ **Case Received Date (J) and Case Closed Date (K) are stored as text**, for example `2 Jun 2026`, not as real Excel dates. This matters in Exercise 3.
- The workbook has a single sheet. **Build your own pivots on a new sheet** and check them against the expected results in this guide.

| Column | Field | Column | Field |
|---|---|---|---|
| A | Case ID | I | Case Owner |
| B | Branch Name | J | Case Received Date |
| C | Branch Code | K | Case Closed Date *(blank if open)* |
| D | Zone | L | TAT (Days) *(blank if open)* |
| E | Case Type | M | TAT Benchmark (Days) |
| F | Applicant Name | N | Customer Segment |
| G | Product | O | Risk Level (Low / Medium / High / Critical) |
| H | Loan Amount (₹) | P | Status (Cleared / Pending / Escalated) |
| Q–T | **You fill these** | | |

---

## ⚡ The Excel Meta Prompt — Your Starting Point

This follows the RTCFT pattern from `MetaPrompting_Guide_RCU_BFL.md`, adapted for Excel. The file layout is already filled in, so for each exercise you only replace **[TASK]**.

```
Act as a Microsoft Copilot prompt expert specialising in Excel for a risk containment unit.

Role:    I am an RCU (Risk Containment Unit) Analyst at Bajaj Finance Limited. I use Copilot
         Chat, which cannot edit my workbook — I will apply the result in Excel myself.
Task:    I need to: [TASK]
Context: Sheet "RCU Case Log" in BFL_RCU_Copilot_Demo.xlsx.
         Headers are in row 2; data is in rows 3 to 27 (25 cases).
         Columns: A Case ID, B Branch Name, D Zone, E Case Type, I Case Owner,
         J Case Received Date, K Case Closed Date, L TAT (Days), M TAT Benchmark (Days),
         N Customer Segment, O Risk Level, P Status.
         Dates in J and K are stored as TEXT like "2 Jun 2026". Open cases have blank K and L.
Format:  The prompt must ask Copilot for:
         1. The exact result (formula for row 3, or pivot/table layout) ready to copy
         2. Step-by-step instructions to apply it manually in Excel
         3. How to handle blanks and text dates
         4. A quick way to verify the result is correct
Tone:    Clear and step-by-step, for an RCU user who is not an Excel expert.

Write me a detailed, ready-to-use Copilot prompt I can use in Copilot Chat with this file attached.
```

> ✏️ **Short on time?** Once you've done this for Exercise 1, you can reuse the Working Prompt Copilot gave you and swap in the new task for the later exercises.

---

---

# Exercise 1 — Formula Column: Breach Flag (Q)
**Time:** ~8 minutes

### Step 1 — [TASK] to paste into the Meta Prompt
```
write a formula for column Q ("Breach Flag") that returns "Pending" if TAT (L) is blank,
"Breach" if TAT is greater than the TAT Benchmark (M), otherwise "On Time", for rows 3 to 27
```

### Step 2 — Check the Working Prompt
- [ ] Does it mention row 3 and filling down to row 27?
- [ ] Does it ask for manual steps and a verification check?

### Step 3 — Attach the file and run
Attach `BFL_RCU_Copilot_Demo.xlsx` → paste the Working Prompt → send.

### Step 4 — Apply in Excel
1. Click **Q3** and paste the formula Copilot gave you.
2. Fill it down to **Q27**: select **Q3:Q27** and press **Ctrl + D**, or double-click the fill handle at the bottom-right corner of Q3.

### Step 5 — Verify
Type this in any empty cell, such as **W3**:
```excel
=COUNTIF(Q3:Q27,"Breach")
```
**Expected: 13 Breach · 5 On Time · 7 Pending.**
- **Why 7 Pending when column P shows only 6?** RCU-006 is *Escalated* but still open, so its TAT is blank too.
- **11 of the 13 breaches are in the West zone** and 2 are in Central.

<details><summary>Reference formula (open only if stuck)</summary>

```excel
=IF(L3="","Pending",IF(L3>M3,"Breach","On Time"))
```
</details>

> **Discussion Point:** Which case types dominate the 13 breaches? All five closed Fraud Investigation cases are among them. What makes fraud reviews run so far past a 5-day benchmark?

---

# Exercise 2 — Formula Column: Risk Score Band (R)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column R ("Risk Score Band") that converts Risk Level (O) into a number:
"Critical" = 4, "High" = 3, "Medium" = 2, "Low" = 1, any other value = 0, for rows 3 to 27
```

### Steps 2–4
Same as Exercise 1, but paste in **R3** and fill down to **R27**.

### Step 5 — Verify
```excel
=SUM(R3:R27)
```
**Expected: 54.**
- By band: **4 cases score 4** (Critical), **5 score 3** (High), **7 score 2** (Medium), **9 score 1** (Low).
- Check one band: `=COUNTIF(R3:R27,4)` returns **4**, which is RCU-006, 010, 016 and 021.

<details><summary>Reference formula</summary>

```excel
=IF(O3="Critical",4,IF(O3="High",3,IF(O3="Medium",2,IF(O3="Low",1,0))))
```
</details>

> 💡 **Why a number?** A numeric band can be sorted and filtered, so Critical cases rise to the top of any report.

---

# Exercise 3 — Formula Column: Pending Days (S) ⚠️ the text-date trap
**Time:** ~10 minutes

### Step 1 — [TASK]
```
write a formula for column S ("Pending Days") that returns 0 if the case is closed
(Case Closed Date K is not blank), otherwise the number of days from the Case Received
Date (J) to today. Remember J is stored as text like "2 Jun 2026". Rows 3 to 27.
```

### Steps 2–4
Paste in **S3** and fill down to **S27**.

### Step 5 — Verify
- **18 rows show 0**, one for each closed case.
- **7 rows show a number of days**: RCU-003, 006, 008, 011, 017, 019, 023.
  - On 12 Oct 2026, those values range from **131 to 138** days.
  - They go up by one each day, because the formula uses `TODAY()`.
- Check one row yourself. RCU-006 was received on 27 May 2026, so this should match **S8**:
```excel
=TODAY()-DATE(2026,5,27)
```

### ❗ If you see `#VALUE!` on the open rows
Your Excel could not read the text date. This depends on your regional settings. Tell Copilot:
```
The formula returns #VALUE! for open rows because DATEVALUE cannot read "2 Jun 2026" in my
regional settings. Give me a version that builds the date from the text without DATEVALUE.
```

<details><summary>Reference formulas</summary>

Try this first. It works in most English regional settings:
```excel
=IF(K3<>"",0,TODAY()-DATEVALUE(J3))
```
This version works in any regional setting:
```excel
=IF(K3<>"",0,TODAY()-DATE(RIGHT(J3,4),MATCH(MID(J3,FIND(" ",J3)+1,3),{"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"},0),LEFT(J3,FIND(" ",J3)-1)))
```
If the result shows as a date instead of a number, set the column format to **Number**.
</details>

> **Lesson:** Copilot's first formula is a *draft*. When a formula errors, don't fix it by hand. Paste the error back into Copilot Chat along with the reason.

> **Discussion Point:** Which open cases have waited the longest? Are they concentrated in one owner, branch or case type? Four of the seven are Document Verification or Address Verification cases that look routine, yet they have waited over four months.

---

# Exercise 4 — Formula Column: Resolution Category (T)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column T ("Resolution Category") that returns: "Pending" if TAT (L) is blank;
"Fast" if TAT is 50% or less of the TAT Benchmark (M); "Within TAT" if TAT is within the Benchmark;
"Moderate Breach" if TAT exceeds the Benchmark by up to 50%; "Critical Breach" if more than 50%.
Rows 3 to 27.
```

### Steps 2–4
Paste in **T3** and fill down to **T27**.

### Step 5 — Verify
**Expected: 5 Within TAT · 6 Moderate Breach · 7 Critical Breach · 7 Pending · 0 Fast.**
- The 7 Critical Breaches are RCU-002, 005, 010, 013, 016, 021 and 024. Five of them are Fraud Investigation cases.

> 💡 **Zero "Fast" is correct.** No case closed in half its benchmark or less. An empty category doesn't mean the formula is wrong, so always check against the data.

<details><summary>Reference formula</summary>

```excel
=IF(L3="","Pending",IF(L3<=M3*0.5,"Fast",IF(L3<=M3,"Within TAT",IF(L3<=M3*1.5,"Moderate Breach","Critical Breach"))))
```
</details>

---

# Exercise 5 — Ask Copilot to Explain a Formula
**Time:** ~3 minutes

This works exactly as it does in the Agent version. No meta prompt or attachment is needed.

Copy the formula from **T3** and paste it into Copilot Chat:
```
Explain this Excel formula in simple terms for an RCU user. What does each part
do, and in what order are the conditions checked?
[paste formula here]
```

**What to look for:**
- The explanation should state that the conditions are checked **in order**.
- Each `IF` only runs if the one before it was not true.

---

# Exercise 6 — Pivot Table: Cases by Case Type and Status
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the count of cases for each Case Type (rows) broken down by
Status (columns: Cleared, Pending, Escalated). Give me the exact field placement and
click-by-click steps to build it in Excel, plus the expected result table so I can check my pivot.
```

### Steps 2–3
Run the Working Prompt with the file attached, as before.

### Step 4 — Build it in Excel
1. On **RCU Case Log**, select **A2:T27** exactly. Don't include the title in row 1 or the note rows below the data.
2. Go to **Insert → PivotTable → New Worksheet → OK**.
3. Place the fields:
   - **Case Type** → Rows
   - **Status** → Columns
   - **Case ID** → Values. It shows as *Count of Case ID*.

### Step 5 — Verify

| Case Type | Cleared | Escalated | Pending | Total |
|---|---|---|---|---|
| Address Verification | 3 | | 1 | 4 |
| Document Verification | 1 | | 3 | 4 |
| Employment Verification | 3 | | 1 | 4 |
| Fraud Investigation | 2 | 4 | | 6 |
| Pre-Disbursement Verification | 4 | | | 4 |
| Reference Check | 2 | | 1 | 3 |
| **Grand Total** | **15** | **4** | **6** | **25** |

*Excel sorts rows and columns alphabetically by default, so your order may differ from the list in the Agent guide.*

> **Discussion Point:** All 4 Escalated cases are Fraud Investigations, and 3 of the 4 Document Verification cases are still pending. Where is the backlog forming, and is it the same reason in both?

---

# Exercise 7 — Pivot Table: Average TAT by Case Owner
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the AVERAGE TAT (Days) for each Case Owner (rows) broken down by
Case Type (columns). Give me the field placement, click-by-click steps, how to switch the
value from Count to Average, and the expected row totals.
```

### Step 4 — Build it in Excel
1. Select **A2:T27** → **Insert → PivotTable → New Worksheet**.
2. Place the fields:
   - **Case Owner** → Rows
   - **Case Type** → Columns
   - **TAT (Days)** → Values
3. Excel may default the value to **Count** because the column contains blanks. To change it:
   - Click the value field → **Value Field Settings → Average → OK**.
   - Blank rows (open cases) are ignored in the average.

### Step 5 — Verify (Grand Total column)

| Case Owner | Average TAT (days) | Closed cases |
|---|---|---|
| Priya Desai | 11 | 2 |
| Sunita Rao | 11 | 1 |
| Amit Kulkarni | 8.75 | 4 |
| Neha Joshi | 6.67 | 3 |
| Rahul Mehta | 6.25 | 4 |
| Ravi Patil | 4.25 | 4 |
| **Grand Total** | **7.22** | **18** |

> **Discussion Point:** Priya Desai's 11-day average is a 3-day case and a 19-day Fraud Investigation (RCU-021, Critical). Sunita Rao's 11 days rests on a single case. How many cases does an average need before you act on it? And is the fraud workload spread fairly across officers?

> 💡 **No pivot tables allowed on your machine?** Ask Copilot for the same result as a `COUNTIFS` / `AVERAGEIFS` formula grid instead. For example, `=AVERAGEIFS(L3:L27,I3:I27,"Rahul Mehta")` returns **6.25**.

---

# Exercise 8 — Bonus: Ask Copilot for Insights
**Time:** ~5 minutes

This works directly in Copilot Chat with the file attached. No manual steps are needed.

```
Look at the RCU Case Log sheet in the attached file. Which branches have the most Critical
and High risk cases? If branches are tied, group them by city (e.g. all "Mumbai …" branches
together). Which case owners have the highest proportion of Escalated cases? Summarise the
top risk areas for the RCU team in 3 bullet points, quoting Case IDs as evidence.
```

**Expected:**
- **There are 9 High or Critical cases** (5 High, 4 Critical): RCU-002, 005, 006, 010, 013, 016, 019, 021 and 024.
- **At branch level, nothing is ahead.** Every one of the 25 branches appears once, so the branch-level question has no single answer.
- **By city:** **Mumbai 3** (Andheri, Dadar, Bandra), **Pune 3** (Kothrud, Wakad, Shivajinagar), then **Nashik 1**, **Solapur 1** and **Nagpur 1**.
- **By zone:** 7 of the 9 are in the **West** zone and 2 in Central.
- **Escalated proportion by owner:** Rahul Mehta, Priya Desai and Amit Kulkarni are tied at **1 of 4 (25%)**, Neha Joshi is **1 of 5 (20%)**, and Sunita Rao and Ravi Patil have none.

> 💡 **Lesson:** if Copilot names one "top branch" or one "highest owner", check it against the data. A question that ends in a tie needs a better grouping, and here city works better than branch.

---

## Reference: What Your Results Should Show

| Check | Expected |
|---|---|
| Total cases | 25: 15 Cleared · 6 Pending · 4 Escalated |
| Breach Flag | 13 Breach (11 West, 2 Central) · 5 On Time · 7 Pending |
| Risk Score Band | 4 Critical (4) · 5 High (3) · 7 Medium (2) · 9 Low (1) · total score 54 |
| Pending Days | 18 rows at 0 · 7 open cases, 131–138 days on 12 Oct 2026 |
| Resolution Category | 5 Within TAT · 6 Moderate · 7 Critical · 7 Pending · 0 Fast |
| Fraud Investigation | 6 cases: all 4 Escalated cases, and 5 of the 7 Critical Breaches |
| Highest average TAT | Priya Desai, 11 days (2 cases); Sunita Rao, 11 days (1 case) |
| Overall average TAT | 7.22 days across 18 closed cases |

---

## Agent vs Copilot Chat — What Changes

| | Edit with Copilot (Agent) | Copilot Chat + Meta Prompt (this guide) |
|---|---|---|
| Licence | Microsoft 365 Copilot (paid) | Copilot Chat / Basic |
| Writes formula into cells | ✅ Automatic | ✍️ You paste and fill down |
| Builds pivot table | ✅ Automatic | ✍️ You build it using Copilot's layout |
| Explains formulas, gives insights | ✅ | ✅ Same |
| Handles errors | Agent retries | You paste the error back and ask for a fix |
| What you learn | Prompting | Prompting **plus** checking the formula logic yourself |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Formula refers to row 2 or the wrong column | Remind Copilot: *"Headers are row 2, data starts row 3."* |
| `#VALUE!` in Pending Days | This is the text-date issue. See Exercise 3. |
| `#NAME?` after pasting | Curly quotes crept in. Retype the `"` characters in Excel. |
| Pivot shows *Count* instead of *Average* | Change it in **Value Field Settings → Average**. |
| Pivot includes the title or note text | Rebuild it from **A2:T27** only. |
| Copilot says it can't open the file | Re-attach it from OneDrive, or paste the relevant rows as text. |
| Copilot mixes up the two "Pending" meanings | Status = Pending is a column P value (6 cases). Breach Flag = Pending means TAT is blank (7 cases). |

---

## Further Reading

- [Microsoft Copilot overview: Basic vs Premium experiences](https://learn.microsoft.com/en-us/copilot/overview)
- [Microsoft 365 Copilot overview: in-app features for Basic](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-overview)
- [Microsoft 365 Copilot release notes: Edit with Copilot in Excel](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

*Bajaj Finance Limited | AI Academy — Risk Containment Unit (RCU) | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India***

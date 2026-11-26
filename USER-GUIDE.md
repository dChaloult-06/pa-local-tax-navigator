# PA Local Tax Navigator — User Guide

**For payroll professionals setting up or verifying Pennsylvania local tax configurations**

Built by Dorothy Chaloult, CPP · [linkedin.com/in/dorothy-chaloult-cpp](https://www.linkedin.com/in/dorothy-chaloult-cpp/)

---

## What This Tool Does

The PA Local Tax Navigator is a compliance reference and setup tool for payroll professionals working with Pennsylvania employees. It is designed to help you:

- **Look up and interpret DCED address search results** — and turn them into a payroll system setup directive
- **Understand Act 32 EIT and LST rules** — including the Higher-Of withholding mechanic, LST proration, and low-income exemptions
- **Navigate Philadelphia and Pittsburgh special rules** — Philadelphia operates entirely outside Act 32; Pittsburgh's EIT runs through Act 32, but its LST and Payroll Expense Tax are handled separately by the city
- **Handle out-of-state employees working in PA** — including the 880000 PSD code, PA–Maryland local exemptions, and courtesy withholding for PA residents working out-of-state

**What this tool does not do:**
- It does not replace the official DCED address search — you still run that first
- It does not file taxes, register accounts, or submit forms
- It does not provide legal or accounting advice

---

## How to Use the DCED Setup Lookup

The Lookup Tool is the first section in the navigator. It takes the raw results from the DCED address search and converts them into a complete payroll setup directive.

### Step 1 — Run the DCED Address Search

Go to the official DCED address search tool:

**[apps.dced.pa.gov/munstats-public/FindLocalTax.aspx](https://apps.dced.pa.gov/munstats-public/FindLocalTax.aspx)**

Enter the employee's **home address** and **work address** in the respective fields and click **View Information**.

> **Important:** Enter the physical work location — the actual address where the employee reports to work — not the employer's mailing address or corporate headquarters if different.

### Step 2 — Copy the Results

When the results page loads:

1. Click anywhere on the results page
2. Press **Ctrl+A** (Windows) or **Cmd+A** (Mac) to select all text
3. Press **Ctrl+C** / **Cmd+C** to copy

You are copying the entire page — navigation, addresses, rates, and collector information. The tool is designed to extract only the relevant data.

### Step 3 — Set Pay Frequency

In the navigator, select the employee's pay frequency before pasting:

- **Weekly** (52 periods)
- **Bi-Weekly** (26 periods)
- **Semi-Monthly** (24 periods)
- **Monthly** (12 periods)

This is used to calculate the correct per-period LST withholding amount. It can be changed and the directive re-generated if needed.

### Step 4 — Paste and Generate

Paste the copied text into the text box and click **Parse and Generate Directive**.

The tool will extract:
- Home PSD code and resident EIT rates (municipal and school district)
- Work PSD code, non-resident EIT rate, and LST amounts
- LST low-income exemption thresholds
- All tax collectors shown in the results (name, address, phone, and website where available)

### Step 5 — Review the Output

The directive shows:

| Section | What It Contains |
|---|---|
| **Rate boxes** | EIT rate to withhold and total annual LST — at a glance |
| **Setup Values** | Home PSD, Work PSD, component rates, and withholding directive |
| **LST Per-Period** | Per-period LST amount calculated for your selected pay frequency |
| **Tax Collectors** | All collectors from your DCED results, deduplicated if the same collector handles multiple tax types |
| **Employer Action Steps** | Five numbered steps to complete the employee's PA local tax setup |

> **Note on collectors with no website:** Some local Act 511 collectors are small municipal offices with no web presence. When the DCED results include a collector without a website, the tool shows the name, address, and phone number — use those to contact the collector directly for registration.

---

## How to Read the Setup Directive

### The Higher-Of Rule

Pennsylvania Act 32 requires employers to withhold the **higher** of two rates:

- The employee's **Total Resident EIT Rate** (home municipality + home school district)
- The **Work Location Non-Resident EIT Rate**

The DCED results already do this calculation — the "Total Taxes to be Withheld" box in the DCED output shows the correct withholding rate. The navigator confirms and displays this rate with the supporting math.

**Example from the directive:**
```
Withhold EIT: 1.000% — Resident rate
  Resident EIT: 1.000% (0.500% municipal + 0.500% school district)
  Non-Resident EIT: 0.000%
  Higher-Of: Resident rate wins → withhold 1.000%
```

### LST Per-Period Calculation

When the combined LST exceeds $10/year, it must be prorated across all pay periods — it cannot be collected as a lump sum. The tool calculates this automatically and rounds down to the nearest cent per period.

**Example:**
```
Annual LST: $52.00
Pay periods: 26 (Bi-Weekly)
Per-period amount: $2.00 (rounded down)
```

If the combined LST is $10 or less, it may be collected as a lump sum in the first paycheck of the year.

### LST Low-Income Exemption

When the setup directive includes an LST exemption alert, the jurisdiction requires employers to make **Form LST-E** available to employees who may qualify. The threshold shown in the alert comes directly from the DCED results.

**Key rules:**
- Make the form available at hire — do not wait for the employee to ask
- Do not stop withholding until you receive a completed, valid LST-E
- Resume withholding if the employee notifies you their circumstances have changed

### Special Rule Alerts

If the work PSD code triggers a special rule, a colored alert appears at the top of the directive:

| Alert | Meaning |
|---|---|
| **Philadelphia** | PSD starts with 51 — standard Act 32 EIT does not apply. Apply Philadelphia Wage Tax instead (3.735% resident / 3.425% non-resident, eff. July 1, 2026). Philadelphia levies no LST. |
| **Pittsburgh** | Work PSD is 700102 (Pittsburgh S D, Allegheny Central TCD) or 730105 (Baldwin-Whitehall S D, Allegheny Southwest TCD). The alert shows the resident EIT and LST split for that code. Employer also owes Payroll Expense Tax (0.55%). |

---

## Quick Reference: When to Use Each Section

| You need to... | Use this section |
|---|---|
| Set up a new PA employee from scratch | DCED Setup Lookup |
| Verify an existing employee's setup | DCED Setup Lookup (compare directive to current config) |
| Understand the Higher-Of rule | Act 32 / EIT |
| Calculate LST per-period manually | Local Services Tax |
| Set up a Philadelphia employee | Philadelphia |
| Set up a Pittsburgh worksite | Pittsburgh |
| Handle an employee who lives in NJ or MD and works in PA | Out-of-State |
| Handle a PA resident working for an out-of-state employer | Out-of-State |
| Understand the PA–Maryland TCD exemption | Out-of-State → PA–Maryland Deep Dive tab |
| Find collector registration links | Tax Collectors |

---

## Glossary

**Act 32**
Pennsylvania Act 32 of 2008. The statute that standardized local EIT collection into 69 Tax Collection Districts (TCDs), effective January 1, 2012. Philadelphia operates outside this framework. Pittsburgh's EIT is collected under Act 32 through the Allegheny Central and Southwest TCDs; only its LST and Payroll Expense Tax are handled separately by the city.

**EIT (Earned Income Tax)**
Pennsylvania's local earned income tax, levied by municipalities and school districts. Governed by Act 32. Applies to wages, salaries, and net profits from self-employment. Separate from PA state income tax (3.07% flat rate).

**Higher-Of Rule**
Act 32's core withholding mechanic: compare the employee's Total Resident EIT Rate to the Work Location Non-Resident EIT Rate and withhold the higher of the two. Remit to the work-location TCD collector.

**LST (Local Services Tax)**
A flat annual fee for the privilege of working in a jurisdiction. Separate from EIT and governed by its own statute. Based on work location only. Standard maximum is $52/year; in the 2026 DCED register only Harrisburg and Scranton exceed it ($156/year). Philadelphia levies no LST. Must be prorated across pay periods when the combined rate exceeds $10/year.

**PSD Code**
Political Subdivision Code. A six-digit number that uniquely identifies each Pennsylvania municipality and school district. Required for the Residency Certification Form and payroll system configuration. Lookup via the DCED Address Search.

**TCD (Tax Collection District)**
One of Pennsylvania's 69 regional collection zones, each served by a single contracted tax collector. The TCD collector receives employer remittances and distributes resident portions to the correct home municipalities.

**880000**
The standard out-of-state PSD code used when an employee lives outside Pennsylvania. Set the Resident PSD Code to 880000 and Resident EIT Rate to 0% on the Residency Certification Form. The employee is still subject to the Work Location Non-Resident EIT Rate and LST.

**Residency Certification Form (DCED-CLGS-32-6)**
Required from every PA employee at hire and upon any address change. Captures home and work PSD codes and EIT rates. Must be retained by the employer.

**Courtesy Withholding**
When an out-of-state employer voluntarily withholds PA local EIT for a PA resident employee. Not legally required, but recommended by DCED. If the employer does not withhold, the employee must make quarterly estimated payments to their home TCD collector.

**Act 48**
Requires all PA employers — including those outside Philadelphia — to withhold Philadelphia's resident Wage Tax from employees who live in Philadelphia, regardless of where the worksite is located within PA.

**PA–MD Local Exemption**
Certain Pennsylvania TCDs have agreed — through legal settlements or local ordinance — to exempt Maryland residents from local nonresident EIT withholding. This is a TCD-level determination. York and Adams Counties are confirmed exempt via a 1981 legal settlement. LST is never covered by this exemption.

---

## Important Notes on Accuracy

**Philadelphia Wage Tax rates change July 1 each year.** The rates shown in this tool (3.735% resident / 3.425% non-resident) are effective July 1, 2026. Always verify current rates at the [Philadelphia Department of Revenue](https://www.phila.gov/services/payments-assistance-taxes/taxes/business-taxes/business-taxes-by-type/wage-tax-employers/) before configuring payroll.

**DCED Address Search is the authoritative source for PSD codes and rates.** This tool interprets and explains the DCED output — it does not replace the lookup. Always run the official search for each employee.

**Pittsburgh has two PSD codes.** Most of the city is PSD 700102 (Pittsburgh S D, 3.0% resident EIT, $52 municipal LST). The Baldwin-Whitehall S D portion is PSD 730105 (1.5% resident EIT, $47 municipal + $5 school district LST). Always confirm the code with the DCED Address Search.

**Collector assignments change.** TCDs periodically change or re-bid their collector contracts. If a collector name in the directive doesn't match your existing records, verify via the DCED Address Search or contact the TCD directly.

**This tool is a reference, not legal advice.** For complex multi-state situations, expatriate employees, or ambiguous residency questions, consult a qualified payroll tax advisor.

---

## Official Sources

| Resource | Link |
|---|---|
| DCED Find Local Tax (Address Search) | [apps.dced.pa.gov/munstats-public/FindLocalTax.aspx](https://apps.dced.pa.gov/munstats-public/FindLocalTax.aspx) |
| DCED Local Income Tax Information | [dced.pa.gov/local-government/local-income-tax-information/](https://dced.pa.gov/local-government/local-income-tax-information/) |
| DCED Local Withholding Tax FAQs | [dced.pa.gov/local-government/local-income-tax-information/local-withholding-tax-faqs/](https://dced.pa.gov/local-government/local-income-tax-information/local-withholding-tax-faqs/) |
| Residency Certification Form (DCED-CLGS-32-6) | [dced.pa.gov/download/residency-certification-form...](https://dced.pa.gov/download/residency-certification-form-local-earned-income-tax-withholding-pdf/?wpdmdl=57773) |
| LST-E Exemption Certificate | [dced.pa.gov/download/taxpayer-application-for-exemption...](https://dced.pa.gov/download/taxpayer-application-for-exemption-from-local-services-tax-lst/?wpdmdl=56757) |
| Philadelphia Wage Tax (Employer) | [phila.gov/services/.../wage-tax-employers/](https://www.phila.gov/services/payments-assistance-taxes/taxes/business-taxes/business-taxes-by-type/wage-tax-employers/) |
| Pittsburgh Tax Forms | [pittsburghpa.gov/City-Government/Finance-Budget/Taxes/Tax-Forms](https://www.pittsburghpa.gov/City-Government/Finance-Budget/Taxes/Tax-Forms) |
| York Adams Tax Bureau | [yatb.com](https://yatb.com/) |
| PA Form REV-419 | [revenue.pa.gov/.../rev-419.pdf](https://www.revenue.pa.gov/FormsandPublications/FormsforIndividuals/PIT/Documents/rev-419.pdf) |
| Maryland Form MW507 | [marylandcomptroller.gov/.../MW507.pdf](https://www.marylandcomptroller.gov/content/dam/mdcomp/tax/forms/2026/mw507.pdf) |
| Maryland Form 502CR | [marylandcomptroller.gov/.../502cr.pdf](https://www.marylandcomptroller.gov/content/dam/mdcomp/tax/forms/2025/502cr.pdf) |

---

*This guide is maintained by Dorothy Chaloult, CPP. For questions or corrections, connect on [LinkedIn](https://www.linkedin.com/in/dorothy-chaloult-cpp/).*

*For informational use only. This guide does not constitute legal, tax, or accounting advice.*

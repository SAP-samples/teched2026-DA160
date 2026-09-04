# Instructor notes — DA160 (45–60 minutes)

Attendee path is the exercise READMEs. This page is for the room, not for participants to follow. Expected outcomes: [exercises/ex_solutions/README.md](exercises/ex_solutions/README.md).

## Timing (40 laptops, 2 people each)

| Minutes | What | Attendee page |
|---------|------|----------------|
| 0–5 | Chrome, Hub URL, desk credentials | [exercises/ex0](exercises/ex0/README.md) |
| 5–22 | Load `SAP_Contact.csv` (Upload → Map → Define → Review, **Partial Update**, **LOAD DATA**) | [exercises/ex1](exercises/ex1/README.md) |
| 22–35 | One Hub search (Organization + Source System Name equals Finance + Name contains Lab) | [exercises/ex2](exercises/ex2/README.md) |
| 35–55 | Potential matches: merge one pair, Not a Match one pair | [exercises/ex3](exercises/ex3/README.md) |

Use the platform overview in [exercises/ex0](exercises/ex0/README.md) as a **2–3 minute talk** (or pre-read). Do not have the room read it during the lab.

## What this workshop is (and is not)

Hands-on core is steward work in Hub: load, search, match/merge.

Do **not** run the 5-day implementation bootcamp in this room: APIs/Postman, L3 modeling, RDM, match-rule builder, survivorship config, workflows, Reltio Integration Hub, exams, or Snowflake zero-copy / Reltio Intelligent 360 configuration.

## Environment to confirm before the session

- One tenant per laptop; Chrome; desk-id credentials
- `SAP_Contact.csv`, optional `SAP_Org.csv`, `Load_Mappings_Ops.xlsx` on each laptop (or a shared path you announce)
- Tenants either include the Fluor (or equivalent) potential-match dataset for Exercise 3, **or** attendees only merge on data from Exercise 1
- Confirm the Contact entity-type **label** in the tenant (Contact vs Individual) and announce it before Exercise 1
- Confirm whether **Source System Name** `Finance` and **Name** containing `Lab` exist; if not, announce a fallback query from `SAP_Org.csv`
- No Postman

Do not put tenant passwords or tokens in this repository.

## Data files

Student files come from `Bootcamp_Student_Resources.zip`. They are **not** in this GitHub repository (PII and mapping ownership). Copy them to each laptop before the session. See [data/README.md](data/README.md).

## Screenshots

Exercise pages are written as a numbered click path. Product screenshots are not in the repo yet. Capture them on a workshop tenant and drop PNGs into each exercise `images/` folder. Suggested filenames:

| File | What to capture |
|------|-----------------|
| `exercises/ex0/images/01-hub-search.png` | Hub Search after successful sign-in |
| `exercises/ex1/images/01-load-data-entities.png` | Data Loader **LOAD DATA** → **Entities** |
| `exercises/ex1/images/02-upload.png` | Upload: job name, entity type, CSV selected |
| `exercises/ex1/images/03-map.png` | Map Attributes with at least one mapped column and a crosswalk |
| `exercises/ex1/images/04-define-partial.png` | Define: **Partial Update** selected |
| `exercises/ex1/images/05-review-load.png` | Review with **LOAD DATA** |
| `exercises/ex1/images/06-job-completed.png` | Job Status **COMPLETED** with loaded count |
| `exercises/ex2/images/01-quick-filter-org.png` | Quick Filters with **Organization** selected |
| `exercises/ex2/images/02-advanced-search.png` | Advanced Search: Finance + Lab |
| `exercises/ex2/images/03-profile-sources.png` | Organization profile showing sources / crosswalks |
| `exercises/ex3/images/01-potential-matches.png` | Potential Matches perspective, side by side |
| `exercises/ex3/images/02-merge.png` | **Merge** on a match pair |
| `exercises/ex3/images/03-not-a-match.png` | **Not a Match** on a distinct pair |
| `exercises/ex3/images/04-merged-profile.png` | Surviving profile with multiple crosswalks |

Then add `![](./images/<file>.png)` under the matching step.

## Floor helpers — common stuck points

- Sign-in fails: wrong desk-id user, or Hub URL for a different tenant
- Data Loader job fails: source / crosswalk not mapped; wrong entity type; **Full Update** chosen by mistake
- Search returns zero: Finance / Lab not on this tenant — give the fallback query
- No potential matches: training dataset missing — use Exercise 1 contacts/orgs only; do not invent Fluor data
- Accidental merge: **Unmerge** on the surviving profile, then retry

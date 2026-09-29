# Exercise 3 — Match, merge, and Not a Match (20 min)

SAP TechEd 2026, Hands-On Workshop: DA160

**Hands-on**

In this exercise you unify profiles: review **potential matches**, **merge** records that are the same real-world organization, and mark pairs that are **not** the same so the engine does not keep suggesting them.

## Why this step exists

Data unification in Reltio is three related processes:

| Process | What it does |
|---------|----------------|
| **Match** | Identify entities that represent the same real-world object |
| **Merge** | Combine matched entities and keep all source crosswalks on one profile |
| **Survivorship** | Choose which value is shown for each attribute on the **best-version profile** |

You are not configuring match rules or survivorship in this workshop. You are doing the steward job: decide on **potential matches** the engine was not confident enough to merge automatically.

Human **Not a Match** outranks the engine. If you mark two profiles Not a Match, later attribute edits will not put that pair back on your queue.

> [!TIP]
> Do not merge on name alone. Look for a **critical attribute** — a conflict that proves two similar names are different people or companies (different legal entities, strongly different identifiers, father/son, and similar cases).

## Exercise 3.1 — Find potential matches

1. Open **Search**.
2. In **Quick Filters**, set entity type to **Organization**.
3. Filter or sort so you can see organizations with **potential matches**. If the tenant shows a **Potential Matches** facet or column, use it (three or more if that column is available).

Then pick **one** path:

**Training-dataset path:** If the instructor confirmed the training dataset is on this tenant, search for **Pacific Rim Packaging**.

**Load-only path:** If the tenant only has data from Exercise 1, pick any organization that shows potential matches from your load (or from seed data already on the tenant).

## Exercise 3.2 — Review side by side

1. Open the profile.
2. In the left navigation, select **Profile** → **Potential Matches**.
3. Compare the main profile with the suggested matches. Matching attribute values are highlighted. If a **Relevance score** is shown, use it as a hint, not as a substitute for reading the attributes.
4. Look at more than the name: address, identifiers, and **source**. A similar name with a conflicting killer attribute is often **not** the same organization.

By default the perspective shows a small set of comparison profiles. You can select additional potential matches if you need them.

## Exercise 3.3 — Merge and Not a Match

On a comparison column, hover over the profile name and use the actions at the top of the table:

- **Merge** — combine that profile into the main entity. The contributor no longer exists as a separate profile; its crosswalks move to the survivor.
- **Not a Match** — declare they are different. The profile leaves this list and appears on the **Not a Match** tab.

> [!WARNING]
> **Merge** and **Not a Match** at the top of the table apply to **all** profiles on the page. For this workshop, act on **one pair at a time**.

### Training-dataset path (Pacific Rim Packaging)

The bootcamp challenge: **Pacific Rim Packaging** starts related to three other profiles (four profiles in total):

- 1 named Pacific Rim Packaging Co
- 1 named PACIFIC RIM PACKAGING
- 1 named Pacific Rim Packaging Incorporated
- 1 named Pacific Rim Packaging LLC

**Goal:** end with **three** profiles — one for each legal name — and those three marked **Not a Match** with each other.

1. **Merge** two Pacific Rim Packaging profiles into one.
3. Leave one as its own profile.
4. Mark one pair **Not a Match**.

If you merge the wrong pair, **unmerge** on the surviving profile and retry. Unmerge is expected; it also writes Not a Match for that split.

### Load-only path (no Fluor data)

1. Merge **one** pair you are confident is the same organization (or the same contact, if you are working from Exercise 1 contacts).
2. Mark **one** pair **Not a Match**.
3. Stop. Do not empty the whole queue.

## Exercise 3.4 — Confirm the best-version profile

1. Open the surviving merged profile.
2. Confirm multiple **crosswalks / sources** are present. Merge keeps lineage; it does not throw sources away.
3. Skim operational values (name, address). Survivorship already chose what is displayed; you are not editing rules today.

That merged profile is the trusted record downstream apps, analytics, and AI agents should use — the same idea as a **data product**, not a spreadsheet extract.

## Summary

You should be able to explain, in one sentence each:

- What a potential match is (engine unsure; steward decides)
- What merge does (one profile, many sources)
- Why Not a Match matters (permanent steward override)

You have finished the hands-on path for this session.

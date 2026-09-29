# Exercise 2 — Search in Hub (15 min)

SAP TechEd 2026, Hands-On Workshop: DA160

**Hands-on**

In this exercise you find the organizations (and contacts) in your tenant the way a steward does: quick filter first, then a precise advanced query. This workshop keeps **one** search challenge.

If Exercise 1 is still running, wait until the Data Loader job is completed before you search for the contacts you just loaded.

## How Hub Search is laid out

The Search page has three areas:

- **Left** — **Advanced Search** (query builder) and **Quick Filters** (entity type and attribute facets)
- **Top** — current criteria, saved / recent searches, share, and actions such as load and export
- **Center** — results as a table or a list, with the total profile count

**Global search** looks across attribute values when you only have a keyword. **Quick Filters** limit by entity type. **Advanced Search** combines conditions (`equals`, `contains`, missing values, and more). Every attribute is indexed, so you can filter on what you see.

## Exercise 2.1 — Open Search and filter to Organization

1. In Hub, select **Search**.
2. In **Quick Filters**, under **Entity Types**, select **Organization**.
3. Confirm the result count changes. You are no longer looking at all types at once.

> [!NOTE]
> The total count on Search includes all entity types until you filter. After you select **Organization**, the count should drop.

## Exercise 2.2 — Build one precise query

Build **this** search. Do not skip filters.

1. Keep entity type **Organization**.
2. Open **Advanced Search** on the left panel.
3. Add a condition: **Source System Name** `equals` **SAP**.
4. Add a second condition (combine with **And**): **Name** `contains` **Lab**.
5. Run the search.

You should see **Redwood Data Labs**. That organization is already in the tenant for every participant. The list should be short, not the whole tenant.

> [!NOTE]
> `equals` is an exact match (not case sensitive). `contains` finds the value as a substring inside the attribute.

If you do not see **Redwood Data Labs**, check that the entity type is still **Organization**, the source is **SAP**, and **Name** `contains` **Lab**. Then tell a helper.

## Exercise 2.3 — Read a profile

1. Open one organization from the results.
2. Note the **sources / crosswalks** on the profile (where the data came from). That lineage is what merge keeps when you unify duplicates in Exercise 3.
3. Return to **Search**.

**Optional:** If you have two minutes, switch the entity type quick filter to **Contact** (or **Individual**) and use global search with a last name from `SAP_Contact.csv` to prove your load from Exercise 1 is searchable.

## Summary

You can:

- Filter Search by entity type
- Combine two attribute conditions in Advanced Search
- Open a profile from results and see its sources

Continue to [Exercise 3 — Match, merge, and Not a Match](../ex3/README.md).

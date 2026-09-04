# Exercise 1 — Load contacts with Console Data Loader (20 min)

SAP TechEd 2026, Hands-On Workshop: DA160

**Hands-on**

In this exercise you ingest a CSV of contacts into your workshop tenant using **Data Loader** in Console. You complete the same four stages the product uses for every file load: **Upload**, **Map**, **Define**, **Review**.

If you have not signed in yet, complete [Getting Started](../ex0/README.md) first.

> [!NOTE]
> The instructor announces the folder that contains `SAP_Contact.csv` and `Load_Mappings_Ops.xlsx`. Use those files. Do not invent a spreadsheet.

## What you will do

Data loading is how source records become entities in Reltio. Console Data Loader is the batch UI path. API and streaming exist; they are out of scope today.

When a job updates **existing** records, the **record update preference** controls what happens to attributes that are **not** in your file:

| Preference | What it does | Use when |
|------------|--------------|----------|
| **Partial Update** | Changes only mapped attributes. Leaves unmapped attributes as they are. | Almost always, including a first load |
| **Full Update** | Overwrites the record. Unmapped attributes can become empty. | Only when you intend to wipe values that are missing from the file |

For this workshop, always choose **Partial Update**.

## Exercise 1.1 — Open Data Loader

1. In Hub, open the **Applications** menu and select **Console**.
2. In the **Tenant Management** section, select **Data Loader**.
3. On the **Job Definition** tab, select **LOAD DATA**, then **Entities**.

You are now on the entity data-load page. The wizard is **Upload** → **Map** → **Define** → **Review**.

## Exercise 1.2 — Upload

On the **Upload** section, fill in the following details, then select **CONTINUE**:

1. In **Job definition Name**, enter a name you can find later. Use your desk number, for example `DeskNN-SAP-Contact`.
2. In **Entity type**, select **Contact**.
3. Leave the source as **My Computer** (the default).
4. For file type, select **CSV**.
5. Select the **First row is a header** checkbox.
6. For the delimiter, select **Comma (,)**.
7. Select **BROWSE FILE** and choose **`SAP_Contact.csv`** from the workshop data folder.
8. Confirm the file preview looks like contact rows (names, source identifiers), not a mapping spreadsheet.
9. Select **CONTINUE**.

> [!WARNING]
> Local uploads must stay under 50 MB. The workshop CSV is well under that limit. If the preview looks empty, check that **First row is a header** is selected and that you picked the CSV, not the XLSX.

## Exercise 1.3 — Map

On the **Map** section you map CSV columns to attributes in the tenant data model, including the **crosswalk** (source system + source ID) so Reltio can recognize the same record on later loads.

1. Select **Map Attributes**.
2. Select **Select Mapping**, then **New Mapping** (unless the instructor tells you to reuse a saved mapping).
3. Map each required column using **`Load_Mappings_Ops.xlsx`** as the reference. Typical mappings include name fields, identifiers, and the source / crosswalk type. Do not leave the crosswalk blank.
4. If the tenant offers AI-assisted auto-mapping, you may use it, then **verify** every mapping against the spreadsheet before you continue.
5. Select **CONTINUE**.

> [!TIP]
> If a required attribute is still unmapped, Data Loader warns you when you reach **Define**. Return to **Map** and finish the mapping rather than switching to **Full Update**.

## Exercise 1.4 — Define

On the **Define** section you set how the job writes to existing profiles.

1. Select **Partial Update**.
2. Leave **Execute LCA** at the default (enabled) unless the instructor tells you otherwise.
3. Leave **Enable Data Change Request (DCR)** cleared. This workshop loads data directly; you do not send each row through an approval inbox.
4. Leave other advanced options at the instructor’s defaults.
5. Select **CONTINUE**.

## Exercise 1.5 — Review and start

On the **Review** page you should see file details, a mapping summary, and job information.

1. Check entity type, file name, mapping, and **Partial Update**.
2. If something is wrong, select **Edit mapping** or **Edit job**, fix it, and return to **Review**.
3. Select **LOAD DATA** (not **SUGGEST DATA LOAD** — that path creates DCRs instead of loading).
4. Wait on **Job Status** until the job is completed. Open the completed job and note how many records loaded and how many failed.

> [!WARNING]
> If the job fails, do not re-run blindly. Check mapping and crosswalk / source type first, then ask a floor helper. A second load with a bad mapping can create extra profiles.

## If you finish early

**Optional:** Load **`SAP_Org.csv`** with the same four stages:

- Entity type: **Organization**
- Record update preference: **Partial Update**
- Mapping: still **`Load_Mappings_Ops.xlsx`**
- Job name example: `DeskNN-SAP-Org`

## Summary

You should have:

- A completed Data Loader job for `SAP_Contact.csv`
- Contact profiles you can find in Hub Search (Exercise 2)

Continue to [Exercise 2 — Search in Hub](../ex2/README.md).

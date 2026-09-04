# Getting Started — Prepare your working environment (5 min)

SAP TechEd 2026, Hands-On Workshop: **DA160 — Build Real-Time, Unified Data Products for Agentic AI with SAP Reltio**

You use labels throughout the exercises to tell reading from doing:

- **Hands-on:** Steps you perform in the tenant on your laptop.
- **Read-only:** Background so load, search, and match make sense. The instructor covers this in 2–3 minutes. Do not read it during the timed lab.

## Step 1 — Sign in to Hub (5 min)

**Hands-on**

1. Use **Google Chrome** (current version).
2. Open the **Hub URL** on your **desk card** (one tenant per laptop; two people share the screen).
3. Sign in with the credentials on your **desk card**.

   - User ID: \
   - Password: \

4. Confirm you can see Hub **Search**. If you cannot, raise a hand before Exercise 1.
5. Confirm the workshop data folder is available (the instructor announces the path). You need **`SAP_Contact.csv`** for Exercise 1. You also need **`Load_Mappings_Ops.xlsx`** as the mapping reference.

> [!NOTE]
> Replace the Hub URL and credentials with the values on your desk card. Do not share passwords with other desks.

> [!TIP]
> If Hub asks you to pick a tenant, choose the tenant ID printed on the desk card.

When you can see Search, go to [Exercise 1 — Load contacts with Console Data Loader](../ex1/README.md). The rest of this page is optional reading.

---

# Overview — The SAP Reltio platform and its components

**Read-only** (instructor talk or pre-read)

This overview introduces how the pieces fit together so load, search, and match make sense.

## Learning objectives

After this overview you can:

- Recognize the cost of scattered, duplicated data on the business and on customers
- Explain how **Reltio Multidomain MDM** creates one trusted profile for every customer, supplier, and product
- Describe how **Reltio Data Cloud** unifies, governs, secures, and delivers that data at enterprise scale
- Describe how **Reltio AgentFlow** and **Reltio MCP Server** bring governed AI agents into operations

## The problem

Critical data — customers, suppliers, products, and the relationships between them — is scattered across systems that do not talk to each other (CRM, ERP, commerce, service, marketing, and more). Each system quietly creates its own version of the same entity. The same person can exist as five records, and none of the systems know it.

That shows up as:

- The same question asked twice, and a different answer from web chat than from the call center
- Marketing that ignores an opt-out because another system never saw it
- AI that acts on a fragmented, unreliable picture of the business

This is a trust problem. Master data management exists to close it.

### Three kinds of data

| Building block | What it is | Examples |
|----------------|------------|----------|
| **Entities** | People, organizations, places, and things | Customer, supplier, product, location |
| **Relationships** | How entities connect | Contact who works at a company; product on an account |
| **Interactions** | What actually happened | Purchase, service call, claim |

Most organizations can see pieces of this in individual applications. Few have the full connected picture. That connected picture is what the platform is built to create.

### What poor data actually costs

Figures used in the Reltio Basics training:

- Average cost of poor data quality: **$13.1M per year** per organization ([Gartner](https://www.gartner.com/smarterwithgartner/how-to-improve-your-data-quality))
- **94%** of organizations suspect their own customer and prospect data is inaccurate
- Duplication rates of **10–30%** are common without a data quality program

Every duplicate is a place where a person — or an AI agent — decides from an incomplete picture.

## How the pieces fit together

The platform is one connected stack, not five products you stitch together yourself.

```text
Reltio AgentFlow          governed AI agents + Reltio MCP Server
        │
Reltio Intelligent 360    relationships, interactions, grouping, segments
        │
Reltio Multidomain MDM    match, merge, cleanse, enrich → trusted profiles
```

- **Reltio Multidomain MDM** and **Reltio Intelligent 360** are the two core products that run on that platform.
- **Reltio AgentFlow** is the agentic layer on the same foundation. **Reltio MCP Server** is the open connection point for your own agents; it is included with Reltio Data Cloud.

## Reltio Multidomain MDM

**Reltio Multidomain Master Data Management** (Reltio Multidomain MDM) continuously unifies, cleanses, and enriches data from source systems. It resolves duplicates and builds **one trusted profile** — a trusted data foundation — for every customer, supplier, product, or location, in real time.

That profile is what operational systems, analytics, and AI agents should consume. If the foundation is shaky, everything built on it is shaky.

## Reltio Data Cloud

Reltio Data Cloud unifies, governs, secures, and delivers trusted data at enterprise scale. The capabilities below all sit on that platform.

### Integrating data: get it in, get it out

Customers connect sources through configuration rather than custom code — on-premises, private data centers, or public cloud (AWS, Google Cloud, Azure). After data is cleansed and unified, you can send it downstream as:

- File download
- Real-time and batch APIs
- Near real-time streaming

### Entity resolution

Entity resolution decides which records are the same person, company, or product. It has three parts:

1. **Matching**
   - Rule-based matching: your team defines what constitutes a match
   - **Reltio Flexible Entity Resolution Networks (FERN)**: an LLM-powered matching engine that finds matches rules alone would miss. FERN works **alongside** rule-based and manual matching; it does not replace them
2. **Survivorship** — configurable rules pick the best, most trustworthy value from each source, field by field, into the **best-version profile** (most recent, most complete, or most trusted source wins)
3. **Reltio ID** — one persistent identifier per resolved entity for life, even as source records come and go, so downstream systems have a stable reference

### Governance that stays on

Once data is unified, it has to stay trustworthy:

- Out-of-the-box workflows such as **Data Change Requests (DCR)**, **Potential Match Review**, and **Recommend Delete** — propose, review, approve before production
- Automated **data quality** dashboards (no separate project to stand up monitoring)
- Built-in **reference data management** (country codes, product types, and similar controlled lists) so reports add up across sources

### Data quality: built in, always on

Machine learning inspects incoming data for anomalies and drift. Interactive dashboards track completeness and uniqueness, with drill-down to where an issue occurred. Cleansing, standardization, and verification (including address and email formatting) run through built-in enrichment integrations so downstream systems receive higher-quality data with less manual effort.

### Faster time to value: velocity packs

**Velocity packs** are pre-configured, industry-specific packages: data model, relationships, match rules, reference data, and UI configuration from implementation best practices. You start from an industry kit and tailor it, instead of designing the model from a blank tenant.

## Context intelligence

Clean, unified data is necessary. It is not automatically enough for reliable AI.

Two organizations can use the same AI model and get very different results. The difference is whether the business has **connected context** the model can use: entities, relationships, transactions, and business rules tied together. Without that, the model guesses at meaning. With it, the model can reason from a complete picture of the business.

How the stack builds up to it:

1. Entity resolution identifies and merges duplicates
2. Reltio Multidomain MDM turns that into a trusted master view
3. Reltio Intelligent 360 unifies relationships, transactions, and interactions into real-time 360° profiles
4. Reltio AgentFlow turns that context into governed action

## Reltio AgentFlow and Reltio MCP Server

AI agents are only as good as the data they stand on. Homegrown agents that are not connected to trusted, governed data tend to stall in production: light on capability, heavy on risk.

**Reltio AgentFlow** brings governed agents into data governance and business operations. There are two ways in:

| Path | Who it is for | What you get |
|------|----------------|--------------|
| **Reltio AgentFlow** prebuilt agents | Teams that want Reltio-managed agents immediately | Point at jobs such as duplicate resolution; productive without a custom build |
| **Reltio MCP Server** | Teams building or orchestrating their own LLM agents | An open, standard connection to search, match, merge, and enrich against live governed data — hours instead of weeks of custom integration |

Most customers start with prebuilt agents and add Reltio MCP Server as custom agent use cases grow. Agents work from the current best-version profile, not a stale file extract.

### Governed by design

- Every agent action inherits existing **role-based access control** and **data masking** — nothing new to configure for the agent path
- Every agent call is **logged**, so risk and compliance teams have auditable evidence of how AI touched the data

That is what makes it reasonable to scale agents into sensitive domains instead of leaving them in a sandbox.

## Reltio Intelligent 360

A clean record tells you **who or what** something is. That is necessary and often not sufficient. A service rep can have the correct customer record and still miss the recent purchase, the open ticket, or the preferred channel. The record is accurate; the situation is invisible.

**Reltio Intelligent 360** closes that gap. It includes the trusted MDM foundation and adds business context: what is happening, why it matters, and what should happen next.

### What builds the context

- **Relationships** — how records connect (contact to household, supplier to product)
- **Grouping** — larger business structures (account hierarchies, provider networks)
- **Interactions and transactions** — what happened (call, claim, purchase)
- **Derived attributes and segmentation** — churn-risk score, high-value segment, next-best action

Together these turn a trusted record into a context-rich profile.

### Where it shows up

- Customer-facing teams see the full situation, not just a record
- Decision-makers can prioritize (for example a high-value customer who is also at risk of churn)
- AI agents and analytics work from a fuller, governed view instead of stale or disconnected data

## Recap

| You should now be able to… | The component that addresses it |
|----------------------------|----------------------------------|
| Name the cost of scattered, duplicated data | The business problem MDM exists to solve |
| Explain one trusted profile per customer, supplier, and product | Reltio Multidomain MDM |
| Describe unify / govern / secure / deliver at scale | Reltio Data Cloud |
| Explain why AI needs connected context, not only clean data | Context intelligence |
| Describe governed agents in operations | Reltio AgentFlow and Reltio MCP Server |
| Distinguish 360 context from MDM and from the platform | Reltio Intelligent 360 |

Every piece above is one connected platform. Continue to [Exercise 1 — Load contacts with Console Data Loader](../ex1/README.md).

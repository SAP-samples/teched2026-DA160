# Containing Files

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2026-DA160)](https://api.reuse.software/info/github.com/SAP-samples/teched2026-DA160)


1. The LICENSE file:
In most cases, the license for SAP sample projects is `Apache 2.0`.

2. The REUSE.toml file: 
The [Reuse Tool](https://reuse.software/) must be used for your samples project. You can find the REUSE.toml in the project initial. Please replace the parts inside the single angle quotation marks < > by the specific information for your repository.

3. The README.md file (this file):
Please edit this file as it is the primary description file for your project. You can find some placeholder titles for sections below.

# DA160 - Build Real-Time, Unified Data Products for Agentic AI with SAP Reltio

## Description

This repository contains the material for the SAP TechEd 2026 Hands-on Workshop **Build Real-Time, Unified Data Products for Agentic AI with SAP Reltio** (Session-ID DA160).

## Overview

Trusted AI starts with trusted data. In this workshop you learn how **SAP Reltio** in **SAP Business Data Cloud** unifies enterprise master data across SAP and third-party systems, complementing the SAP Master Data Governance application to improve data quality, enable Customer 360 scenarios, and deliver trusted, real-time data products for applications, analytics, and AI.

On your laptop you load master data into a dedicated SAP Reltio tenant, execute simple search queries, and unify duplicate profiles into a trusted record — the same steward path that feeds downstream apps, analytics, and AI agents.

Complete the exercises in order. The room is timed for **45–60 minutes** of hands-on (one tenant per laptop, two people per laptop).

## Requirements

The technical requirements to complete the exercises, including hardware and software, are taken care of by the systems provided for the in-person Hands-on Workshop.

- Google Chrome (current version)
- Desk credentials and tenant URL from the instructor
- Workshop data files on the laptop or the path the instructor announces (`SAP_Contact.csv`, mapping sheet)

Required configuration tasks are in [Getting Started](exercises/ex0/).

## Exercises

Complete the exercises in the sequence below. **Getting Started** must be first; Exercises 1, 2, and 3 depend on each other.

- [Getting Started — Prepare your working environment](exercises/ex0/)
  - [Sign in to Hub](exercises/ex0#step-1--sign-in-to-hub-5-min)
  - [Read-only: platform overview](exercises/ex0#overview--the-sap-reltio-platform-and-its-components) (instructor talk or pre-read)
- [Exercise 1 — Load contacts with Console Data Loader](exercises/ex1/README.md)
  - [1.1 Open Data Loader](exercises/ex1/README.md#exercise-11--open-data-loader)
  - [1.2 Upload](exercises/ex1/README.md#exercise-12--upload)
  - [1.3 Map](exercises/ex1/README.md#exercise-13--map)
  - [1.4 Define](exercises/ex1/README.md#exercise-14--define)
  - [1.5 Review and start](exercises/ex1/README.md#exercise-15--review-and-start)
- [Exercise 2 — Search in Hub](exercises/ex2/README.md)
  - [2.1 Filter to Organization](exercises/ex2/README.md#exercise-21--open-search-and-filter-to-organization)
  - [2.2 Build one precise query](exercises/ex2/README.md#exercise-22--build-one-precise-query)
  - [2.3 Read a profile](exercises/ex2/README.md#exercise-23--read-a-profile)
- [Exercise 3 — Match, merge, and Not a Match](exercises/ex3/README.md)
  - [3.1 Find potential matches](exercises/ex3/README.md#exercise-31--find-potential-matches)
  - [3.2 Review side by side](exercises/ex3/README.md#exercise-32--review-side-by-side)
  - [3.3 Merge and Not a Match](exercises/ex3/README.md#exercise-33--merge-and-not-a-match)
  - [3.4 Confirm the best-version profile](exercises/ex3/README.md#exercise-34--confirm-the-best-version-profile)

Instructors: see [INSTRUCTOR.md](INSTRUCTOR.md) for timing, environment checks, and what was cut from longer Reltio training.

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).

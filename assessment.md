# 📝 AlgoKit Documentation Survey & Assessment Report

**Date:** November 20, 2025
**Objective:** Baseline documentation status, tooling, and prioritize unification of Utils, Client-Generators, and Subscribers.

---

## 1. Documentation Status Report: Core Focus Areas (AC #1 & AC #2)

This table focuses on the core target repositories (utils, client-generators, and subscribers), summarizing the tooling found, build status, estimated coverage, and the resulting priority for unification effort.

| Repository                      | Language   | Category         | Tooling Status / Est. Coverage %      | **Priority Rank** | Next Step for Unification                                            |
| :------------------------------ | :--------- | :--------------- | :------------------------------------ | :---------------- | :------------------------------------------------------------------- |
| **algokit-utils-py**            | Python     | Utils            | **Sphinx Config Found** / 20%         | **Medium**        | Fix Sphinx configuration/build script to generate output.            |
| **algokit-utils-ts**            | TypeScript | Utils            | **TypeDoc Config Found** / 88%        | **High**          | **CRITICAL: Upgrade TypeDoc and plugins.** Implement CI/CD.          |
| **algokit-core**                | TypeScript | Utils            | **MD Book Config** / 30%              | **Medium**        | **DECISION POINT:** Migrate to TypeDoc or standardize MD Book setup. |
| **algokit-client-generator-py** | Python     | Client-Generator | **No Sphinx Config** / 15%            | **High**          | Install Sphinx and setup basic API documentation.                    |
| **algokit-client-generator-ts** | TypeScript | Client-Generator | **No TypeDoc Installed/Config** / 40% | **High**          | Install TypeDoc and establish basic configuration.                   |
| **algokit-subscriber-py**       | Python     | Subscriber       | **Sphinx Config Found** / 60%         | **Low**           | Implement automated deployment/hosting.                              |
| **algokit-subscriber-ts**       | TypeScript | Subscriber       | **TypeDoc Config Found** / 55%        | **High**          | **CRITICAL: Upgrade TypeDoc and plugins.** Implement CI/CD.          |
| **algokit-utils-ts-debug**      | TypeScript | Utils            | **TypeDoc Config Found** / 85%        | **High**          | **CRITICAL: Upgrade TypeDoc and plugins.** Implement CI/CD.          |

---

## 2. Prioritized List: Low-Hanging Fruit & Critical Tooling Updates (AC #2) 🥇

These repositories are prioritized for the first phase. The TS repos are moved to **High Priority** to address their outdated/broken tooling before they can be deployed.

1.  **`algokit-subscriber-py`** (Python Subscriber, 60% covered): **Tooling is functional.** Ready for hosting pipeline setup (Low-Hanging Fruit).
2.  **`algokit-utils-ts`** (TypeScript Utility, **88% covered**): **CRITICAL:** **Upgrade TypeDoc and replace `typedoc-plugin-markdown`** to enable functional builds. Once fixed, ready for hosting pipeline setup.
3.  **`algokit-subscriber-ts`** (TypeScript Subscriber, 55% covered): **CRITICAL:** **Upgrade TypeDoc and replace broken plugin** to enable functional builds. Once fixed, ready for hosting pipeline setup.
4.  **`algokit-utils-ts-debug`** (TypeScript Utility, 85% covered): **CRITICAL:** **Upgrade TypeDoc and replace broken plugin** to enable functional builds. Once fixed, ready for hosting pipeline setup.

---

## 3. Tool Confirmation & Unification Requirement (AC #3)

### Tool Status Summary:

- **TypeDoc (TS):** Tooling is present but **outdated and dysfunctional** due to dependency conflicts (e.g., `typedoc-plugin-markdown` breakage). This requires an immediate **upgrade and dependency cleanup** across all core TS libraries before hosting can be implemented.
  - **New Suggestion:** Adopt **`typedoc-plugin-coverage`** in CI/CD to ensure API documentation coverage remains at high levels (e.g., $80\%+$), enforcing quality across the unification effort.
- **Sphinx (Python):** Tooling is **inconsistent**. Some repos are functional (`algokit-subscriber-py`), while others require configuration debugging (`algokit-utils-py`) before they can be deployed.
- **MD Book:** The presence of MD Book in `algokit-core` introduces a deviation from the established TypeDoc/Sphinx standard. A decision on **migration vs. standardization** for MD Book is required for a complete unification plan.

### Standard Unification Requirement:

To achieve standard documentation (webpage) across the core repos, the single most critical next step is:

1.  **Tooling Remediation:** **Upgrade/Fix all TypeDoc installations and plugins** (TS repos).
2.  **Unified CI/CD:** Implement a unified build and hosting CI/CD pipeline (e.g., GH Pages) for both TypeDoc (TS) and Sphinx (Python) output for all functional repos.

---

Would you like me to draft the action plan for **upgrading the TypeDoc tooling** in **`algokit-utils-ts`**?

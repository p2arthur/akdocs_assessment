# 📝 AlgoKit Documentation Survey & Assessment Report

**Date:** November 20, 2025
**Objective:** Baseline documentation status, tooling, and prioritize unification of Utils, Client-Generators, and Subscribers.

---

## 1. Documentation Status Report: Core Focus Areas (AC #1 & AC #2)

This table summarizes the tooling found, estimated coverage, and the resulting priority for unification effort.

| Repository                      | Language   | Category         | Tooling Status / Est. Coverage %      | **Priority Rank** | Next Step for Unification                                                        |
| :------------------------------ | :--------- | :--------------- | :------------------------------------ | :---------------- | :------------------------------------------------------------------------------- |
| **algokit-utils-ts**            | TypeScript | Utils            | **TypeDoc Config Found** / 88%        | **Medium**        | **Action:** Update TypeDoc/plugins; update code to achieve 100% coverage.        |
| **algokit-utils-ts-debug**      | TypeScript | Utils            | **TypeDoc Config Found** / 100%       | **Medium**        | **Action:** Update TypeDoc/plugins; update code to achieve 100% coverage.        |
| **algokit-subscriber-ts**       | TypeScript | Subscriber       | **TypeDoc Config Found** / 95%        | **Medium**        | **Action:** Update TypeDoc/plugins; update code to achieve 100% coverage.        |
| **algokit-subscriber-py**       | Python     | Subscriber       | **Sphinx Config Found** / 60%         | **Medium**        | Run `coverage` builder; update code to achieve 100% coverage.                    |
| **algokit-utils-py**            | Python     | Utils            | **Sphinx Config Found** / 20%         | **Medium**        | update code for 100% coverage.                                                   |
| **algokit-core**                | TypeScript | Utils            | **MD Book Config** / 30%              | **Medium**        | **DECISION POINT:** Migrate to TypeDoc or standardize MD Book setup.             |
| **algokit-client-generator-ts** | TypeScript | Client-Generator | **No TypeDoc Installed/Config** / 40% | **Medium**        | Install TypeDoc, establish configuration, and update code for 100% coverage.     |
| **algokit-client-generator-py** | Python     | Client-Generator | **No Sphinx Config** / 15%            | **Medium**        | Install Sphinx and setup basic API documentation. Update code for 100% coverage. |

---

## 2. Prioritized List: Low-Hanging Fruit & Documentation Updates (AC #2) 🥇

We prioritize the TypeScript repositories first due to **team familiarity** and existing high coverage percentages, making the path to $100\%$ more straightforward, despite the initial package updates.

### Phase 1: Low-Hanging Fruit (TS Tooling Fixes & Coverage)

1.  **`algokit-utils-ts`** (TypeScript Utility, **88% covered**): **High Coverage.** Next step: **Update TypeDoc packages/plugins** and eliminate warnings to reach **100% coverage**.
2.  **`algokit-utils-ts-debug`** (TypeScript Utility, 100% covered): **High Coverage.** Next step: Update TypeDoc packages/plugins and update code to reach **100% coverage**.
3.  **`algokit-subscriber-ts`** (TypeScript Subscriber, 95% covered): Next step: Update TypeDoc packages/plugins and update code to reach **100% coverage**.

### Phase 2: Python Tooling & Coverage

4.  **`algokit-subscriber-py`** (Python Subscriber, 60% covered): **Tooling is functional.** Next step: Use the Sphinx `coverage` builder and update code to reach **100% documentation coverage**.

---

## 3. Tool Confirmation & Unification Requirement (AC #3)

### Tool Status Summary:

- **TypeDoc (TS):** Tooling requires **package updates** (e.g., resolving conflicts from outdated `typedoc-plugin-markdown`) across all core TS libraries to ensure functional builds.
  - **Recommendation:** Leverage **`typedoc-plugin-coverage`** to enforce and measure progress toward the **$100\%$ documentation coverage** goal.
- **Sphinx (Python):** Tooling setup is more complex, primarily relying on the **`autoapi`** extension.
  - **Key Action for Python:** The long **`autoapi_ignore`** list in `algokit-utils-py` must be reviewed and trimmed, as it currently bypasses documentation generation for large parts of the public API. Coverage checking relies on running the Sphinx build with the **`coverage`** builder or using the **`-W`** (warnings as errors) flag.
- **MD Book:** The presence of MD Book in `algokit-core` introduces a deviation. A decision on **migration vs. standardization** is required.

### Standard Unification Requirement:

The primary goal for unification is to ensure all core repositories can achieve and maintain **$100\%$ documentation coverage** via their respective generators (TypeDoc/Sphinx). The next steps are focused on **tooling fixes and code documentation updates**.

**Continuous Integration (CI) for Publishing:** **Crucial Step**
To make the documentation accessible and serve as the final, official source of truth, **all documentation-enabled repositories (TypeDoc and Sphinx)** must be configured to automatically publish their generated output to **GitHub Pages** upon successful merge to the `main` branch. This requires adding a dedicated CI workflow (e.g., `.github/workflows/docs.yml`) that uses the `actions/deploy-pages` action. This step ensures that the documentation is always current with the latest codebase.

---

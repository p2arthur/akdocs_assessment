# 📝 AlgoKit Documentation Survey & Assessment Report

**Date:** November 20, 2025
**Objective:** Baseline documentation status, tooling, and prioritize unification of Utils, Client-Generators, and Subscribers.

---

## 1. Documentation Status Report: Core Focus Areas (AC #1 & AC #2)

This table focuses on the core target repositories (utils, client-generators, and subscribers), summarizing the tooling found, build status, estimated coverage, and the resulting priority for unification effort.

| Repository                      | Language   | Category         | Tooling Status / Est. Coverage %      | **Priority Rank** | Next Step for Unification                                                        |
| :------------------------------ | :--------- | :--------------- | :------------------------------------ | :---------------- | :------------------------------------------------------------------------------- |
| **algokit-subscriber-py**       | Python     | Subscriber       | **Sphinx Config Found** / 60%         | **Low**           | Update Python code to achieve 100% coverage.                                     |
| **algokit-utils-ts**            | TypeScript | Utils            | **TypeDoc Config Found** / 88%        | **Medium**        | **Action:** Update TypeDoc/plugins, update code to achieve 100% coverage.        |
| **algokit-subscriber-ts**       | TypeScript | Subscriber       | **TypeDoc Config Found** / 55%        | **Medium**        | **Action:** Update TypeDoc/plugins, update code to achieve 100% coverage.        |
| **algokit-utils-ts-debug**      | TypeScript | Utils            | **TypeDoc Config Found** / 85%        | **Medium**        | **Action:** Update TypeDoc/plugins, update code to achieve 100% coverage.        |
| **algokit-utils-py**            | Python     | Utils            | **Sphinx Config Found** / 20%         | **Medium**        | Fix Sphinx configuration/build script. Update code for 100% coverage.            |
| **algokit-core**                | TypeScript | Utils            | **MD Book Config** / 30%              | **Medium**        | **DECISION POINT:** Migrate to TypeDoc or standardize MD Book setup.             |
| **algokit-client-generator-ts** | TypeScript | Client-Generator | **No TypeDoc Installed/Config** / 40% | **High**          | Install TypeDoc, establish configuration, and update code for 100% coverage.     |
| **algokit-client-generator-py** | Python     | Client-Generator | **No Sphinx Config** / 15%            | **High**          | Install Sphinx and setup basic API documentation. Update code for 100% coverage. |

---

## 2. Prioritized List: Low-Hanging Fruit & Documentation Updates (AC #2) 🥇

These repositories are prioritized for the first phase, focusing on those with existing, functional tooling first.

### Phase 1: Low-Hanging Fruit (Deployment Ready)

1.  **`algokit-subscriber-py`** (Python Subscriber, 60% covered): **Tooling is functional.** Next step: Update code to reach **100% documentation coverage**.
2.  **`algokit-utils-ts`** (TypeScript Utility, **88% covered**): **Tooling present.** Next step: Update TypeDoc packages/plugins and update code to reach **100% documentation coverage**.

### Phase 2: Tooling/Coverage Updates

3.  **`algokit-utils-ts-debug`** (TypeScript Utility, 85% covered): Update TypeDoc packages/plugins and update code to reach **100% documentation coverage**.
4.  **`algokit-subscriber-ts`** (TypeScript Subscriber, 55% covered): Update TypeDoc packages/plugins and update code to reach **100% documentation coverage**.

---

## 3. Tool Confirmation & Unification Requirement (AC #3)

### Tool Status Summary:

- **TypeDoc (TS):** Tooling is present but needs **package updates** across all core TS libraries to resolve dependency conflicts (e.g., outdated TypeDoc/plugin versions) and ensure functional builds.
  - **Recommendation:** Leverage **`typedoc-plugin-coverage`** to enforce and measure progress toward the **$100\%$ documentation coverage** goal.
- **Sphinx (Python):** Tooling is **inconsistent**. `algokit-subscriber-py` is ready for coverage work, while `algokit-utils-py` requires initial configuration fixes.
- **MD Book:** The presence of MD Book in `algokit-core` introduces a deviation. A decision on **migration vs. standardization** is required.

### Standard Unification Requirement:

The primary goal for unification is to ensure all core repositories can achieve and maintain **$100\%$ documentation coverage** via their respective generators (TypeDoc/Sphinx). The next steps are focused on **tooling fixes and code documentation updates**.

---

Would you like me to draft the specific steps for **updating the TypeDoc packages and achieving $100\%$ coverage** in the first TS priority item, **`algokit-utils-ts`**?

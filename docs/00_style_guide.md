# DOCUMENTATION STYLE GUIDE & STANDARD
## Formatting, Tone, and Structural Canons for This Project
### Foundational Engineering Specification (Document 00)
*Namespace: EOS • Owner: architecture-team*

---

## Navigation
**[Next: Document 01 (Manifest)](01_manifest.md) →**

- [0. Status, Scope, and Authority](#0-status-scope-and-authority)
- [1. Purpose](#1-purpose)
- [2. File Naming & Organization](#2-file-naming--organization)
- [3. Header & Metadata Standard](#3-header--metadata-standard)
- [4. Navigation & Interlinking](#4-navigation--interlinking)
- [5. Typography & Formatting](#5-typography--formatting)
- [6. Tone & Voice (RFC 2119)](#6-tone--voice-rfc-2119)
- [7. Section Standardization](#7-section-standardization)
- [8. Visual Representation Standard (C4 Model)](#8-visual-representation-standard-c4-model)
- [9. Summary](#9-summary)

---

## 0. Status, Scope, and Authority

**Status:** FOUNDATIONAL  
**Audience:** All Contributors  
**Change policy:**
- Append-only
- No silent edits

This document defines the canonical documentation standard for the EOS project.

[Back to top](#navigation)

---

## 1. Purpose

This document defines the canonical documentation style, formatting, navigation, and engineering writing standards for the EOS project.

All project documentation MUST adhere to these standards to maintain:
- **Readability:** Uniform visual hierarchy
- **Navigability:** Consistent cross-linking and anchoring
- **Authority:** High-grade engineering tone
- **Determinism:** Predictable document structure and formatting

[Back to top](#navigation)

---

## 2. File Naming & Organization

- **Naming Convention:** `dd_topic_slug.md`
  - `dd`: Two-digit zero-padded index (e.g. `00`, `01`, `10`)
  - `topic_slug`: Lowercase, underscore_separated
- **Examples:**
  - `00_style_guide.md`
  - `01_manifest.md`
  - `02_architecture.md`
  - `03_runtime_model.md`
- **Storage:** Documentation MUST reside under the `/docs` directory
- **Assets:** Images and diagrams MUST reside under `./assets/`

[Back to top](#navigation)

---

## 3. Header & Metadata Standard

Every document MUST begin with the following structure:

~~~markdown
# [DOCUMENT TITLE IN CAPS]
## [Descriptive Subtitle]
### Foundational Engineering Specification (Document XX)
*Namespace: EOS • Owner: architecture-team*

---
~~~

### Rules

- **H1:** Uppercase system-level or document-level concept
- **H2:** Human-readable descriptive subtitle
- **H3:** Canonical document identifier
- **Metadata:** Single italicized line

[Back to top](#navigation)

---

## 4. Navigation & Interlinking

### 4.1 Navigation Bar

Every document MUST contain a navigation block immediately following the header separator.

~~~markdown
## Navigation
**← [Prev: Document XX (Name)](xx_document.md) | [Next: Document YY (Name)](yy_document.md) →**
~~~

### 4.2 Table of Contents

Every document MUST include a manually maintained TOC.

### 4.3 Back Links

Every major `##` section MUST end with:

~~~markdown
[Back to top](#navigation)
~~~

[Back to top](#navigation)

---

## 5. Typography & Formatting

### 5.1 Code Blocks

- All code blocks MUST use triple-tilde fences (`~~~`)
- Every code block MUST specify a language
- Use `text` for logs or structured plaintext

### 5.2 Tables

- Use standard GitHub Flavored Markdown tables
- Left-align textual columns unless justified otherwise

### 5.3 Invariants & Warnings

Use standard Markdown emphasis instead of proprietary admonition blocks.

**Invariant Example:**

> **Hard Invariant:** Application state transitions MUST remain deterministic.

**Warning Example:**

> **Warning:** Violating this rule invalidates architectural guarantees.

[Back to top](#navigation)

---

## 6. Tone & Voice (RFC 2119)

Documentation MUST:
- Use RFC 2119 terminology (`MUST`, `SHOULD`, `MAY`, etc.)
- Avoid marketing language
- Avoid vague wording
- Prefer active voice
- Prefer explicit ownership and responsibility

**Bad:**

> The application should probably try to avoid inconsistent state.

**Good:**

> The synchronization layer MUST reject conflicting state mutations.

[Back to top](#navigation)

---

## 7. Section Standardization

### 7.1 Section 0 Requirement

Every document MUST begin with:

~~~markdown
## 0. Status, Scope, and Authority

**Status:** FOUNDATIONAL / DRAFT / DEPRECATED
**Audience:** [Target Roles]
**Change policy:**
- Append-only
- No silent edits
~~~

### 7.2 Closing Statement

Every document MUST end with:

~~~markdown
## X. Closing Statement

[Why this document matters.]

---

**END OF DOCUMENT XX**
~~~

[Back to top](#navigation)

---

## 8. Visual Representation Standard (C4 Model)

Architectural diagrams SHOULD follow the C4 model hierarchy and SHOULD be implemented using Mermaid.

### 8.1 Hierarchy Mapping

- **Level 1:** System Context
- **Level 2:** Containers / Runtime Services
- **Level 3:** Internal Components

### 8.2 Example

~~~mermaid
graph TD
    User((User))

    subgraph "EOS"
        App[Application Runtime]
        Sync[Sync Engine]
        Storage[Persistence Layer]
    end

    User --> App
    App --> Sync
    Sync --> Storage
~~~

[Back to top](#navigation)

---

## 9. Summary

This style guide defines the canonical engineering documentation standard for EOS:
1. Strict structure
2. Deterministic formatting
3. Explicit navigation
4. RFC 2119 normative language
5. Consistent architectural representation

Adherence is mandatory for all contributions.

---

**END OF DOCUMENT 00**

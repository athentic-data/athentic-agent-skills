# athentic-agent-skills

This repository contains agent skills for **Athentic Consulting** — reusable, installable skill modules that extend Claude's capabilities for specialized workflows. Each skill encapsulates domain expertise, structured rules, and step-by-step instructions so Claude can handle complex, repeatable tasks consistently and accurately.

---

## What is a Skill?

A skill is a `.skill` file you install into Claude via **Settings → Skills**. Once installed, Claude automatically applies it when it detects a relevant task — no extra prompting required. Skills are especially useful for standardizing processes that involve strict rules, templates, or domain-specific knowledge.

---

## Skills

### 1. `data-inventory-metadata-transform`

**Transforms Data Inventory files into structured metadata following Thai government standards มรด. 3-1 and มรด. 6 (DGA Data Governance Framework).**

This skill is designed for Thai public sector data governance work. When given an Excel-based Data Inventory, it maps each sheet to a standardized 16-field metadata record — covering dataset name, owning organization, contact, keywords, update frequency, data classification, storage format, and more.

**Key features:**
- One Excel sheet = one metadata output block
- Applies all มรด. mapping rules strictly (no hallucination, flags missing fields as `[INSERT INFORMATION]`)
- Handles conditional logic for data classification (Public / Internal / Personal Data)
- Normalizes database engine names to `"Database"`
- Converts `real-time` frequency to `"ตามเวลาจริง"` and cascades dependent fields correctly

**How to use:**
1. Install `data-inventory-metadata-transform.skill` via **Settings → Skills**
2. Upload your Data Inventory Excel file in a Claude conversation
3. Ask Claude to generate metadata — e.g., *"แปลง data inventory นี้เป็น metadata มรด."*
4. Claude will output one structured metadata block per sheet, ready for submission

---

*More skills coming soon.

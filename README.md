# claude-skill-legal-doc-advisor

A Claude Code skill that reviews legal documents from a founder-first perspective — like having a senior startup lawyer in the room before you sign.

## What it does
- Reviews any legal document across 8 structured sections
- Identifies hidden risks a non-lawyer would miss
- Explains every clause in plain English
- Flags power imbalances and one-sided terms
- Provides **redline-ready replacement language** — not vague suggestions
- Finds missing clauses that should be there but aren't
- Drafts worst-case scenarios with concrete dollar estimates
- Gives a clear verdict: safe to sign, sign with changes, or do not sign

## Works great for
- NDAs and confidentiality agreements
- SaaS / software agreements (MSA, Order Form, ToS)
- SAFE notes and convertible notes
- Term sheets (VC Series A+)
- Employment and contractor agreements
- Enterprise partnership and reseller agreements
- Data Processing Agreements (DPA)
- Any contract a founder is asked to sign

## Installation
```bash
# 1. Download the .skill file from Releases
# 2. Install it
mkdir -p ~/.claude/skills
unzip legal-doc-advisor.skill -d ~/.claude/skills/

# 3. Restart Claude Code
```

No additional dependencies — this skill does not require Playwright MCP.

## Usage

### Direct invocation
```
/legal-doc-advisor
```

### Natural language triggers
- *"Review this contract"*
- *"Is this safe to sign?"*
- *"Check this NDA"*
- *"What are the red flags in this agreement?"*
- *"Is this standard for a Series A term sheet?"*
- *"Should I sign this?"*

Claude will also trigger this skill automatically whenever you upload or share a legal document.

## How it works

```
STEP 0  Request document
        (PDF, DOCX, URL, Google Docs link, or pasted text)

        Then ask two context questions:
        - Are you signing this or self-reviewing before sending?
        - Anything specific to focus on?

STEP 1  Ingest the document
        Supports PDF, DOCX, URL, Google Docs, and raw text

STEP 2  Identify agreement type
        Loads the relevant clause checklist and red flag list

STEP 3  Full 8-section analysis:
        1. Executive Summary
        2. Critical Risk Areas (table with risk levels)
        3. Financial & Liability Exposure
        4. Control & Power Dynamics
        5. IP & Data Ownership
        6. Negotiation Strategy (with exact redline language)
        7. Worst-Case Scenarios
        8. Final Recommendation

STEP 4  Save polished output as .md and .html files
```

## Output

Every review produces:
- A **verdict**: 🟢 Safe to Sign / 🟡 Sign with Changes / 🔴 Do Not Sign Yet / ⛔ Do Not Sign
- A **risk table** with every flagged clause, quoted exactly, with risk level and suggested fix
- **Copy-paste redline language** — lawyer-quality replacement text for every must-fix clause
- **3 worst-case scenarios** grounded in the actual document
- Saved `.md` and `.html` report files

## Requirements
- Claude Code

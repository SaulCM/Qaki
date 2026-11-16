---
name: Bug report
about: Report a reproducible defect using the project defect form
title: "[Area] Short description of the defect"
labels: "bug"
assignees: ""
---

<!--
Defect intake form. GitHub Issues is the authoritative defect tracker for this project.

Source of truth:
- docs/05_qa_standards/BUG_REPORTING.md, section 16 (this form)
- docs/05_qa_standards/BUG_REPORTING.md, section 17.2 (labels)
- docs/05_qa_standards/BUG_REPORTING.md, sections 6, 8, 9, and 10 (title, severity, priority, status)

Mark a field Unknown, Not Available, or Not Applicable rather than inventing information.
Do not delete a section that applies.
-->

## Identification

- **Bug ID:** Assigned by GitHub as the issue number. Do not invent a `BUG-XXX` identifier unless a document needs an alias (see section 17.1).
- **Status:** Reported
- **Severity:** Critical / High / Medium / Low, or Not yet classified
- **Priority:** P0 - Immediate / P1 - High / P2 - Normal / P3 - Low, or Not yet classified
- **Affected Feature:** Feature, system, or subsystem name
- **Reporter:** GitHub user name or agent identifier
- **Date Reported:** YYYY-MM-DD

## Environment

- **Game Version:** X.Y.Z, or Not Available when no build exists
- **Build:** Build identifier, or Not Available
- **Platform:** Windows / Linux / macOS / Other
- **Godot Version:** For example 4.7.2
- **Configuration:** Debug / Release
- **Additional Context:** Relevant environment details

## Description

Describe the problem and its impact.

## Preconditions

- Condition 1.
- Condition 2.

## Steps to Reproduce

1. Step one.
2. Step two.
3. Step three.

## Expected Result

Describe what should happen.

## Actual Result

Describe what actually happens.

## Reproduction Frequency

- **Frequency:** Always / Frequent / Intermittent / Rare / Once / Unknown
- **Attempts:** X out of Y, if known

## Evidence

Attach or link screenshots, recordings, logs, and save files. Do not paste large logs inline.

- **Screenshot:**
- **Video:**
- **Logs:**
- **Save File:**
- **Additional Evidence:**

## Additional Information

- **Workaround:** None / Description
- **Suspected Cause:** Hypothesis only, if applicable
- **Related Issues:** Issue references
- **Related Requirements:** Work item or acceptance criterion identifiers

## Classification

Applied during triage from the defect label vocabulary in `BUG_REPORTING.md` (section 17.2). These labels must exist in the repository's label configuration; a label named only in this template has no effect in the tracker.

`bug`

`severity:critical` `severity:high` `severity:medium` `severity:low`

`area:gameplay` `area:ui` `area:audio` `area:performance` `area:persistence`

`regression` `release-blocker` `needs-reproduction` `needs-information`

## Resolution

Completed while the defect is investigated and closed.

- **Assigned To:**
- **Fix Description:**
- **Affected Commit or PR:**
- **Fixed Version:**
- **Verification Result:** Not Run / Passed / Failed / Blocked
- **Verification Evidence:**
- **Closure Reason:**

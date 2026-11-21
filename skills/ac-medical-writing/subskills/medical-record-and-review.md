---
name: medical-record-and-review
domain: writing/medical-record-and-review
trigger: "Managing versions and review of a medical document."
anti_trigger: "Not for the drafting itself, and not for publication ethics."
scope: "Version control and the review record."
status: seedling
---

# Medical record and review

## Standard

A medical document goes through structured review before it is released: clinical review for accuracy, statistical review for the data, regulatory review for compliance, and editorial review for clarity. The record tracks the document through these stages so that what was checked, by whom, and what changed is auditable. An unreviewed medical document is a liability.

Version control is the foundation. Each draft is versioned, changes are tracked, and the version under review is unambiguous. Clinical, statistical and regulatory reviewers examine the aspects they own; their comments are logged and resolved, and the resolution is recorded. A change made in one round is verified in the next, because a fix that introduces a new error is a known failure mode.

The review record closes the document. It names the version released, the reviews completed, the checks performed against source data, and any issues left open. A document released without a review record cannot demonstrate that its accuracy was ever verified.

Primary sources: <https://www.ich.org/> and <https://en.wikipedia.org/wiki/Medical_writing>.

## Decision rules

- Every draft is versioned with changes tracked; the version under review is unambiguous.
- Clinical, statistical, regulatory and editorial reviews each cover their own scope.
- Review comments are logged and their resolution recorded.
- A change in one round is verified in the next.
- The release record names version, reviews, checks and open issues.

## Procedure

1. Version each draft and track changes.
2. Route the document through clinical, statistical, regulatory and editorial review.
3. Log each comment and its resolution.
4. Verify prior-round changes in the next round.
5. Check the final version against source data.
6. Write the release record: version, reviews, checks, open issues.

## Anti-patterns

- An unversioned draft with untracked changes.
- A review that covers only style, never clinical accuracy.
- Comments resolved without a recorded resolution.
- A fix that introduces a new error, unverified.
- Release without a review record.

## Done checklist

- [ ] Drafts versioned with changes tracked.
- [ ] All required reviews completed.
- [ ] Comments logged with resolutions.
- [ ] Prior-round changes verified.
- [ ] Release record written.

Source-data verification is its own pass, distinct from clinical and editorial review. A checker compares every number, percentage, patient count and table in the document against the analysis output or source dataset, item by item, and signs off on each. This is the step that catches transcription errors no amount of clinical reading will find, and it is documented separately so the release record can show that verification actually happened.

## Sources

- International Council for Harmonisation: <https://www.ich.org/>
- Medical writing: <https://en.wikipedia.org/wiki/Medical_writing>
- Clinical study report: <https://en.wikipedia.org/wiki/Clinical_study_report>

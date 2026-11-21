---
name: annotator-calibration
domain: software-engineering/annotator-calibration
trigger: "Selecting, training, and qualifying the people who apply labels."
anti_trigger: "Not for writing the codebook, and not for measuring agreement statistics."
scope: "Selecting, training, and qualifying the people who apply the labels."
status: seedling
---

# Annotator calibration

## Standard

Annotators are part of the instrument, and an uncalibrated annotator is an unstandardised one. Snow and colleagues showed that non-expert crowds can match expert quality on many language tasks — but only when the task is decomposed and the workers are guided; the cheap-and-fast result is a finding about process, not a licence to skip it. Calibration is the process that turns a pool of people into a consistent measuring device: select for the task, train on the codebook, qualify against a known-answer set, and keep watching for drift once production starts.

The qualification gate is the load-bearing step. Before an annotator's labels enter the set, they must label a qualification batch whose correct answers are already known, and meet a stated accuracy bar against it. This catches the person who read the guidelines but applies them differently, and it does so before their noise is spread across thousands of items. Sheng and colleagues' multiple-noisy-labeler work gives the economic reason to invest here: a labeler's error rate is estimable, and knowing it lets you decide whether to retrain, reweight, or route around that person rather than silently averaging their errors into the data.

Primary sources: <https://aclanthology.org/D08-1027/> and <https://doi.org/10.1145/1401890.1401965>.

## Decision rules

- Select annotators for the task's domain and language, not just availability.
- Train on the current codebook version; training on a stale version is a defect.
- Gate every annotator on a known-answer qualification batch before production.
- State the qualification accuracy bar up front; do not lower it to fill seats.
- Estimate each annotator's error rate; use it to retrain, reweight, or route.
- Re-calibrate on a schedule and after any guideline change; watch for drift.

## Procedure

1. Define the task's required domain and language competencies.
2. Recruit a pool larger than needed so the gate can filter.
3. Train the pool on the frozen codebook with worked examples.
4. Administer the qualification batch; score against known answers.
5. Admit only those above the bar; record each annotator's qualification score.
6. Monitor production accuracy via golden items; re-calibrate on drift.

## Anti-patterns

- Letting annotators label production items before qualifying.
- Lowering the qualification bar to hit a headcount or deadline.
- Training on an old codebook version after a revision.
- Assuming a qualified annotator stays calibrated forever.
- Averaging a known-bad labeler's errors into the set instead of routing around them.

## Done checklist

- [ ] Selection criteria tied to the task.
- [ ] Training on the current codebook version.
- [ ] Qualification gate with a stated accuracy bar.
- [ ] Per-annotator qualification score recorded.
- [ ] Error rates estimated and acted on.
- [ ] Drift monitoring and re-calibration scheduled.

## Sources

- Cheap and Fast – But is it Good? (Snow et al.): <https://aclanthology.org/D08-1027/>
- Get Another Label? (Sheng et al.): <https://doi.org/10.1145/1401890.1401965>
- Towards a Shared Rubric for Dataset Annotation (Greene): <https://arxiv.org/abs/2112.03867>
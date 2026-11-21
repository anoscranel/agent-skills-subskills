---
name: knowledge-distillation
domain: software-engineering/knowledge-distillation
trigger: "Training a smaller student model to mimic a larger teacher."
anti_trigger: "Not for generic fine-tuning on data, and not for weight averaging of peers."
scope: "Teaching a smaller student from a larger teacher."
status: seedling
---

# Knowledge distillation

## Standard

Distillation transfers behaviour from a large, expensive teacher into a small, cheap student. Instead of training the student only on hard ground-truth labels, it is trained to match the teacher's outputs. The teacher's soft probability distribution carries more information than a one-hot label: the relative probabilities of the wrong answers encode how the teacher generalizes, which Hinton called the dark knowledge in the tail. A temperature parameter softens the distribution so those small probabilities become visible to the student during training.

The transfer signal varies by design. Response-based distillation matches the teacher's final outputs (logits or probabilities). Feature-based distillation also matches intermediate representations, giving the student richer guidance but requiring aligned hidden layers. For large language models, a common practical form is sequence-level distillation: generate text with the teacher and train the student on it, which needs no access to the teacher's internals, only its outputs. Distillation differs from fine-tuning: fine-tuning adapts a model to data, while distillation adapts a student to another model's behaviour. The student inherits the teacher's failure modes as well as its strengths, so a biased or hallucinating teacher produces a biased or hallucinating student.

Primary sources: <https://arxiv.org/abs/1503.02531> and <https://en.wikipedia.org/wiki/Knowledge_distillation>.

## Decision rules

- Distill when a capable teacher exists and a smaller model must approximate it cheaply.
- Use response-based distillation when only teacher outputs are available.
- Add feature-based terms when teacher internals and aligned layers are accessible.
- Tune temperature to expose the tail of the teacher's distribution.
- Evaluate the student against the teacher AND against ground truth, not only the teacher.
- Expect the student to inherit teacher failure modes; check for them explicitly.

## Procedure

1. Choose the teacher and the student architecture and size.
2. Decide the transfer signal: outputs only, or outputs plus features.
3. Generate teacher outputs (or soft labels) over the training inputs.
4. Train the student to match, with temperature on the soft targets.
5. Evaluate against ground truth and against the teacher on held-out data.
6. Record teacher, student, signal, temperature, and the quality gap.

## Anti-patterns

- Treating the student as an independent model rather than a teacher approximation.
- Evaluating only against the teacher, so inherited errors look like success.
- Temperature left at default when the tail carries the useful signal.
- Sequence-level distillation on teacher text that was never quality-checked.
- Assuming distillation removes the teacher's biases or hallucinations.

## Done checklist

- [ ] Teacher and student chosen and justified.
- [ ] Transfer signal decided.
- [ ] Teacher outputs generated over the training inputs.
- [ ] Student trained with tuned temperature.
- [ ] Evaluated against ground truth and teacher.
- [ ] Inherited failure modes checked.

## Sources

- Hinton et al., Distilling the Knowledge in a Neural Network: <https://arxiv.org/abs/1503.02531>
- Knowledge distillation overview: <https://en.wikipedia.org/wiki/Knowledge_distillation>
- Gou et al., Knowledge Distillation: A Survey: <https://arxiv.org/abs/2006.05525>

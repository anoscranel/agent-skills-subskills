---
name: dag-and-confounding
domain: critical-thinking/dag-and-confounding
trigger: "Mapping the causal structure and finding what to adjust for."
anti_trigger: "Not for the estimator, and not for sensitivity analysis."
scope: "The causal graph and what confounding is."
status: seedling
---

# DAG and confounding

## Standard

The causal directed acyclic graph encodes the analyst's assumptions about what causes what. A confounder is a common cause of treatment and outcome; it creates a backdoor path from treatment to outcome that is not the causal effect. Confounding is the reason treated and untreated units differ before any treatment is applied, and adjusting for the common causes is what removes it. The graph is what tells the analyst which variables are confounders, and therefore which to adjust for, rather than guessing from correlations or significance.

The graph also tells the analyst what NOT to adjust for. A collider is a variable caused by two others; conditioning on a collider opens a path that was closed and induces a spurious association. Conditioning on a descendant of the treatment biases the effect by blocking part of the causal path or by opening a collider path. The practical rule is that the adjustment set is read off the graph structure, never chosen because a covariate looked predictive or significant. Predictive power is not a reason to adjust, and a strong predictor of the outcome can be a collider that ruins the estimate.

Primary sources: <https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf> and <https://en.wikipedia.org/wiki/Directed_acyclic_graph>.

## Decision rules

- Draw the causal DAG before choosing any adjustment set.
- Identify confounders as common causes of treatment and outcome.
- Block backdoor paths by conditioning on the common causes.
- Never condition on a collider or on a descendant of treatment.
- Choose the adjustment set from graph structure, not predictive power.

## Procedure

1. Draw the assumed DAG: treatment, outcome, and their causes.
2. Trace every backdoor path from treatment to outcome.
3. Select a set that blocks all backdoor paths and opens none.
4. Check no selected variable is a collider or a treatment descendant.
5. Record the graph as a stated assumption, open to challenge.

## Anti-patterns

- Choosing covariates by significance or correlation with the outcome.
- Conditioning on a collider because it is predictive.
- Adjusting for a mediator or a descendant of treatment.
- Omitting the graph and asserting the adjustment set is obvious.

## Done checklist

- [ ] DAG drawn and recorded.
- [ ] Confounders identified as common causes.
- [ ] Backdoor paths traced and blocked.
- [ ] No collider or treatment descendant in the set.
- [ ] Set justified by structure, not significance.

## Sources

- Causal diagrams and backdoor adjustment: <https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf>
- Graph structure: <https://en.wikipedia.org/wiki/Directed_acyclic_graph>
- Confounding: <https://en.wikipedia.org/wiki/Confounding>

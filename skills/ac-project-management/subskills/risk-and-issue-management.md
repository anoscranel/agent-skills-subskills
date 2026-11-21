---
name: risk-and-issue-management
domain: software-engineering/risk-and-issue-management
trigger: "Identifying and managing project risks and issues."
anti_trigger: "Not for security threat modelling, and not for post-mortems."
scope: "The risk register, mitigation, and issue tracking."
status: seedling
---

# Risk and issue management

## Standard

A risk is an uncertain event that has not happened; an issue is one that has. The two are managed differently: risks are analysed and mitigated in advance, issues are resolved as they occur. The risk register is the central record, listing each risk with its probability, its impact, and the response chosen. It is a working document reviewed on a cadence, not a form completed once at the start and filed.

Risks are assessed on a probability-impact matrix so that attention goes to the few that matter most. Responses follow a small set of strategies: avoid the risk by changing the plan, reduce its probability or impact, transfer it to a party better able to bear it, or accept it knowingly with a contingency and a trigger. Every significant risk gets an owner and, where useful, an early-warning indicator. Issues, when they arise, are logged, prioritised and tracked to closure with the same discipline.

Primary sources: <https://en.wikipedia.org/wiki/Risk_register> and <https://en.wikipedia.org/wiki/Risk_management>.

## Decision rules

- Separate risks (uncertain, future) from issues (happened, present) and manage each accordingly.
- Assess each risk on probability and impact; focus effort on the highest exposures.
- Choose a response per risk: avoid, reduce, transfer, or accept knowingly.
- Give every significant risk an owner and, where useful, an early-warning trigger.
- Review the register on a fixed cadence and after any material change.
- Log, prioritise and track issues to closure with named owners.

## Procedure

1. Identify risks with the team, including external and assumption-based ones.
2. Score each for probability and impact on the matrix.
3. Select a response strategy per significant risk.
4. Assign owners and early-warning triggers.
5. Fund contingency for accepted risks from the budget.
6. Review the register on cadence and log issues as they arise.

## Anti-patterns

- A register written once and never reviewed again.
- Risks listed without probability, impact, or a chosen response.
- Accepting a major risk with no contingency and no trigger.
- Confusing an issue that has happened with a risk that might.
- High-impact risks with no named owner.

## Done checklist

- [ ] Risks identified including external ones.
- [ ] Probability and impact scored per risk.
- [ ] Response strategy chosen per significant risk.
- [ ] Owners and triggers assigned.
- [ ] Contingency linked to accepted risks.
- [ ] Review cadence set and issues tracked.

## Sources

- Risk register: <https://en.wikipedia.org/wiki/Risk_register>
- Risk management: <https://en.wikipedia.org/wiki/Risk_management>
- Project management: <https://en.wikipedia.org/wiki/Project_management>

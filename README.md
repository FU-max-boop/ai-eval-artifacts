# AI Evaluation Research Artifacts

A small portfolio of AI evaluation artifacts built around one habit:

> turn broad claims about model and agent behavior into runnable audits with
> controls, result cards, and explicit claim boundaries.

The artifacts are deliberately compact. Each one has a quickstart, smoke test,
result card, and a sentence about what the evidence does **not** prove.

For a concise overview aimed at research-engineering internships or research
collaborations, see the
[one-page pitch](docs/internship_research_engineering_pitch.md).

## 30-Second Scan

This portfolio is meant to show research-engineering ability, not just project
names:

- **Flagship agent artifact:** StateBind Guard tests whether coding-agent
  handoffs preserve executable bindings, not only visible identifiers.
- **Flagship LLM-eval artifact:** TraceUseAudit tests whether final answers
  behaviorally depend on supplied traces, not only whether traces look correct.
- **Shared quality bar:** every artifact has a runnable gate, a result card, and
  a claim boundary that says what the evidence does not prove.

## Artifacts

| Artifact | Question | Public repo | One-command gate |
| --- | --- | --- | --- |
| TraceUseAudit | Does a model's final answer behaviorally depend on supplied traces, or does it merely imitate trace form? | https://github.com/FU-max-boop/traceuse-audit-public | `make public-check` |
| StateBind Guard | Can coding-agent handoffs preserve executable state bindings rather than only visible identifiers? | https://github.com/FU-max-boop/statebind-guard | `bash scripts/check_public_ready.sh` |
| Claim-Boundary Audit | Which code-review feedback claim is warranted: local utility, transfer utility, text sensitivity, or hold? | https://github.com/FU-max-boop/claim-boundary-audit-public | `make public-check` |

## Shared Pattern

Modern AI evaluation often overclaims from surface success:

- a model can produce a rationale without using it;
- an agent can see an identifier without preserving the executable binding;
- feedback can improve one target-selection surface without supporting broad
  repair claims.

The artifact pattern is:

1. define the narrow behavioral claim;
2. add counterfactual or control conditions;
3. produce a compact result card;
4. state the claim boundary;
5. make the artifact runnable before making it persuasive.

## Current Evidence Snapshot

### TraceUseAudit

Public repo: https://github.com/FU-max-boop/traceuse-audit-public

Core message:

> high trace accuracy is not evidence of trace use.

Demo result:

| Demo | Trace accuracy | Gold-trace final accuracy | Trace-flip sensitivity | Same-trace shortcut-flip sensitivity |
| --- | ---: | ---: | ---: | ---: |
| Canonical parity | 0.900 | 1.000 | 0.100 | 1.000 |
| Language eligibility | 1.000 | 1.000 | 1.000 | 0.333 |

### StateBind Guard

Public repo: https://github.com/FU-max-boop/statebind-guard

Core message:

> visibility is not binding; executable handoffs must preserve active target,
> semantic role, and exact executable handle.

Natural-handoff benchmark:

| Method | Accuracy | Unsafe accept rate |
| --- | ---: | ---: |
| visibility baseline | 0.500 | 1.000 |
| keyword-role baseline | 0.500 | 1.000 |
| StateBind Guard | 1.000 | 0.000 |

### Claim-Boundary Audit

Public repo: https://github.com/FU-max-boop/claim-boundary-audit-public

Core message:

> code-review feedback can support a bounded target-selection claim without
> proving broad executable repair or human-level review understanding.

Four-bridge aggregate:

| Provider | Control | Positive bridges | Row-pooled delta |
| --- | --- | ---: | ---: |
| DeepSeek | shuffled-feedback | 4/4 | +0.247 [+0.194, +0.300] |
| DeepSeek | no-feedback | 4/4 | +0.228 [+0.175, +0.281] |
| GLM-4.5 | shuffled-feedback | 4/4 | +0.264 [+0.211, +0.317] |
| GLM-4.5 | no-feedback | 4/4 | +0.244 [+0.197, +0.294] |

## Direction

I am interested in the space between AI research and research engineering:
evaluation, interpretability-adjacent experiments, agentic workflows, and tools
that make model behavior easier to reason about.

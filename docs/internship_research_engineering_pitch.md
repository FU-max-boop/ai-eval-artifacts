# Fu Xiaonan - AI Evaluation / Research Engineering Pitch

HKU mathematics undergraduate building compact AI-evaluation artifacts.

I work at the boundary between research and engineering: turning broad claims
about model or agent behavior into runnable audits with controls, result cards,
and explicit claim boundaries.

I am looking for internship or research-engineering opportunities around AI
evaluation, agents, post-training behavior, and reliability tooling.

## Three Runnable Artifacts

| Artifact | Why it matters | Link |
| --- | --- | --- |
| TraceUseAudit | Tests whether final answers actually depend on supplied traces, instead of only imitating trace style. | https://github.com/FU-max-boop/traceuse-audit-public |
| StateBind Guard | Tests whether coding-agent handoffs preserve executable state bindings rather than only visible identifiers. | https://github.com/FU-max-boop/statebind-guard |
| Claim-Boundary Audit | Separates local utility, transfer utility, and overbroad claims for code-review feedback. | https://github.com/FU-max-boop/claim-boundary-audit-public |

Portfolio landing page:
https://github.com/FU-max-boop/ai-eval-artifacts

## Open-Source Track Record

Merged upstream PRs:

- xlang-ai/OpenCUA#56: fixed AgentNetBench evaluator scoring edge cases.
- HKUDS/LightRAG#3038: added an offline sample retrieval check for RAGAS
  evaluation.
- HKUDS/RAG-Anything#273: preserved content-list aliases in multimodal chunks.
- HKUDS/RAG-Anything#278: fixed content-list duplicate detection.
- pydantic/pydantic-ai#5355: preserved xAI tool result IDs and updated the xAI
  SDK constraint.

Additional open PRs are under review in pydantic-ai, MCP Python SDK,
MarkItDown, browser-use, and claw-eval.

## What I Can Contribute

- Design small evaluations that answer a real decision rather than only fill a
  leaderboard table.
- Build reproducible artifacts: scripts, smoke tests, result cards, and
  limitation notes.
- Find benchmark/evaluator failure modes and upstream small patches.
- Move quickly across research code, agent workflows, and practical validation.

## Best Fit

Teams working on:

- AI evaluation and benchmark reliability
- coding agents / agent handoffs / tool-use reliability
- post-training diagnostics and process supervision
- research engineering for model behavior, eval infrastructure, or AI systems

GitHub: https://github.com/FU-max-boop

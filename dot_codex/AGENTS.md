# Coordination and delivery

The main conversation acts as the Chief of Staff: own the user's goal, scope, priorities, cross-project dependencies, integration, final verification, and final delivery. Delegate bounded implementation when useful and complete straightforward tasks directly.

- Use `project_manager` only when a project or independent workstream needs sustained decomposition, dependency tracking, or acceptance management. Create one PM per active workstream as needed; there is no fixed PM count.
- Use `implementation_worker` for scoped code changes, fixes, tests, and other implementation deliverables. A PM may dispatch these workers; the main agent may dispatch them directly for simpler work.
- Give every task an owner, objective, relevant context, allowed files or modules, interfaces, dependencies, acceptance criteria, and required verification. One agent coordinates each task; route changes through that coordinator.
- Do not impose a fixed numeric implementation-worker cap in these instructions. The Chief of Staff dynamically sizes parallel execution from independent ready tickets, observable runtime slots, API quotas, and local build/test capacity, coordinating across PMs and both clients. Leave capacity for PMs, advisors, and skill-required helpers. Queue work when capacity is exhausted and resume when slots free up rather than repeatedly retrying failed spawns. Honor explicit run budgets and platform-enforced limits.
- Parallelize independent work with explicit file ownership. Concurrent ticket branches in the same repository require separate worktrees/checkouts; otherwise serialize checkout, editing, testing, commits, and pushes. Assign one writer per ledger file: CoS owns the portfolio ledger, each PM owns separate project records, and workers report updates through their coordinator. Every worker must preserve others' changes.
- Keep project state in the assigned project task document when persistence is useful. Worker reports must include changed files, verification results, and unresolved issues. PMs check acceptance evidence; the main agent reviews integration and verifies final outcomes before reporting completion.

# Chief of Staff intake and autonomous delivery

For rough requirements, daily portfolio priorities, PRD-to-ticket planning, or approved unattended execution, read [chief_of_staff operating workflow](~/.codex/workflows/chief-of-staff.md). Run the main conversation as the authoritative Chief of Staff; use `chief_of_staff` as a dedicated primary-session role or bounded delegate, not a second competing dispatcher.

CoS owns the daily priority queue and unified dispatch. PMs decompose PRDs, maintain project context, and prepare ready tickets. Workers implement on ticket branches, verify changes, and automatically create/update Draft PRs when authorized for the assigned repository and run. Persist task state and reconcile interruptions as the workflow specifies.

Apply the workflow's advisor gates: architecture after PRD decomposition and before consequential dispatch; visual review after UI direction and after rendered implementation; code review after checks and before consequential PR publication. CoS schedules the relevant review, PM supplies context, and Worker reports evidence and findings. Skip unnecessary reviews with a reason and reuse reviews that cover unchanged evidence.

# UI design workflow

Every agent performing UI page development or changes to user-facing screens, components, layout, styling, interactions, or UX copy must use the installed `impeccable` skill to guide design before UI implementation. Read its SKILL.md from the available skills and follow the applicable workflow in the target project's directory.

The main agent or PM supplies the brief, existing product/design context, and target surface. A worker must load the applicable skill workflow in its own session rather than assuming the coordinator's skill invocation reached it. Use Impeccable's specialized helpers where its workflow requires them, within available runtime capacity and the coordinator's scheduling plan; consult `visual_advisor` for independent visual analysis when useful.

# Advisor delegation

Advisors provide independent analysis; implementation workers produce changes. The main agent coordinates specialist advice, and PMs or workers can request a focused consultation through their coordinator.

- For cross-module architecture decisions, difficult failures unresolved after targeted investigation, or consequential design tradeoffs, delegate a focused question to `architecture_advisor`.
- For a nontrivial implementation plan, confusing execution path, or consequential code review, delegate a focused question to `code_advisor`.
- For screenshots, charts, interface consistency, readability, or user-facing copy, delegate a focused question to `visual_advisor` with the relevant images, text, or accessible screen context.
- Invoke agents by their configured role names so their model and reasoning settings apply. Include the question, relevant evidence, constraints, and expected result. Wait for advice before dependent actions and check the evidence behind recommendations.
- Advisors remain read-only and complete their assigned analysis without spawning additional agents. Implementation workers do not create PMs or more implementation workers; skill-required helpers follow the UI workflow above.

# UI design workflow

For UI page development or changes to user-facing screens, components, layout, styling, interactions, or UX copy, the main agent must use `$impeccable` to guide design before UI implementation. Read the installed `impeccable` skill's `SKILL.md` using the current session's available-skills catalog and follow its applicable workflow in the target project's directory.

The main agent owns the Impeccable design workflow. Consult `visual_advisor` for independent visual analysis when useful.

# Advisor delegation

Apply this routing in the main agent. The main agent owns implementation, verification, and final delivery; advisors provide independent analysis.

- For cross-module architecture decisions, difficult failures that remain unresolved after targeted investigation, or competing designs with consequential tradeoffs, delegate a focused question to `architecture_advisor`.
- For an independent assessment of a nontrivial implementation plan, a confusing execution path, or a consequential code change, delegate a focused question to `code_advisor`.
- For screenshots, charts, interface consistency, readability, or user-facing copy, delegate a focused question to `visual_advisor`. Include the relevant images, text, or accessible screen context.
- Complete straightforward tasks directly. Start with the single most relevant advisor; consult another when a distinct question needs its expertise. Parallelize consultations only when the questions are independent.
- Invoke advisors by their configured role names so their model settings and instructions apply. Give each advisor the question, relevant evidence, constraints, and the expected result.
- Wait for advice before taking dependent actions, check the evidence behind recommendations, then carry out the implementation and appropriate verification in the main agent.
- Advisors complete their assigned analysis without spawning additional agents.

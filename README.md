# AI Work Team

A structured, skills-only workflow for moving AI-assisted projects from **discussion → planning → handoff → strict execution** without silently changing scope.

AI Work Team is designed for product, game, software, and other project work where you want the model to behave differently at different stages instead of mixing brainstorming, planning, and implementation together.

## Core modes

### Discussion Mode
Use this while the idea is still being shaped.

- Asks **one focused question at a time** when information is missing.
- Summarises the current understanding as decisions accumulate.
- Offers a small number of suitable directions while preserving the user's ability to propose a different option.
- Keeps unresolved items explicit instead of inventing decisions.
- Continues until the project is defined well enough to hand to Planning Mode.
- Does **not** start implementation.

### Planning Mode
Use this once the direction is sufficiently defined.

- Treats existing project documentation and repository state as source-of-truth inputs when available.
- Produces a detailed implementation plan rather than coding immediately.
- Splits work into bounded milestones/stages.
- Defines scope, dependencies, acceptance criteria, validation, risks, and exit gates.
- Produces handoff material that another model/session can execute without relying on hidden chat context.
- Does **not** silently resolve contradictions in the source of truth.

### Strict Worker
Use this after an implementation plan or handoff has been approved.

- Executes only the approved scope.
- Does not redesign the feature while implementing it.
- Validates work against the handoff's acceptance criteria.
- If the handoff conflicts with the repository, architecture, prior locked decision, or actual implementation state, it **stops and escalates** instead of improvising.
- Requires the relevant exit gate to pass before declaring the stage complete.

## Workflow

```text
Idea
  ↓
Discussion Mode
  ↓  design sufficiently defined
Planning Mode
  ↓  approved handoff / source of truth
Strict Worker
  ↓
Validated implementation
```

If Strict Worker discovers a contradiction, the flow moves back to Discussion or Planning rather than allowing implementation to redefine the project.

## Example invocation

```text
@AI Work Team, discussion mode
I want to design a small management game. Ask me one focused question at a time until the design is sufficiently defined.
```

```text
@AI Work Team, planning mode
Use the current source of truth and prepare implementation milestones and handoff files. Do not implement yet.
```

```text
@AI Work Team, strict worker
Execute M3.1 exactly as defined in the approved handoff. Escalate any contradiction instead of changing scope.
```

## Repository layout

```text
.
├── .agents/plugins/marketplace.json
├── plugins/ai-work-team/
│   ├── .codex-plugin/plugin.json
│   └── skills/
│       ├── ai-work-team/
│       ├── discussion-mode/
│       ├── planning-mode/
│       └── strict-worker/
├── docs/
│   ├── installation.md
│   ├── workflow.md
│   └── handoff-protocol.md
├── examples/
│   ├── discussion-example.md
│   ├── planning-example.md
│   └── strict-worker-example.md
├── CONTRIBUTING.md
├── CHANGELOG.md
└── LICENSE
```

## Install from GitHub

This repository includes a plugin manifest and a GitHub marketplace manifest.

### Workspace marketplace import

For supported managed workspaces, an admin can import the repository as a plugin marketplace:

1. Open **Workspace/Admin settings → Plugins**.
2. Select **Add → Import marketplace**.
3. Use this repository as the source: `https://github.com/dinosauryeo/ai-work-team`.
4. Leave the marketplace path empty because `.agents/plugins/marketplace.json` is at the repository root.
5. Import the marketplace, then install **AI Work Team**.

### Individual skill upload

If your ChatGPT account supports personal Skills, you can also use the individual skill packages under `plugins/ai-work-team/skills/`. Review the files first, then use **Plugins → Skills → Create → Upload from your computer** for the skill you want.

> GitHub distribution is separate from publication in OpenAI's universal Plugin Directory. Public-directory publication requires the official plugin submission/review process.

## Source-of-truth principle

AI Work Team uses an explicit hierarchy whenever a project already has persistent documentation:

1. Locked decisions / approved source-of-truth documents
2. Approved milestone or handoff document
3. Current repository state and tests
4. Current chat instructions that do not conflict with the above
5. Assumptions — only when safe and clearly labelled

A contradiction between higher-priority sources is not something Strict Worker should "fix" by guessing. It should produce an escalation.

## Versioning

This project follows semantic versioning where practical:

- **PATCH** — wording/clarity changes that preserve workflow behaviour.
- **MINOR** — new compatible skills, templates, or workflow capabilities.
- **MAJOR** — behavioural changes that alter mode boundaries or handoff guarantees.

Current version: **0.1.0**.

## Security and privacy

AI Work Team is currently a **skills-only plugin**. It does not bundle credentials or external app connections. Any tools available to the model remain governed by the user's ChatGPT/Codex environment and its normal permissions.

Never commit secrets, API keys, private project files, or proprietary source-of-truth material to this public repository.

## License

MIT. See [LICENSE](LICENSE).

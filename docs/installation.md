# Installation

## Import as a GitHub marketplace

Workspace admins can import AI Work Team directly from this repository.

1. Open **Workspace settings → Plugins**.
2. Select **Add → Import marketplace**.
3. Set Source to `https://github.com/dinosauryeo/ai-work-team`.
4. Leave **Path** empty because `.agents/plugins/marketplace.json` is stored at the repository root.
5. Leave Branch empty to follow the default branch, or choose `main` explicitly.
6. Import the marketplace and review the resulting plugin.
7. Set the installation policy appropriate for your workspace.

Once imported, GitHub-backed marketplaces can sync updates from the repository.

## Upload individual skills

Eligible ChatGPT accounts that support personal Skills can also install individual skills manually:

1. Open the desired folder under `plugins/ai-work-team/skills/`.
2. Download/copy that skill folder, including its `SKILL.md` and any supporting files.
3. In ChatGPT, open **Plugins → Skills → Create → Upload from your computer**.
4. Upload the skill package and review it before installing.

Available skills:

- `ai-work-team` — router
- `discussion-mode`
- `planning-mode`
- `strict-worker`

## Invocation

After installation, invoke AI Work Team using an @ mention when supported, or explicitly name the desired mode in your prompt.

Examples:

```text
@AI Work Team, discussion mode
```

```text
@AI Work Team, planning mode
```

```text
@AI Work Team, strict worker
```

## Notes

Plugin and Skill availability varies by plan, workspace, role, product surface, and rollout. GitHub marketplace import is primarily a workspace-admin distribution mechanism; individual skill upload may be more convenient for personal use when available.

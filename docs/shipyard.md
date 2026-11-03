# Agent setup moved to Shipyard

`dot_codex` and `dot_claude` have been removed from this repository. Their shared workflow, native role templates, optional model configuration, launcher, and guarded branch cleanup now live in [Shipyard](https://github.com/itamaker/skills/tree/main/skills/in-progress/shipyard).

Shipyard is in development under `skills/in-progress`; this migration does not promote it into the released plugin or create a release. Merge the skills change before this retirement so installation can resolve the source. Future publication and installation are owned by the skills repository.

## Migrate

Install from the skills repository, selecting **Global** scope and both Codex and Claude Code:

```bash
npx skills@latest add itamaker/skills --skill=shipyard
```

For noninteractive installation, explicitly add `-g`; `--yes` alone uses project scope. Alternatively, maintainers can use the skills repository's existing local-link workflow, after inspecting its replacement behavior.

Preview and then explicitly install native role configuration from the installed skill:

```bash
python3 ~/.agents/skills/shipyard/scripts/install_clients.py --client both
python3 ~/.agents/skills/shipyard/scripts/install_clients.py --client both --apply
```

The Linux/macOS installer backs up changed named files and preserves unrelated global settings and instructions. Invoke `$shipyard` in Codex or `/shipyard` in Claude Code. The skill's [client reference](https://github.com/itamaker/skills/blob/main/skills/in-progress/shipyard/references/clients.md) documents optional primary-session launch commands and requirements.

Removing the source directories stops chezmoi managing these agent files. This migration does not delete existing files in the user's home; do not purge `~/.codex` or `~/.claude`, which may hold authentication and session data. Existing global instruction files can retain old rules: review their team-workflow sections and replace those sections with the installed skill entry when adopting Shipyard, preserving unrelated instructions.

Worker test selection, pre-merge CI regression, staffing, and cleanup policy are documented once in the skill. No permanent CI/QA role is required by default; the coordinator owns acceptance and assigns specialist work only when evidence or risk calls for it.

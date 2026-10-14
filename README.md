# Buzz Context Skills

Three small, instruction-only skills for the [Buzz Context MCP](https://github.com/moonishaider/buzz-context-mcp). They improve research and answer quality; they do not add tools or expand access. Ready for the approved teammate alpha rollout, skills version **0.1.1**. The three skills were discovered and used in local macOS Codex and Claude Code acceptance checks; Windows/Linux client discovery remains unverified. No official Buzz or OpenAI endorsement.

| Skill | Use |
| --- | --- |
| [buzz-context-research](skills/buzz-context-research/SKILL.md) | Questions, investigations and readable source attribution |
| [buzz-context-catch-up](skills/buzz-context-catch-up/SKILL.md) | Period/project summaries, decisions and follow-ups |
| [buzz-context-document-review](skills/buzz-context-document-review/SKILL.md) | Native documents, uploaded files and extraction limits |

## Install into Codex or Claude Code

This repository is public; no GitHub invitation is needed. You need a configured Buzz Context MCP to use the skills. For a new installation, use the combined prompt below. These skills need no credentials, packages, scripts or new MCP registration. They do not read Buzz's credential storage.

Paste this into your local assistant session for connector plus skills:

> Set up https://github.com/moonishaider/buzz-context-mcp and install all three skills from https://github.com/moonishaider/buzz-context-skills. Follow both READMEs, preserve my existing settings, offer browser or Terminal setup, and verify the connection and skill discovery. Keep my credentials out of chat and tell me about any unverified support on my platform.

If the connector is already configured, install only the skills and preserve its registration/profile. These are local Codex/Claude Code instructions, not a promise of support in every assistant or cloud session.

Assistant installation procedure:

1. Read the public repository without credentials; never ask for a Buzz key or GitHub token in chat. Read this README and the three `SKILL.md` files from a clean reviewed checkout. Record the resolved source commit; use that exact commit for installation, not a moving branch during the operation.
2. Prefer the bundled skill-installer's `install-skill-from-github.py` when available. Use `--repo moonishaider/buzz-context-skills --ref RESOLVED_COMMIT --path skills/buzz-context-research skills/buzz-context-catch-up skills/buzz-context-document-review`. The helper's location and supported options depend on the installed client; read its local instructions/help instead of inventing a command path.
3. Check the actual client's skill destination. The [official Codex guide](https://learn.chatgpt.com/docs/build-skills) documents user skills in `~/.agents/skills`; some bundled installers use `$CODEX_HOME/skills` (default `~/.codex/skills`). When needed, use the helper's supported `--dest` for the client's discoverable location. [Claude Code](https://code.claude.com/docs/en/skills) documents personal skills in `~/.claude/skills/<skill-name>/SKILL.md`; copy the three reviewed directories there for a local Claude Code session. `agents/openai.yaml` is Codex-specific metadata and is not required by Claude Code. Do not install duplicates across directories within one client. A checkout alone is not a skill installation. Other clients need their own verified skill support.
4. If the helper is absent, copy only the three reviewed skill directories into the verified user-skill location. Stop on an existing same-name directory and compare before changing it; do not silently overwrite unrelated or customized skills. No global `AGENTS.md`, hooks, plugins or MCP settings need modification.
5. Check the installed files against the pinned checkout and record source commit, destination and installed names in the setup report. Confirm skill discovery through the actual client when available. Codex normally detects newly installed skills automatically; restart if they do not appear. In the current thread, the assistant can explicitly read the installed `SKILL.md` to use it immediately without pretending automatic discovery has been verified.

Automatic selection is enabled by default, but not guaranteed on every prompt. Invoke a skill explicitly with its name when you want a particular workflow. These skills do not fetch instructions from Buzz conversations or update themselves remotely.

## MCP alignment and updates

The 13-tool connector version 0.1.0-alpha.3 includes readable-source guidance and complete supported attachment-text continuation. Skills do not add these runtime capabilities. Install skills independently; an MCP update requires a reviewed source checkout, the implementation repository's supported preparation steps, and a restart of its client connection. Preserve the profile, registration and credential entry; no new secret entry is required by an instruction-only update. Do not pull over a dirty checkout or use a scratch runtime as a permanent registration.

For a skills update, review the new commit and compare local modifications before replacement. Rollback can restore the recorded prior skill files. Uninstall removes only the three installed skill directories after checking ownership/customization; it does not disconnect or remove Buzz credentials.

## Quality and limits

See [VALIDATION.md](VALIDATION.md) for checks actually performed and remaining client acceptance. Skill guidance cannot guarantee model compliance. It does not fix unsupported encryption, edit/delete reconciliation, legacy threads, file-content indexing or extraction bounds.

Apache-2.0 licensed. No private workspace material belongs in this repository.

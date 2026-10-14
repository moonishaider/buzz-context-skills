# Buzz Context Skills

Three small, instruction-only skills for the private [Buzz Context MCP](https://github.com/moonishaider/buzz-context-mcp). They improve research and answer quality; they do not add tools or expand access. Private personal-use release, version **0.1.0**. No official Buzz or OpenAI endorsement.

| Skill | Use |
| --- | --- |
| [buzz-context-research](skills/buzz-context-research/SKILL.md) | Questions, investigations and readable source attribution |
| [buzz-context-catch-up](skills/buzz-context-catch-up/SKILL.md) | Period/project summaries, decisions and follow-ups |
| [buzz-context-document-review](skills/buzz-context-document-review/SKILL.md) | Native documents, uploaded files and extraction limits |

## Install into your existing Codex setup

You need access to this private repository and an already configured Buzz Context MCP. These skills need no credentials, packages, scripts or new MCP registration. They do not read Buzz's credential storage.

Paste this into the same Codex thread:

> Install the three skills from https://github.com/moonishaider/buzz-context-skills using its README. Use the built-in skill-installer if available, review the files first, preserve existing skills and my existing Buzz Context MCP registration and credentials, and verify that all three are discoverable. Then use buzz-context-research for my Buzz questions. Tell me if this client needs a restart before it sees the skills.

Assistant installation procedure:

1. Authenticate with existing GitHub/git access; never ask for a Buzz key or a GitHub token in chat. Read this README and the three `SKILL.md` files from a clean reviewed checkout. Record the resolved source commit; use that exact commit for installation, not a moving branch during the operation.
2. Prefer the bundled skill-installer's `install-skill-from-github.py` when available. Use `--repo moonishaider/buzz-context-skills --ref RESOLVED_COMMIT --path skills/buzz-context-research skills/buzz-context-catch-up skills/buzz-context-document-review`. The helper's location and supported options depend on the installed client; read its local instructions/help instead of inventing a command path.
3. Check the client-supported skill destination. The current [official Codex guide](https://learn.chatgpt.com/docs/build-skills) documents user skills in `~/.agents/skills`; some bundled installers use `$CODEX_HOME/skills` (default `~/.codex/skills`). When necessary, pass the helper's supported `--dest` explicitly for the client's documented discoverable location. Do not install duplicate copies into both directories. A repository checkout alone is not a user-skill installation.
4. If the helper is absent, copy only the three reviewed skill directories into the verified user-skill location. Stop on an existing same-name directory and compare before changing it; do not silently overwrite unrelated or customized skills. No global `AGENTS.md`, hooks, plugins or MCP settings need modification.
5. Check the installed files against the pinned checkout and record source commit, destination and installed names in the setup report. Confirm skill discovery through the actual client when available. Codex normally detects newly installed skills automatically; restart if they do not appear. In the current thread, the assistant can explicitly read the installed `SKILL.md` to use it immediately without pretending automatic discovery has been verified.

Automatic selection is enabled by default, but not guaranteed on every prompt. Invoke a skill explicitly with its name when you want a particular workflow. These skills do not fetch instructions from Buzz conversations or update themselves remotely.

## MCP alignment and updates

The existing 13-tool connector works with these skills. Its older citation instructions may encourage ID-heavy answers. The companion MCP change makes normal citations readable while retaining exact references in tool results. Install skills independently of that change; an MCP update requires a reviewed source checkout, the implementation repository's supported preparation steps, and a restart of its client connection. Preserve the profile, registration and credential entry; no new secret entry is required by an instruction-only update. Do not pull over a dirty checkout or use a scratch runtime as a permanent registration.

For a skills update, review the new commit and compare local modifications before replacement. Rollback can restore the recorded prior skill files. Uninstall removes only the three installed skill directories after checking ownership/customization; it does not disconnect or remove Buzz credentials.

## Quality and limits

See [VALIDATION.md](VALIDATION.md) for checks actually performed and remaining client acceptance. Skill guidance cannot guarantee model compliance. It does not fix unsupported encryption, edit/delete reconciliation, legacy threads, file-content indexing or extraction bounds.

Apache-2.0 licensed. No private workspace material belongs in this repository.

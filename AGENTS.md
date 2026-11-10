# AGENTS.md

Instructions for AI agents. Read the section that matches what the user asked you to do: install this skill, use it, or maintain it.

## Installing it for a user

The skill has no dependencies and needs no API keys. Installing means putting this folder where the user's agent looks for skills.

1. **Pick the skills directory** for the agent the user wants it in:
   - Claude Code, for all projects: `~/.claude/skills/etsy-listing-helper`
   - Claude Code, for one project: `<project>/.claude/skills/etsy-listing-helper`
   - Codex: `~/.codex/skills/etsy-listing-helper`

   If you are not sure which agent or scope the user wants, ask. If you are that agent, install it for yourself.
2. **Check whether the target already exists.**
   - It does not exist: clone into it.

     ```bash
     git clone https://github.com/silennsong/etsy-listing-helper.git ~/.claude/skills/etsy-listing-helper
     ```

   - It exists and is a git clone of this repository: run `git -C <target> pull`.
   - It exists and is anything else: stop and ask the user before replacing it. It may hold their own edits.
3. **Verify.** `<target>/SKILL.md` and `<target>/references/listing-fields.md` must exist. The folder name must stay `etsy-listing-helper`, matching the `name` in `SKILL.md`.
4. **Tell the user** to start a new session, and that the skill triggers when they paste product specs and/or product images and ask for Etsy listing content. Point them to the usage example in `README.md`.

Claude.ai cannot be installed from a shell. Tell the user to download the repository as a ZIP and upload it in the Skills section of their Claude.ai settings.

## Using the skill

Follow `SKILL.md`. In short: read `references/listing-fields.md` on every run, grep `references/etsy-categories.md` for the category instead of reading it whole, and do not read `references/sources/` during normal generation.

## Maintaining the skill

- The rules for adding new Etsy guidance are in the "Maintaining this skill" section of `SKILL.md`. Follow them; the reference layer is deliberately one rulebook plus one lookup table.
- `README.md` and `README.zh-CN.md` say the same thing in two languages. Change both together, including the source list when a new official source is integrated.
- Do not put shop names, product data from real orders, or other user-specific content into the repository. Examples must be generic.

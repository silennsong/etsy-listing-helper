# Etsy Listing Helper

**English** | [简体中文](README.zh-CN.md)

An **Agent Skill** for [Claude Code](https://claude.com/claude-code), Claude.ai and Codex that turns print-on-demand (POD) product specs and product photos into complete, copy-paste-ready Etsy listing content.

## What it does

Give your agent the product spec text (material, size, printing technique, features…) and/or white-background product images, and it outputs the following in a **fixed, consistent format** every time:

1. **Title**: ≤140 chars, strongest buyer search phrase first
2. **Tags**: all 13, each ≤20 chars, covering Etsy's official brainstorming dimensions (descriptive, materials, recipient, occasion, solution, style, size)
3. **Description**: keyword-rich opening (Google snippet), structured sections with emoji bullets
4. **Materials**: up to 13 searchable entries
5. **Category & Attributes**: the deepest matching path from Etsy's official category tree, plus applicable attributes
6. **Photo Alt Text**: ≤250 chars for accessibility/SEO
7. **Variations**: size / print sides / personalization suggestions
8. **Rationale**: why each choice was made

**Language handling**: copy-paste blocks are in English by default, or in any listing language you specify (for example German for Etsy DE). Translations and rationale are written in whatever language you chat in. Copy-paste blocks never mix languages.

**Multi-product**: send N images and get N complete listings. Send images only and the skill reuses the product spec from earlier in the conversation.

## Install

No dependencies and no API keys. The skill is a folder of Markdown files.

### Let your agent do it

Paste this into Claude Code or Codex:

```text
Read https://github.com/silennsong/etsy-listing-helper and install this skill for me by following its AGENTS.md. When you finish, tell me how to use it.
```

### Manual install

Claude Code, personal skill:

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.claude/skills/etsy-listing-helper
```

Claude Code, project skill: clone into `.claude/skills/etsy-listing-helper` inside your project.

Codex:

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.codex/skills/etsy-listing-helper
```

Claude.ai: download this repository as a ZIP and upload it in the Skills section of your settings.

Start a new session afterwards. The skill triggers on its own when you paste product specs or images and ask for listing content.

### Update

```bash
git -C ~/.claude/skills/etsy-listing-helper pull
```

## Usage example

Paste something like this, plus your product image:

```
Material Description: Plastic + PVC.
Product Size: 5.5"x5.5"x11.0".
Printing Technique: UV Printing.
Product Performance: ... built-in solar panel, 120mAh battery, up to 6 hours ...
Applicable Scenario: patio, garden, porch ... Christmas, Halloween ...
Package Includes: A product instruction manual is included.

Please generate the Etsy listing info.
```

You get a complete, numbered, paste-ready listing for each image.

## Built on official Etsy guidance

The `references/` folder contains structured digests of:

- [Keywords 101: Everything You Need to Know](https://www.etsy.com/seller-handbook/article/keywords-101-everything-you-need-to-know/382774281517), Etsy Seller Handbook
- [Add Attributes to Help Increase Your Shop's Visibility](https://www.etsy.com/seller-handbook/article/604203126614), Etsy Seller Handbook
- [The Anatomy of a Well-Crafted Etsy Listing](https://www.etsy.com/seller-handbook/article/1347574487014), Etsy Seller Handbook
- [Checklist: Optimize Your Shop for Etsy Search](https://www.etsy.com/seller-handbook/article/366470356778), Etsy Seller Handbook
- [Complete Etsy Category List](https://www.etsy.com/help/categories/seller), the full official category tree (~3,000 lines), so suggested categories are real, exact, deepest-level paths

> Etsy content © Etsy, Inc., included for reference with attribution. Etsy is a trademark of Etsy, Inc. This project is not affiliated with or endorsed by Etsy.

## Repository layout

| Path | Purpose |
|---|---|
| `SKILL.md` | The skill itself: workflow, output format, quality bar. This is what the agent loads. |
| `references/listing-fields.md` | One consolidated rulebook for every listing field. Read on every run. |
| `references/etsy-categories.md` | Etsy's category tree, used as a lookup table. |
| `references/sources/` | Source notes: a link and short summary for each official article. Not read during normal use. |
| `AGENTS.md` | Install and maintenance steps for AI agents. |

## Contributing new Etsy guidance

Merge rules into `references/listing-fields.md` (one consolidated rulebook, each fact stated once) and add a source note (link, dates, short summary) to `references/sources/`. Don't copy Etsy's articles in full. Don't add new always-read reference files. See the "Maintaining this skill" section in [SKILL.md](SKILL.md).

## License

MIT. See [LICENSE](LICENSE).

The MIT license covers this project's own work. Files under `references/` summarize and quote the Etsy Seller Handbook and Etsy Help Center; that content remains © Etsy, Inc.

# Etsy Listing Helper

A [Claude Code](https://claude.com/claude-code) / Claude.ai **Agent Skill** that turns print-on-demand (POD) product specs and product photos into complete, copy-paste-ready Etsy listing content.

[中文说明](#中文说明) below.

## What it does

Give Claude your product spec text (material, size, printing technique, features…) and/or white-background product images, and it outputs — in a **fixed, consistent format** every time:

1. **Title** — ≤140 chars, strongest buyer search phrase first
2. **Tags** — all 13, each ≤20 chars, covering Etsy's official brainstorming dimensions (descriptive, materials, recipient, occasion, solution, style, size)
3. **Description** — keyword-rich opening (Google snippet), structured sections with emoji bullets
4. **Materials** — up to 13 searchable entries
5. **Category & Attributes** — the deepest matching path from Etsy's official category tree, plus applicable attributes
6. **Photo Alt Text** — ≤250 chars for accessibility/SEO
7. **Variations** — size / print sides / personalization suggestions
8. **Rationale** — why each choice was made

**Language handling**: copy-paste blocks are in English by default (or any listing language you specify — e.g. German for Etsy DE). Translations and rationale are written in whatever language you chat in. Copy-paste blocks never mix languages.

**Multi-product**: send N images → get N complete listings. Send images only → the skill reuses the product spec from earlier in the conversation.

## Built on official Etsy guidance

The `references/` folder contains structured digests of:

- [Keywords 101: Everything You Need to Know](https://www.etsy.com/seller-handbook/article/keywords-101-everything-you-need-to-know/382774281517) — Etsy Seller Handbook
- [Add Attributes to Help Increase Your Shop's Visibility](https://www.etsy.com/seller-handbook/article/604203126614) — Etsy Seller Handbook
- [Complete Etsy Category List](https://www.etsy.com/help/categories/seller) — the full official category tree (~3,000 lines), so suggested categories are real, exact, deepest-level paths

> Etsy content © Etsy, Inc., included for reference with attribution. Etsy is a trademark of Etsy, Inc. This project is not affiliated with or endorsed by Etsy.

## Install

**Claude Code (personal skill):**

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.claude/skills/etsy-listing-helper
```

**Claude Code (project skill):** clone into `.claude/skills/etsy-listing-helper` inside your project.

Restart Claude Code (or start a new session) and the skill auto-triggers when you paste product specs / images and ask for listing content.

## Usage example

Paste something like this (plus your product image):

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

## License

MIT — see [LICENSE](LICENSE).

---

## 中文说明

这是一个 Claude Code / Claude.ai 的 Agent Skill，用于辅助 Etsy 上架：输入 POD 产品规格文本和白底电商图，输出固定格式的完整上架信息（标题、13 个标签、描述、材料、官方类目路径、属性、图片 Alt 文本、变体建议、写作理由）。

- **语言规则**：供复制粘贴的部分默认输出英语（可指定其他上架语言）；翻译和理由说明使用你与 Claude 对话的语言。复制区绝不混入其他语言，方便直接粘贴进 Etsy。
- **多图多 listing**：一次发 N 张图就输出 N 套上架信息；只发图时自动沿用本会话中上一次的产品规格。
- **官方依据**：`references/` 内整理了 Etsy 官方关键词指南、属性指南全文和完整官方分类树（约 3000 行），类目建议保证是官方真实存在的最深层路径。

**安装**：

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.claude/skills/etsy-listing-helper
```

重启 Claude Code 后，粘贴产品信息 + 图片并说「出上架信息」即可自动触发。

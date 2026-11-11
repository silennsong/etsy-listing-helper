# Etsy Listing Helper

[English](README.md) | **简体中文**

一个给 [Claude Code](https://claude.com/claude-code)、Claude.ai 和 Codex 用的 **Agent Skill**，用来辅助 Etsy 上架：输入 POD（按需定制）产品的规格文本和产品图，输出可以直接复制粘贴的完整上架信息。

## 它能做什么

把产品规格文本（材质、尺寸、印刷工艺、功能等）和白底产品图发给 Agent，它每次都按**固定格式**输出下面这些内容：

1. **标题**：不超过 140 个字符，买家最常搜的词放在最前面
2. **标签**：填满 13 个，每个不超过 20 个字符，覆盖 Etsy 官方建议的几个角度（描述、材质、送礼对象、场合、解决的问题、风格、尺寸）
3. **描述**：开头带关键词（会成为 Google 搜索摘要），后面分段，用 emoji 做小标题
4. **材料**：最多 13 项可被搜索的材料
5. **类目和属性**：Etsy 官方类目树里最深一层的匹配路径，加上适用的属性
6. **图片 Alt 文本**：不超过 250 个字符，用于无障碍和 SEO
7. **变体建议**：尺寸、单面或双面印刷、个性化定制
8. **写作理由**：每一项为什么这样写

**语言规则**：供复制粘贴的部分默认输出英语，也可以指定其他上架语言（比如 Etsy 德国站用德语）。翻译和理由说明使用你和 Agent 对话的语言。复制区不会混入其他语言，可以直接粘贴进 Etsy。

**多图多 listing**：一次发 N 张图，就输出 N 套上架信息。只发图时，自动沿用本次对话里上一次给的产品规格。

## 安装

没有依赖，也不需要任何 API Key。整个 skill 就是一个 Markdown 文件夹。

### 让 Agent 帮你装

把下面这段话发给 Claude Code 或 Codex：

```text
请阅读 https://github.com/silennsong/etsy-listing-helper ，按仓库里 AGENTS.md 的步骤帮我把这个 skill 装好，装完告诉我怎么用。
```

### 手动安装

Claude Code，个人 skill：

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.claude/skills/etsy-listing-helper
```

Claude Code，项目 skill：clone 到项目里的 `.claude/skills/etsy-listing-helper`。

Codex：

```bash
git clone https://github.com/silennsong/etsy-listing-helper.git ~/.codex/skills/etsy-listing-helper
```

Claude.ai：把这个仓库下载成 ZIP，在设置的 Skills 部分上传。

装完后新开一个会话。粘贴产品信息或图片，说一句“出上架信息”，skill 会自动触发。

### 更新

```bash
git -C ~/.claude/skills/etsy-listing-helper pull
```

## 使用示例

粘贴类似下面的内容，再附上产品图：

```
Material Description: Plastic + PVC.
Product Size: 5.5"x5.5"x11.0".
Printing Technique: UV Printing.
Product Performance: ... built-in solar panel, 120mAh battery, up to 6 hours ...
Applicable Scenario: patio, garden, porch ... Christmas, Halloween ...
Package Includes: A product instruction manual is included.

请帮我出 Etsy 上架信息。
```

每张图会得到一套编号完整、可以直接粘贴的上架信息。

## 依据的 Etsy 官方资料

`references/` 文件夹里整理了以下官方内容：

- [Keywords 101: Everything You Need to Know](https://www.etsy.com/seller-handbook/article/keywords-101-everything-you-need-to-know/382774281517)，Etsy 卖家手册
- [Add Attributes to Help Increase Your Shop's Visibility](https://www.etsy.com/seller-handbook/article/604203126614)，Etsy 卖家手册
- [The Anatomy of a Well-Crafted Etsy Listing](https://www.etsy.com/seller-handbook/article/1347574487014)，Etsy 卖家手册
- [Checklist: Optimize Your Shop for Etsy Search](https://www.etsy.com/seller-handbook/article/366470356778)，Etsy 卖家手册
- [Complete Etsy Category List](https://www.etsy.com/help/categories/seller)，完整的官方类目树（约 3000 行），所以建议的类目都是官方真实存在的最深层路径

> Etsy 相关内容版权归 Etsy, Inc. 所有，这里注明出处后供参考。Etsy 是 Etsy, Inc. 的商标。本项目与 Etsy 没有隶属或背书关系。

## 仓库结构

| 路径 | 用途 |
|---|---|
| `SKILL.md` | skill 本体：流程、输出格式、质量要求。Agent 加载的就是它。 |
| `references/listing-fields.md` | 所有上架字段的规则合订本，每次生成都会读。 |
| `references/etsy-categories.md` | Etsy 类目树，当查询表用。 |
| `references/sources/` | 出处说明：每篇官方文章的链接和简短摘要。正常使用时不读。 |
| `AGENTS.md` | 给 AI Agent 看的安装和维护步骤。 |

## 补充新的 Etsy 官方资料

把规则合并进 `references/listing-fields.md`（一份合订本，每条事实只写一次），在 `references/sources/` 里加一份出处说明（链接、日期、简短摘要）。不要整篇复制 Etsy 的文章。不要新增每次都要读的参考文件。详见 [SKILL.md](SKILL.md) 里的 “Maintaining this skill” 一节。

## 许可证

MIT，见 [LICENSE](LICENSE)。

MIT 许可证覆盖的是本项目自己的内容。`references/` 下的文件摘录和引用了 Etsy 卖家手册与 Etsy 帮助中心，这部分内容的版权仍归 Etsy, Inc. 所有。

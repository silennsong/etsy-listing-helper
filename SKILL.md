---
name: etsy-listing-helper
description: >-
  Generate complete, copy-paste-ready Etsy listing content (title, tags, description,
  materials, category, attributes, alt text, variation ideas) from POD product spec text
  and/or white-background product photos. Use this skill whenever the user provides
  product information (Material Description, Product Size, Printing Technique, etc.)
  and/or e-commerce product images and wants Etsy listing info, listing copy, SEO tags,
  or anything related to publishing a product on Etsy — in any language. Also trigger
  when the user only sends product images in a session where product base info was given
  earlier — reuse that info. One image = one listing output.
---

# Etsy Listing Helper

Turn POD (print-on-demand) product specs + designed product photos into ready-to-paste Etsy listing content, in a **fixed format** with translations and reasoning.

## Language rules

Two kinds of content appear in the output — keep them strictly separate:

1. **Copy-paste blocks** (Title, Tags, Description, Materials, Alt Text): **English by default**, since Etsy's primary marketplace language is English. If the user explicitly asks for another listing language (e.g., German for Etsy DE), write these blocks in that language instead. Never mix languages inside a copy-paste block — the user pastes these into Etsy verbatim.
2. **Annotations** (translation lines, rationale section, any commentary): use the **language the user is conversing in** — not the language of the product spec. A user chatting in Chinese with English spec text gets Chinese annotations; a user chatting in English gets English annotations.

If the conversation language is the same as the listing language (e.g., both English), omit the translation lines entirely — they would be duplicates — but keep the rationale section.

## Inputs you may receive

1. **Product base info** (spec text: Material Description, Product Size, Design Area, Printing Technique, Product Performance, Applicable Scenario, Washing Instructions, Warm Reminder, Package Includes…)
2. **One or more white-background product images** showing the design

Rules:
- **N images → N complete listings**, one per design. Number them Listing 1, Listing 2…
- **Images only, no spec text** → reuse the most recent product base info from this conversation. If none exists in the session, ask the user for it.
- **Spec text only, no image** → generate one listing; note that design-specific keywords (subject, style) are placeholders the user must fill.
- Look carefully at each image: identify the design subject (e.g., French Bulldog wearing sunglasses with coffee), art style (vintage, watercolor, cartoon…), colors, and mood. These drive the keywords — the spec text alone produces generic, low-ranking listings.

## Reference files — read before writing

- [references/etsy-rules.md](references/etsy-rules.md) — quick field-by-field checklist (character limits, photo/variation/personalization specs). Always read.
- [references/keywords-101.md](references/keywords-101.md) — full official "Keywords 101" article: title before/after examples, tagging dos & don'ts, the 7 tag-brainstorming dimensions (descriptive / materials & techniques / who it's for / occasions / solution / style / size). Always read; build the 13 tags by covering several of these dimensions.
- [references/attributes.md](references/attributes.md) — full official attributes article: attributes power sidebar filters, must describe what the product IS not how it's used (occasion attribute ≠ gift tag). Read when filling section 5.
- [references/etsy-categories.md](references/etsy-categories.md) — Etsy's complete official category tree (~3,000 lines). Do NOT read whole; grep for the product keyword (e.g. "Lantern") or top-level category (e.g. "Home & Living") and pick the **deepest matching subcategory**. Use the exact official names in the Category path of section 5.
- [references/search-optimization.md](references/search-optimization.md) — ranking mechanics and title rules from "Anatomy of a Well-Crafted Listing" + the official search-optimization checklist: ~15-word titles, the tag "Google rule", first-photo SEO (no text overlays, 2000px+), description = phase-2 ranking, shop-level factors. Always read.

Validate every title ≤ 140 characters and every tag ≤ 20 characters before output.

## SEO principles (from Etsy Seller Handbook)

- Think like a buyer: keywords = **subject + product type + recipient/occasion + style** (e.g., "french bulldog gift", "solar garden lantern", "dog mom gift", "vintage patio decor"). Spread them across title, tags, description, and attributes — Etsy ranks holistically, so the title doesn't have to carry everything.
- Title: **short and scannable, ~15 words or fewer** — clearly name the item, put its most important traits (subject, color, material, size) upfront, don't repeat words, no subjective fluff ("perfect", "beautiful"), no price/shipping/sale info. Include a holiday/occasion/recipient word only if it's essential to what the item IS (a "Halloween costume" yes; an item that merely makes a good gift, no — that goes in tags). Word order doesn't affect ranking directly, but a clear title earns clicks, and popularity feeds back into ranking.
- Tags: always use **all 13**; multi-word phrases in natural language — official rule of thumb: *if you can't imagine someone typing it into Google, it shouldn't be a tag*. Don't repeat the category/attribute words verbatim; mix high-traffic and long-tail; cover several brainstorming dimensions (what it is, how it's made, who it's for, occasion, style, solution, size); no deliberate misspellings, no plural variants. Tags must be in the shop's language — foreign-language tags don't help search.
- Description: keywords in descriptions power the second phase of search ranking. Put essential info (size, dimensions, colors) at the top, incorporate top keywords naturally in the first few sentences (they also feed Google's snippet) — don't copy the title verbatim; don't open with "Welcome to my shop"; end with the design's story in the brand's voice.
- Categories and attributes act like extra tags — pick the deepest official category and fill every truly applicable attribute (choose the closest available option even if imperfect); don't waste tag slots duplicating them.
- First photo is a search factor: advise white/clean background, no text overlays or collages, at least 635px (2000px+ recommended) — POD white-background renders qualify as-is.

## Fixed output format

Use this exact template for every listing. Copy-paste blocks must contain **only the listing language** (zero characters from other languages) so the user can paste directly into Etsy. The `> Translation:` lines and section 8 are annotations — write them in the user's conversation language, and label them naturally in that language (e.g. `> 中文翻译：` for a Chinese-speaking user, `> Traducción:` for Spanish).

---

```
## Listing {N} — {design short name, e.g. "French Bulldog Coffee Lantern"}

### 1. Title (~15 words, ≤140 chars)
{listing-language title}

> Translation: {title in conversation language — omit if same language}

### 2. Tags (13 tags, ≤20 chars each)
{tag1}, {tag2}, … {tag13}

> Translation: {tag-by-tag translation — omit if same language}

### 3. Description
{listing-language description, structured as:}
{• Opening hook sentence with main keywords (first ~160 chars feed the Google snippet)}
{• ✨ DESIGN — describe the printed design}
{• 📏 DETAILS — size, material, printing technique, design area}
{• ☀️ FEATURES — solar/battery/waterproof etc. from Product Performance}
{• 🎁 PERFECT FOR — scenarios & gift occasions}
{• 🧼 CARE — washing instructions}
{• 📦 PACKAGE — what's included}
{• ⚠️ PLEASE NOTE — the production-variance reminder, rewritten in friendly customer-facing language}

> Translation: {full description in conversation language — omit if same language}

### 4. Materials (≤13)
{e.g. Plastic, PVC, Solar panel}

### 5. Category & Attributes
- Category: {deepest official Etsy category path from etsy-categories.md}
- Occasion: {…} / Holiday: {…} / Room: {…} / Color: {…} (only ones that truly apply)

### 6. Photo Alt Text (≤250 chars)
{listing-language alt text describing the image for accessibility/SEO}

### 7. Variations (if applicable)
{e.g. size options, single- vs double-sided printing, personalization offer — or "Not applicable"}

### 8. Rationale
{2-5 bullet points in the conversation language: why the title is ordered this way,
how the tags balance head terms and long-tail, why this category/attribute set,
variation reasoning}
```

---

Multiple listings: repeat the template per image, separated by `---`. Keep section numbering and headings identical every time — consistency is the point; users batch-copy these into Etsy daily.

## Quality bar

- Tags: count characters; anything over 20 chars must be shortened or split into phrasal chunks.
- Title: never start with the shop name or generic words like "Beautiful"; start with the item's strongest identifying phrase, keep it ~15 words, and don't repeat words. Recipient/occasion angles ("dog mom gift") belong in tags unless they define the item itself.
- Don't invent product facts not in the spec or visible in the image (e.g., don't claim "metal" if spec says plastic) — Etsy prohibits misleading descriptions.
- Personalization: POD products usually support custom designs — if plausible, suggest it in Variations as it's a strong Etsy differentiator.
- Remind the user once per session (not per listing): Etsy requires POD shops to disclose production partners under the Handmade Policy.

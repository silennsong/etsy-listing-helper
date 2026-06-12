# Etsy Listing Fields: Consolidated Rules (上架字段规则合订本)

Single consolidated reference for every listing field, merged from official Etsy sources
(all dated August 2025; full original articles preserved in `sources/`):

- Keywords 101: Everything You Need to Know
- Add Attributes to Help Increase Your Shop's Visibility
- The Anatomy of a Well-Crafted Etsy Listing
- Checklist: Optimize Your Shop for Etsy Search
- Etsy Help Center seller docs

Organized in the order the fields appear on Etsy's listing form. Each field's rules
appear here exactly once.

---

## 0. How Etsy search ranks (context for everything below)

- Etsy search takes a **holistic view**: title, tags, attributes, description, first photo, reviews, and more. No single field has to carry all the keywords — spread them.
- **Phase 1 (query matching)**: keywords across titles, descriptions, tags, categories, and attributes. **Phase 2 (ranking)**: keywords/phrases in the description are considered again, plus quality signals.
- **Popularity feedback loop**: listings that earn clicks and sales rank better over time, so buyer-facing clarity (scannable title, strong first photo) is itself an SEO strategy.
- Customer service quality (average review rating, message response rate, case rate over past 3 months), clear shop policies (template gives an extra boost), and US shipping price under $6 all affect placement. New listings appear in search even with zero reviews.
- Etsy matches **root words** (singular/plural: "diary" matches "diaries") and **auto-corrects common misspellings**. It auto-translates titles/tags into the shopper's language.

## 1. Title

**Limits**: max 140 characters; official guidance: **under ~15 words**, short and scannable.

- Clearly **name the item** ("mug", "dress", "lantern") — shoppers only see the first few words in search results, especially on mobile.
- Put the **most important traits upfront**: subject, color, material, size.
- **Word order has no direct ranking effect** — front-loading is for the shopper's scanning, and clicks feed the popularity loop.
- Only include holiday/occasion/recipient words **if essential to what the item IS** ("Halloween costume", "birthday candle" yes; an item that merely makes a good gift, no — that angle goes in tags).
- Don't repeat words. Move subjective words ("perfect", "beautiful") to the description. No price/shipping/sale info (Etsy badges those in search). No ALL CAPS spam, no %&$ characters, never start with the shop name.
- Punctuation and symbols are fine as separators — search still reads each phrase.
- Accuracy is policy: never claim a material the product isn't (no "cashmere" unless it is).

**Official before/after examples:**

| Before (keyword dump) | After (clear & scannable) |
|---|---|
| Dad T-Shirt \| Father Shirt \| Personalized Father's Day Gift \| Personalized Dad T-Shirt \| Dad Statement Shirt \| Father Shirt with Kids Names | Personalized 100% Cotton Dad T-Shirt: Custom Kids' Names S-XL |
| Moonstone Ring Mini Ring Solid Gold Perfect For Women's Wedding Engagement Daily Wear Band | Celestial Blue Moonstone Ring: 9k Solid Gold Band |
| ON SALE ! Birthday Bandana - Happy Birthday, Birthday Dog Bandana, Birthday Cat Bandana, Birthday Bones, Birthday Pet Present | Birthday Bones Cotton Dog Bandana: Easy Slip Over the Collar |

**Pattern that works for POD decor**: `{Design subject} {Material/Feature} {Product type}: {Style} {Use-case}`

## 2. Photos & Alt Text

- Up to **20 photos**. The **first photo is a search factor**: no text overlays, no collages; minimum 635×635 px (below that ranks lower), **2000 px+ recommended**; clean simple background (white-background POD renders qualify as-is).
- More photos → more buyer information → better conversion. Suggest follow-up shots: multiple angles, close-ups of details/texture, lifestyle/in-context images (patio, on a model), natural light, no flash.
- **Alt text**: max ~250 characters; plainly describe subject, product, and colors for accessibility/SEO.

## 3. Description

- Keywords here count in **both ranking phases** — incorporate top keywords naturally in the **first few sentences** (which also feed Google's ~160-char snippet). Don't copy the title verbatim or dump a keyword list; write a human sentence in the brand's voice. Never open with "Welcome to my shop".
- **Essential info at the top**: sizes, dimensions, colors, ordering/customization directions. Then features, scenarios, care, package contents, production-variance note.
- Use bullet points / short paragraphs (emoji bullets work) — a wall of text is intimidating.
- **End with the story**: inspiration or process behind the design builds buyer connection and brand loyalty.

## 4. Tags

**Limits**: exactly **13 tags**, each max **20 characters** including spaces. Use all 13 — unused tags are missed opportunities.

**Dos:**
- Multi-word phrases in natural language ("custom bracelet" > "custom" + "bracelet" — and it frees a slot). **Google rule of thumb: if you can't imagine someone typing it into Google, it shouldn't be a tag.**
- Target **long-tail** phrases over generic head terms ("canvas tote bag" > "tote bag") — specific searchers convert better. A good mix: 3–4 high-traffic terms, 5–6 long-tail, 2–3 recipient/occasion.
- Phrases longer than 20 chars: split into phrasal chunks ("minimalist diamond engagement rings" → "minimalist jewelry" + "diamond ring" + "engagement ring").
- Add synonyms and regional phrases Etsy doesn't auto-map (US "flip flops" vs AU "thong sandals"). Regional *spellings* (jewelry/jewellery) ARE auto-matched — don't waste slots.
- Refresh tags on low-traffic listings; diversify terms (Shop Stats shows what's working).

**Don'ts:**
- Don't repeat tags or near-duplicates ("octopus art print" + "animal wall decor" beats "octopus art" + "octopus print").
- Don't repeat exact phrases already in your category or attributes — those already act as tags.
- No deliberate misspellings (search auto-corrects). No plural variants (root-word matching). No tags in other languages (use the shop language; Etsy auto-translates — foreign-language tags don't help). No irrelevant trending terms.

**The 7 official brainstorming dimensions** — cover several across the 13 tags:

1. **Descriptive** (what it is, in your own words): 1920s cat brooch, striped ceramic mug, set of four coasters
2. **Materials & techniques** (how it's made; include "custom"/"personalized" if applicable): hammered cuff, custom embroidery, reclaimed wood frame, personalized tumbler
3. **Who it's for** (recipient): gifts for boyfriend, gifts for new moms, teacher gift, dog mom gift
4. **Shopping occasions** (appropriate for, even if not made for): stocking stuffers, bachelorette party, first anniversary, christening gifts
5. **Solution-oriented** (the problem it solves): closet organization, workout headbands, indoor garden
6. **Style** (era/palette/aesthetic + product word): art deco lamp, minimalist ring, rustic wall decor
7. **Size/shape**: shallow basket, large beach bag, tiny gold hoops

## 5. Materials

- Up to **13 free-text entries**; searchable. List actual materials (Plastic, PVC) plus notable components (solar panel, LED). Accuracy is policy — no aspirational materials.

## 6. Category

- Pick the **deepest matching subcategory** from the official tree (`etsy-categories.md` — grep, don't read whole; use exact official names). The listing is auto-included in every parent category, and **each category level acts like a tag**.
- Deeper categories also unlock more category-specific attributes (see below).
- Don't spend tag slots repeating phrases that appear in the category path.

## 7. Attributes

- Attributes are **structured, category-specific options** (vs free-text tags). Most categories offer Color (primary/secondary), Holiday, Occasion; deeper categories add specific ones (necklace → chain style, strand count; beads → size, shape; oil paintings → orientation, subject; home decor → room).
- Each attribute **acts like a tag** AND powers the **sidebar filters** — a listing can only appear in filtered results if it has that attribute. Accurate attributes also qualify listings for seasonal/recipient shopping experiences and marketing.
- **Add every attribute that truly applies; skip ones that don't.** Irrelevant attributes erode buyer trust and conversion.
- **Attributes describe what a product IS, not how it's used**: Father's Day attribute fits a Father's Day card, not a wallet that would make a good Father's Day gift (use a tag like "dad gift" for that).
- Choose the closest available option even if imprecise — if "pink" is accurate for your "magenta" yarn, add Pink; then use title/tags/description for your own wording.
- Don't repeat an exact attribute phrase as a standalone tag (multi-word combinations are fine: attribute "Faux fur" + tag "faux fur accent rug").

## 8. Variations & Personalization

- Up to **2 variation types** (e.g., Size, Design Sides), each up to 70 options; options can carry their own price.
- **Personalization toggle**: free-text buyer field with up to 1024-char instructions — a strong differentiator for POD (custom names, photos, breed swaps). Suggest it whenever plausible.

## 9. Shop-level & other fields (advise the user; not part of generated copy)

- **Shipping price**: US domestic listings with shipping under $6 are prioritized in search; shifting shipping cost into item price (same total) measurably improves sales.
- **Shop policies**: having them boosts placement; Etsy's policy template adds more.
- **Shop title**: a concise tagline of what you sell — also feeds SEO.
- **Customer service stats** feed ranking (reviews, response rate, case rate); Star Seller badge builds conversion.
- **POD compliance**: Etsy's Handmade Policy requires disclosing production partners.
- **Maintenance cadence**: refresh titles/tags at season starts and before major holidays; scan for repeated tag phrases as slots to diversify; the Etsy search visibility page (Shop Manager / Seller app) surfaces per-listing actions.

---

Note from Etsy: search is always changing; these are current best practices as of August 2025. Results may vary.

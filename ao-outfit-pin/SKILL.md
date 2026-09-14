---
name: ao-outfit-pin
description: Create a white Canva outfit pin from items in AO Products, reuse a consistent generated male model, verify product labels, and publish to an existing seasonal Pinterest board. Try Canva first and upload directly to Pinterest if Canva publishing fails. Use for The AO Project outfit pins, not retailer product capture or unrelated designs.
---

# AO Outfit Pin

Turn an item list into one editable Canva outfit pin and one verified Pinterest post. Follow the six steps below. Read supporting references only at the step that needs them.

## User defaults

| Setting | Default |
| --- | --- |
| Canvas | 1000 × 1500 px, white background, finished pin on Page 1 |
| Layout | Full-body model in the centre, original product cutouts around him, generous whitespace |
| Product scale | Clearly readable at feed size; generally 28–31% of canvas width for garments, bags, and shoes in a six-item layout, and 18–21% for a watch |
| Decoration | No coloured shapes or textures; arrows only when they clarify a product |
| Model | Same fictional adult male: tall, lean, dark straight hair, light stubble |
| Product labels | Concise customer-facing UPPERCASE names; Caveat, up to 30 px, bold, #18282d, centred, line height 1.12 |
| Footer | THEAOPROJECT.COM |
| Pinterest | Account `theaoproject`; suitable existing seasonal board; homepage `https://theaoproject.com` |
| Publishing | Automatically after checks: Canva first, direct Pinterest fallback if needed |

**Permission:** Creating, saving, uploading, and publishing the requested outfit are authorized. Do not ask again just to save Canva changes or use the Pinterest fallback. A later “don't publish,” review request, board choice, or link change overrides these defaults. Discussing or editing this skill alone does not authorize a sample post.

## 1. Start or resume the run

Use Canva tools for supported asset/design operations and the authenticated browser for unsupported actions. Read current browser documentation before using the UI; inspect tool schemas rather than guessing parameters.

Keep `run.json` and output files under the AO project's `outputs/ao-outfit-pins/<date>-<outfit>/`. The established project is `/Users/ojfamador/Documents/ChatGPT/The AO Project Site`; resolve its references there even if the calling task starts elsewhere.

On a follow-up, read the existing run before making a new design or publishing. Record these fields as they become available: requested items, canonical product names and IDs, display labels, model reference, design ID/URL, page, account, board, title, description, destination, status, publication hold, route, and published pin URL/ID. Do not overwrite a prior run with a new outfit.

If the run is already published, return its pin instead of publishing again unless the user explicitly requests another post. If it is pending or uncertain, verify the outcome first.

## 2. Match every requested product

Find the existing **AO Products** folder. Known folder ID: `FAHU32j4oOc`; re-resolve by name if unavailable. Inspect both assets and designs, including relevant pagination.

Match each requested item by **name and appearance**. Verify colours and model variants. Save the exact folder name as the canonical product name. Write a concise customer-facing display label that keeps the useful brand, model, colour, and item type while removing internal codes, stock references, redundant material or fit wording, and awkward catalogue fragments. Use judgment: a label should identify the visible product naturally, not reproduce every word in its folder name.

Use the original full-resolution cutout, or export the correct page for products stored as designs. Thumbnails are for identification, not final artwork. Preserve product masters. If an item is missing, ambiguous, mislabeled, or the list cannot form a wearable outfit, resolve that specific issue before continuing; do not invent or substitute an item.

## 3. Generate the model image

Read [model and layout guidance](references/model-and-layout.md). Use the built-in image-generation tool with the saved identity reference and matched product images. Generate the wearing model only; add product cutouts and labels separately in Canva.

Established identity:
- Canva asset `MAHVF-NkSRo`, named `AO Model Reference`.
- Project file `outputs/ao-outfit-pins/2026-09-13-spey-denim/ao-model-reference.png`.

Retrieve and inspect that reference. If it cannot be recovered, ask before replacing the established identity. For an initial setup with no established reference, create and save one using the defaults above.

Compare the generated face, hair, proportions, and visible garments/accessories with the references. Correct mismatches, allowing the first generation plus two targeted corrections. Keep a draft if a material mismatch remains.

## 4. Build the Canva design

**Preferred:** Copy the verified editable seed `DAHVF_7HNQg` (The AO Project — Spey & Light Denim — Autumn Outfit). Preserve the original; replace its model, product images, and labels in the copy. Adapt positions for the actual item count.

If copying is unavailable, use the tested import route in [model and layout guidance](references/model-and-layout.md), or create the layout in Canva's editor. Keep every label editable. For connector editing transactions: start → edit → preview → commit → verify saved result. Routine commits are already authorized.

Preserve image aspect ratios and complete product edges. Size the visible product, not merely its transparent container: cutouts should feel substantial beside the model and remain recognizable in a small Pinterest feed preview. For a six-item layout, start with the product-scale range in the defaults table; an increase of roughly 10–15% is appropriate when the first preview feels sparse. Preserve each item's visual centre, keep comfortable gaps from the model and page edges, and rebalance its caption after resizing.

Apply the label style in the defaults table to every product. Keep labels visually consistent, but shorten wording first and reduce a long label modestly (usually to 26–28 px) when needed for proportion. Use deliberate line breaks of no more than two or three lines. Remove internal codes such as `W/ C8135 PP`, stock references, and awkward catalogue fragments. Prefer a natural label such as `POLO RALPH LAUREN NAVY HALF-ZIP JUMPER` while retaining the complete canonical folder name in `run.json`. Pinterest titles and descriptions use natural sentence/title case; the ALL CAPS rule applies to the on-image product labels.

## 5. Check the saved Page 1

Inspect at full size and at a small feed-like size. Fix any failed check before publishing:

- Every requested product appears once as a sharp original cutout with a correct, natural uppercase display label; canonical folder names remain unchanged in the manifest and no old template content remains.
- The model resembles the saved identity and wears the intended visible outfit without material substitutions or anatomical defects.
- Background is white; products are large enough to recognize at feed size; labels are uniform and clearly associated with products; nothing overlaps or is clipped.
- Head, shoes, product edges, and footer are complete, with comfortable whitespace.
- Canva has saved the correct finished Page 1.

## 6. Publish and verify

Read [publishing instructions](references/pinterest-publishing.md). Assess the outfit's season first, then select an appropriate existing board. Use local season only as a tiebreaker.

Write an occasion-led title and a natural description of the look, styling, and where to wear it, following the house style in the publishing reference. Keep full canonical product names in the manifest; use the concise verified display labels on the image, and accurate everyday item names in the description. Set the actual homepage destination field. Save status `publishing` before submitting once. Try Canva first. If it fails and no matching pin exists, export the saved Page 1 and publish directly on Pinterest without another approval. A pending or uncertain Canva job must be resolved before switching routes.

Report success only after verifying the resulting post. Save the actual route (`canva` or `pinterest-direct`), pin URL/ID, and evidence in the run. If blocked, keep the prepared work and state the specific missing input or action. Do not create boards, change accounts, delete pins, or repeat unchanged failed submissions to force completion.

## Return to the user

Give the Canva link, Pinterest pin link, chosen board, and publication status concisely. Distinguish saved, uploaded, and published. Do not claim this workflow was tested on a particular assistant model or that identity consistency was proven across posts unless it actually was.

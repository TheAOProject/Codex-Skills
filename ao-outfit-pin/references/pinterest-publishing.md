# Publish: Canva first, Pinterest fallback

Both routes are authorized for the requested outfit. Respect any later publishing hold. A saved draft or completed upload is not a published pin.

## Prepare one set of publishing details

1. Assess season from the outfit's layers, fabric weight, coverage, and footwear. Use current local season only to break a tie.
2. Inspect the account's existing boards and select the best match. Do not hardcode autumn for every outfit or create a new board. Resolve a missing or ambiguous board with the user.
3. Write the title and description using the house style below: lead with the look, mood, and where someone would wear it. Respect current field limits.
4. Use account `theaoproject`, Page 1 only, immediate publication, and the actual destination field `https://theaoproject.com`. A URL in the description does not replace the destination field.

Keep these values in `run.json` and reuse them if the publishing route changes.

## Title and description house style

Match the user's previous pins in tone and structure, adapting the words to each actual outfit. The supplied example is **Easy Weekend Summer Fit ☀️ | The AO Project**: a relaxed description of the pieces, followed by why the look works for coffee runs, holidays, casual weekends, and summer afternoons. This copy reference does not change the white-background design or uppercase product labels.

**Title:** Use a short, natural occasion/mood/season phrase, one fitting emoji, and `| The AO Project`. Examples: `Easy Weekend Summer Fit ☀️ | The AO Project`, `Autumn Coffee Run Fit ☕ | The AO Project`, or `Relaxed City Weekend 🍂 | The AO Project`. Choose an occasion that suits the actual clothes. Avoid leading with brand/model names or creating a product-catalogue title.

**Description:** Write one natural paragraph, usually two or three sentences:

1. Introduce the overall look and its key colours or pieces in everyday language.
2. Explain the visible fit or styling: relaxed versus structured proportions, layering, or how the pieces work together.
3. Name two to four plausible places, activities, or moments to wear it, such as a coffee run, city walk, casual lunch, holiday, or slow weekend afternoon.

Use a relaxed, approachable voice: simple, clean, easy to wear. Vary phrasing so posts do not sound copied. Describe visible styling rather than claiming unverified comfort, warmth, performance, fabric, or suitability for a specific dress code. No keyword stuffing, sales pitch, invented sponsorships, or mandatory website call to action.

The description may use accurate everyday item names such as “white tee,” “light-wash jeans,” or “white trainers.” Mention a brand naturally when useful; do not append a full list of canonical product names. Exact canonical names remain required in the run manifest and uppercase on-image labels. If a specific brand/model is named in the prose, it must match the verified product.

Example for the Spey-and-denim outfit (style illustration, not a request to edit the existing post):

**Autumn Coffee Run Fit ☕ | The AO Project**

A relaxed men's autumn outfit built around a brown cropped jacket, white tee, light-wash jeans and clean white trainers. The short jacket balances the straight-leg denim, while black sunglasses and a silver watch keep the details simple. An easy everyday look for coffee runs, casual lunches, city walks or slow autumn weekends.

Before publishing, check that both title and description convey the look and a believable occasion, rather than mainly listing products.

## Route A — Canva

1. Open the verified saved design → **Share → Pinterest**. Inspect **See all** if needed.
2. Choose **Image pin** and **Page 1 only**. A single-page design may omit page selection; verify the one-page design and preview instead. The retained screenshot's Page 2 selection must not override the Page 1 requirement.
3. Fill the title, description, seasonal board, and destination link. Verify the account and final preview.
4. Save status `publishing` and route `canva`, then click **Publish** once.
5. Inspect the result. If successful, open the pin and verify it. If clearly failed, check for a matching pin on Pinterest, then use Route B. One retry is reasonable after correcting a specific cause; do not loop on the same error. A user-requested retry may override that normal limit.

UI examples: [Share menu](../assets/canva-share-reference.png), [Pinterest form](../assets/pinterest-form-reference.png). These are references, not live connection state.

## Route B — Direct Pinterest upload

Use this route when Canva publishing is unavailable or failed and no matching pin exists. No additional publishing approval is needed.

1. Export the latest saved Page 1 from Canva as a full-resolution PNG. For the standard layout use 1000 × 1500. Inspect the export; use it rather than a screenshot or thumbnail.
2. Open the selected board in Pinterest and choose **Create a Pin → Pin**, or the current equivalent. Verify `theaoproject` and the exact board name; starting from the board may preselect it.
3. Read current file-upload documentation and upload the exported PNG through the supported file chooser. If Chrome rejects `setFiles` because file URL access is disabled, follow its troubleshooting instructions. Ask the user to enable the permission or select the prepared file; do not change extension permissions silently. After an extension restart, recover the same Chrome profile/session using fresh browser/tab IDs.
4. Fill the prepared title, description, and **Link** field. Keep scheduling off. Because the wearing model is AI generated, enable **Mark as AI-Modified** and **This Pin includes an AI-generated person** when shown.
5. Verify image, copy, board, account, and link. Save status `publishing` and route `pinterest-direct`, then click **Publish** once.
6. Inspect the result and open the new pin. Pinterest may show an extension-install offer after publishing; dismiss it and check the board for the new pin. An empty composer alone is not proof of success.

## Verify and prevent duplicates

- Before resuming or retrying, read the run status. If a matching pin already exists, record its URL and finish without creating another.
- A timeout or pending Canva job is not proof of failure. Resolve its outcome before trying either route again. If it cannot be established, record `publication-unconfirmed` and stop.
- On success, verify the published image, title/description, selected board, and homepage destination where accessible. Save `published`, pin URL/ID, route, and verification evidence. Pinterest may append tracking parameters to the homepage link; verify the same domain and homepage path.
- If the user says to pause, save `publication_hold: true` and make no new attempts until explicitly resumed. An interrupted click may already have submitted a job; inspect its result instead of claiming it was cancelled.
- If upload, login, or publishing remains blocked, preserve the design/export and explain the specific action needed. Do not repeatedly submit unchanged failures.

## Tested result

On 2026-09-13, Canva returned a publishing-app error for the first outfit. Direct Pinterest upload then succeeded after Chrome file URL access was enabled. The board increased from 57 to 58 pins; the live image, copy, and homepage link were verified at [the published test pin](https://uk.pinterest.com/pin/557672366384571970/). This validates the direct route, not Canva publication or performance with a different assistant model.

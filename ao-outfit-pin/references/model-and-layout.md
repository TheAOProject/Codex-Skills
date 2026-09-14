# Model image and Canva layout

## Preserve the identity

Retrieve `AO Model Reference` from the locations in SKILL.md and use it as an actual image reference. Keep durable copies in Canva and the project run; do not rely on expiring thumbnail URLs or temporary clipboard paths.

Preserve the face, adult appearance, hairline, straight dark hair, stubble, skin tone, and tall lean proportions. The original poster is only a layout/build example; its curly-haired person is not the established identity. Reference-guided generation still needs visual comparison and does not guarantee identical faces.

## Generate the wearing model

Label each reference's role: identity or specific garment/accessory. Inspect local images before edits and obey the current image tool's reference mechanism and limits. The tested tool accepted five reference paths per call. When references exceed its limit, use the identity and key garments first, then edit with the resulting model plus remaining products while preserving already matched items. Do not silently omit references.

Adapt this prompt to the verified manifest:

> Create a photorealistic full-body fashion image of one fictional adult male for The AO Project. Preserve the supplied AO Model Reference's identity, face, dark straight hair, light stubble, skin tone, and tall lean build. Use a relaxed standing pose and natural anatomy. Dress him in these supplied product references: [map each image to its exact item]. Match visible colours, silhouette, texture, length, fastenings, soles, and distinctive details. Soft neutral studio lighting, pure white #FFFFFF background, complete head and shoes, and space around all edges. No labels, collage, background shapes, or unlisted accessories. Product cutouts and editable text will be assembled separately in Canva.

Compare the result with the identity and products: face/hair, garment length, neckline, pockets, colour, fit, eyewear, shoes/soles, and visible accessories. Check hands and limbs. A pocket accessory may be represented by its cutout rather than an unnatural wearing pose. Correct material mismatches; do not describe the generated model as an exact product photograph.

White is the default background. If transparency is needed, verify actual alpha: the first test produced an RGB checkerboard instead of transparency. Use supported background removal when needed and inspect edges. Preserve the original product cutouts rather than modifying them to match an incorrect generation.

## Assemble the layout

Copy the established seed first. Keep the model central, arrange the actual product cutouts around him, and maintain readable labels, whitespace, and the small website footer. Adapt to the number of items. Apply the label style from SKILL.md uniformly; wrap long names.

The [original example](../assets/layout-reference.png) shows hierarchy only. The written white-background, straight-hair, and uppercase-label requirements override its styling.

### Alternative when seed copying is unavailable

A tested creation route is an HTML file containing one fixed-size page marked `data-document-role="page"`, separate images, and separate text elements. Import through Canva `import-design-from-url` with `design_file` and `intended_design_type=pinterest_pin`, using the current tool schema. This retained editable Caveat text in the first test.

Inspect the imported layers. Replace embedded thumbnail fills with the original full-resolution Canva asset IDs, including the generated model asset, before saving. Do not upload a flattened collage in place of an editable Canva design, or create a public file host to transfer assets. Verify the saved page after committing.

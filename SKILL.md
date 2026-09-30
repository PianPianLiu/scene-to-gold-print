---
name: scene-to-gold-print
description: Turn a real scene photo or a selected subject into faithful pale-gold Chinese woodblock engraving on a transparent background. Use for 实景金色版画, 酒店金色版画, 单色金色版画, 雕版线描 or transparent gold assets from architecture, interiors, gardens, streets, landscapes and event structures. Support 丰富刻线版, 疏朗留白版 or both, user-selected subjects, and omission of text that cannot be reproduced accurately.
---

# 实景金色版画

Create gold engraving artwork from the user's photograph. Read the `imagegen` skill and use its built-in image editing tool. The current photo is the sole authority for the real subject, camera view, objects, and spatial layout. The bundled images are **style-only** references; never transfer their hotel, canopies, trees, rockery, text, or other scene content to the current photo.

## Variant selection

Use descriptive names in the user-facing choice, not version numbers. Treat 丰富刻线版 and 疏朗留白版 as provisional names that may be renamed with the user while preserving the asset mapping.

If the user invokes this skill without choosing a style, proactively offer this short choice before generating:

> 这张想生成哪种效果？
> - 丰富刻线版：细节更丰富，传统雕版感更浓。
> - 疏朗留白版：刻线更简洁，透明留白更多。
> - 两种都生成：分别出图，方便比较。

Use a tappable selection tool when available; otherwise present the choices in text. Inspect the photo while awaiting the answer, but wait for a selection before image generation. Never silently default to both. If the user already chose a style or both, proceed without asking again. Accept descriptive synonyms and legacy 第一版／第二版 requests for compatibility, but present results by style name.

- **丰富刻线版**: Use `assets/variant-1-detailed-lakeside.png` as a style-only guide. Keep more carved foliage, water reflections, furniture, and local marks; aim for a rich traditional print while preserving the photographed layout.
- **疏朗留白版**: Use `assets/variant-2-airy-lakeside.png` as a style-only guide. Simplify foliage into broad group contours and selected inner cuts; render water with fewer separated ripples and leave more transparent negative space.
- **两种都生成**: Make **two separate images** from the same original photo, one call per variant, label them clearly as 丰富刻线版 and 疏朗留白版. Do not put both variants on one sheet or derive the second only by editing the first; use the original photo as the factual source for each. When the user selects one version, make only that version. Explicit instructions about which scene elements to keep or remove apply to both variants and override generic cleanup rules.

`assets/accepted-hotel-style.png` is the approved original hotel engraving and can be a secondary style reference for hotel exteriors. The two lakeside images establish **line density**, not subject matter. All versions use the same pale-gold, hand-cut visual language.

## Subject selection

Apply the user's selected scope before cleanup. Accept names, colors, positions, marked regions or groups of objects. A temporary advertising board or event gateway can itself be the subject. Never substitute a distant building for a selected foreground object.

If no subject is specified, infer the main subject or coherent scene and briefly state the scope; clarify only when several plausible targets would lead to materially different results. Keep selected structural parts, supports, attached decoration and requested context. Remove unrelated objects behind or through the subject. A bounding rectangle is not the object's boundary: a gateway opening must be transparent, while its beam and legs remain intact.

Preserve source proportions and perspective. Fit an isolated subject to the canvas with margins; for a whole scene, preserve source orientation by default. Do not invent major unseen parts to complete a cropped subject. Reconstruct minor occlusions only from visible evidence.

For example, when the user selects a foreground red event gateway, retain its beam, legs, attached graphic panels and accurately reproducible lettering. Remove the background hotel, trees, cars, road and sky; make the central opening transparent. Convert red to the chosen gold language. These removals are example-specific, not universal cleanup rules.

## Text accuracy

The user accepts omission of text that cannot be accurately reproduced. Preserve accurate text when feasible; omit uncertain or distorted headlines, small copy and numbers without further confirmation. Continue the surrounding gold surface cleanly and preserve the underlying sign or support geometry. Never substitute pseudo-characters or approximate wording. If inspection reveals malformed text, remove it in a targeted correction. A later explicit request for exact lettering overrides omission and requires honest reporting of any limitation.

## Workflow

1. Inspect the actual subject and identify its silhouette, proportions, camera perspective, repeated structural rhythm, permanent features, meaningful foreground elements, and any legible original signage. For buildings, identify roof/eave, facade, entrance, wings, and windows. For interiors or grounds, identify the real furniture, tents, canopies, shore, lake, trees, people, and their relative placement. Preserve what the user explicitly names, even if temporary.
2. Inspect and actually supply the real photo as the edit target and the selected variant image as a separate **style-only** reference; do not silently substitute a verbal description for an available reference image. State each image's role. If the user supplies a different style reference or changes the established style, follow that request.
3. Remove only unwanted clutter and background. Do not automatically remove people, tents, event structures, trees, or water when they are the subject or the user asks to keep them. Reconstruct occluded structure conservatively from visible repetitions; never invent extra architecture, furniture, cultural ornaments, or scenery.
4. Render the retained subject or scene without additional cropping in one muted pale champagne-gold visual language: strong but slightly irregular outer contours, finer structural cuts, selective carved marks, restrained flat masses, and transparent negative space. Set the amount of detail by the chosen variant. Keep the photographed subject recognizable at poster size.
5. Request actual transparent alpha, including between strokes and in all dark/negative areas. Do not generate a black or white rectangular background, photographic lighting, gradients, cast shadows, glowing edges, or additional copy. Retain original signage only if characters can be accurately formed; otherwise omit the lettering and keep blank supports or a clean sign area, following Text accuracy. Never invent plausible-looking Chinese characters.
6. Inspect each result against the photo. Check the scene layout, required elements and original sign, then perform the delivery acceptance checks below for each requested variant. Iterate with one targeted correction when a material defect is present. If image generation still cannot meet exact single-ink purity, describe the limitation honestly rather than presenting it as a guaranteed production-perfect one-color file. Preserve any version the user explicitly selects.

## Prompt scaffold

> Image 1 is the sole factual reference and edit target; image 2 is style-only for the selected line-density variant. Preserve [selected subject], its camera perspective, real structure and [required attached details]. Remove [non-target objects]; make [true openings] transparent. Omit lettering that cannot be accurately reproduced. Turn this scene into a hand-carved Chinese woodblock engraving in one muted pale gold. For 丰富刻线版, use richer selected engraving marks; for 疏朗留白版, simplify inner marks and increase transparent negative space. Actual alpha transparency everywhere outside the gold marks, including dark recesses, gaps, sky, and water between ripple strokes. No new architecture, scenery, ornaments, text, alternate colors, photographic texture, gradients, shadows, or background. Leave transparent margins around the retained subject or scene.

Use the current photo's exact readable sign text where needed; never hard-code the example hotel's name for a different subject.

## Reference and transparency checks

Use the bundled references for their engraving language and selected line density, not as a requirement for global bright surfaces, bright rims or shallow relief. Do not copy their visible halos, colored fringes or background artifacts. Do not copy reference background artifacts. Apply the delivery checks below rather than relying on a transparent-image preview alone.

## Delivery acceptance: transparent PNG

Complete cleanup and inspection before delivery; do not routinely hand the user an image with known fixable defects and ask them to repair it. Use the imagegen workflow for corrections and preserve the selected composition, style and subject. Verify each requested variant separately; do not silently drop one because another looks better.

1. **Inspect real compositing.** Make inspection-only composites of the actual PNG over white and a dark contrasting background such as navy. View the complete composition and representative edges at native scale: rooflines, thin supports, foliage, openings and fine strokes. These composites are QA previews, not substitutes for the transparent deliverable. Check visible color fringes, halos, residual background, checkerboard baked into the pixels and lost fine detail.
2. **Read alpha correctly.** Confirm an alpha channel and genuinely transparent background/openings, but do not treat a transparent corner as sufficient proof. Examine the alpha distribution and representative intended solid regions. In 8-bit alpha, 0 is transparent and 255 opaque; values such as 252–254 are nearly opaque. A large count of pixels below 255 alone is not evidence of unwanted translucency. Assess meaningful background show-through on the composites. Preserve intentional negative cuts and antialiased edges; never threshold all partial alpha indiscriminately.
3. **Separate hidden RGB from visible defects.** Fully transparent pixels may contain arbitrary RGB colors that do not appear in normal compositing. Do not declare red/yellow fringes from raw RGB or a single preview alone. Judge colors with alpha applied and verify that an alleged fringe actually appears on a contrasting background. Conversely, an alpha channel does not excuse visible contamination. Color-count checks can support but not replace visual review.
4. **Correct only demonstrated problems.** Remove visible contamination, unintended background or malformed text through a targeted edit without restyling the subject. Recheck the edited file because generation can alter structure or introduce new defects. If a targeted correction still fails, report the specific remaining problem and provide a clearly labeled preview rather than claiming a finished asset. Do not promise guaranteed production quality from prompting alone.
5. **Deliver with evidence.** Save the original-resolution PNG with its alpha intact, and offer the light/dark inspection composite when useful. State dimensions and the checks actually passed. Describe suitability narrowly: normal layout use after successful compositing checks; do not claim print readiness, strict single-ink separation or suitability at an unspecified print size. Do not call a failed check a pass or exaggerate near-opaque alpha as a defect.
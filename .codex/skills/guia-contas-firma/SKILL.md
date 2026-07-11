---
name: guia-contas-firma
description: Create a faithful master photo and an 8-second TikTok/Flow video prompt for this exact Guia Fio de Contas de Exu e Pombagira: one long continuous guide, one single larger firm bead, repeating groups of three black then three red handmade beads. Use for every new photo, video prompt or creative of this specific product.
---

# Guia Contas Firma — Foto e Vídeo

Run the complete product-to-video workflow in one request: identify the cataloged product, use original references as the visual source of truth, generate a new photo with the environment and scale already defined, and return a Flow-ready video prompt. Produce one photo and one video prompt per request unless the user asks for a different quantity.

## Automation contract

Apply this contract automatically whenever the skill runs; the user must not need to repeat it:

- Before generating any photo, read `references/photo-fidelity-prompt.md` completely and use it as the canonical photo prompt.
- If any instruction in this file, `product.json`, a styling request or prior conversation conflicts with the canonical photo prompt, the canonical prompt and the original product photos win.
- Preserve the canonical prompt's default simple light neutral background unless the user explicitly requests another environment. Even then, change only the environment and keep every product lock unchanged.

- Recreate the same physical product from the real reference photos. Change only the environment, lighting, camera framing and the guide's non-destructive pose.
- Lock all product traits: one long thin continuous guide; groups of three black beads followed by three red beads; visible handmade bead-to-bead irregularity; one single larger grooved black/dark-red firm bead; no clasp, hook, metal or open ends.
- Never reinterpret grooves in the firm as separate beads. Never clean up, regularize, industrialize or redesign the small beads.
- Use generated images only as outputs. Never feed them back as product-identity references.
- If the user supplies only an environment request, infer every product requirement from this skill and the real references.
- If the user supplies no environment, choose a tasteful new setting that does not obscure the product.
- Reject and regenerate whenever the result is merely similar instead of the same product.

## Workflow

1. Resolve the product.
   - Prefer the product ID or slug supplied by the user.
   - If the user says “este produto” or “a guia”, search the product catalog and its `product.json` first.
   - Load the real product photos before any generated image or styling reference. Treat only real product photos and confirmed product data as authoritative for product identity.
   - Do not impose a numeric length. Use `assets/customer-reference-open-guide-20260710.png` as the authority for apparent length, thinness and scale relative to a real hand.
   - Treat the guide as one complete continuous closed loop. It has no hook, clasp, metal fastener, open ends or loose terminal beads. Never infer hardware from generic necklace conventions.
   - Load `assets/customer-reference-open-guide-20260710.png` first for real-world scale, thinness and open layout. Load `assets/gia.webp` second for bead morphology and color sequence. Use `assets/listing.png` only as a supporting view.
   - Do not pass `macro-reference-large-beads.png`, `nail-reference-unha06.jpg` or any generated master photo by default. Use them only when the user explicitly requests a macro detail, styled hand or matching composition. They must never override the real product photos.

2. Build the master-photo specification.
   - Keep the product completely unchanged: category, color, shape, pattern, texture, apparent material, proportions, quantity, visible details, and variant.
   - Keep the entire long guide visibly continuous. When opened or stretched into curves, both sides must remain connected as one uninterrupted loop; never display two ends.
   - Preserve exactly one central firm: one single larger continuous bead, thick and elongated but proportional, with an irregular rounded block/barrel body, glossy black base, dark-red or wine marbling, and visible reliefs or grooves. The grooves belong to the same bead; never split it into modules, duplicate it or distribute firm-like beads elsewhere.
   - Treat changing the arrangement as a geometric repositioning of the same physical cord, never as rebuilding or redesigning the guide. The requested result may uncoil or stretch the guide, but must appear to contain the same existing beads moved with the cord.
   - Preserve the bead scale and morphology from the open customer photo. The small beads are genuinely small and fine relative to the fingers and the single firm bead. They mix rounded, slightly square and short cylindrical shapes with visible handmade variation in size, thickness, alignment and gloss. Do not enlarge them into chunky nuggets, blocks or oversized decorative beads.
   - Preserve the confirmed color sequence along the small-bead strand: three black beads followed by three red beads, repeating around the guide. Count each visible group as 3 black + 3 red. The handmade irregularity belongs to each bead's shape, size, thickness, orientation, spacing and gloss; it must not change the three-and-three color count.
   - Preserve subtle size outliers and orientation changes without exaggerating them. The correct look is handmade and irregular, not rough, chunky or caricatured.
   - Keep the environment visually simple so it cannot compete with product identity. Default to a neutral matte surface and soft natural light.
   - Do not add a hand by default. Add one only when the user asks for scale or styling; keep it outside the guide without touching or covering the product.
   - Use a nail reference only when the user explicitly asks for that manicure.
   - Use portrait 9:16 when the image will feed a vertical video. Do not invent scale unless a reference confirms it.
   - Include hard negatives: no extra pieces, altered colors, changed proportions, invented accessories, logos, text, watermark, or unsupported claims.

3. Generate the photo with the built-in image generation tool.
   - Read `references/photo-fidelity-prompt.md` completely immediately before composing the image-generation request. Include its full product description, display scenario, negative instructions and final priority in the request; do not summarize away constraints.
   - Pass `customer-reference-open-guide-20260710.png` first and `gia.webp` second. These two real product photos are the default generation inputs. Add `listing.png` only if another full-product view is needed.
   - Tell the image model explicitly: "Preserve the apparent length, thinness, small-bead scale and one single larger firm bead from the real product photos. Change only the continuous loop's pose or setting; do not regenerate, redesign, standardize or replace the beads. There is no hook, clasp, fastener or open end."
   - Use the original full product photos to copy the small-bead morphology while enforcing the confirmed repeating groups of three black followed by three red. Treat a one-by-one black/red alternation, incorrect group counts, a repeated bead mold or industrial uniformity as fidelity failures.
   - When bead identity is hard to read, create and pass lossless detail crops only from the real product photos. Label each crop as a section of the same strand, never as permission to duplicate it.
   - Keep styling references out of the first generation attempt. Introduce them only after a product-faithful photo passes every fidelity gate.
   - Inspect the result before accepting it. Reject and regenerate if the product is shortened, duplicated, missing parts, visually different, open-ended or fitted with invented hardware. Repositioning the intact continuous loop is allowed; replacing the bead population is not.
   - Reject if the small beads become visibly larger or chunkier than in the open customer photo; if the guide becomes short, thick or rigid; if there is more than one firm; if the firm is split into multiple beads or modules; if the small-bead colors fail the repeating 3-black/3-red groups; or if bead shapes and spacing become machine-perfect.
   - Reject an attractive image if any product gate fails. Iterate on one failure at a time, using only the real product references. Save only an accepted result as a new versioned asset; never overwrite an original reference.
   - Build every image request around this exact core instruction: `Mude somente o ambiente, a iluminação, o enquadramento e a posição não destrutiva da guia. Preserve o mesmo produto físico das fotos reais de referência; não reconstrua, redesenhe, padronize nem substitua nenhuma conta.`

4. Write the Flow video prompt from the accepted photo.
   - Start with: `VÍDEO 1: Foto em anexo: use a foto em anexo como referência visual exata e obrigatória do cenário e do produto.`
   - Specify 8 seconds, vertical 9:16 and the exact product and environment from the accepted photo.
   - Treat the accepted photo as the first frame and absolute product lock. Animate only a slow camera movement or subtle light change. Never reconstruct the bead strand, change a 3-black/3-red group, duplicate or split the single firm bead, or modify product scale.
   - For fragile or intricate products, prohibit pulling, unrolling, rearranging, morphing, or any motion that makes the model reconstruct the product.
   - Include a simple Brazilian Portuguese voice line that identifies the product, uses only supported benefits, sounds like a customer who bought and approved it, and fits approximately 8 seconds. Avoid “parece”, “talvez” and “aparentemente”.
   - Include negative restrictions: no extra accessories, color changes, quantity changes, text overlays, logos, phone screen, interface, face, or full body.
   - Reuse the same automation contract in the video prompt. The video may animate only camera or light; it must not animate, move, recount, morph or reconstruct any bead or the firm.
   - Read `references/photo-fidelity-prompt.md` again and transfer every product-identity and negative restriction into the Flow prompt. The accepted photo locks the first frame; the canonical prompt locks the product throughout all frames.

5. Deliver the accepted photo and ready-to-paste video prompt, plus the product ID and saved path when useful. Do not produce alternatives unless requested.

## Fidelity gates

Before delivering, verify:

- The generated photo still depicts the same real product, not a stylized approximation.
- There is exactly one firm in the entire guide. It is one single larger continuous bead with an irregular rounded block/barrel silhouette, black/dark-red marbling, gloss, visible grooves and correct connection to the small beads.
- The small beads retain the real open-photo scale: fine and much smaller than a finger width and the single firm bead, with rounded, slightly square and short cylindrical handmade variation. They are not enlarged into chunky nuggets.
- The small-bead color sequence repeats three black beads followed by three red beads. Shape, size, orientation, spacing and gloss vary naturally within and between those fixed-count groups.
- No two adjacent beads look like exact copies. The variation is visible but remains proportional to the real small beads.
- Opening or stretching a coiled guide changes only the cord's pose. It does not authorize replacing the real beads with a newly synthesized, cleaner or more uniform bead set.
- The guide remains one complete long continuous loop with no hook, clasp, metal fastener, open end or loose terminal bead. Do not enforce a numeric length; match the open customer photo's apparent proportions.
- Product scale matches any confirmed measurement or hand reference.
- If a hand is used for scale, it stays beside the guide with no contact, overlap, or obstruction of any product detail.
- If a nail reference is supplied, the same nail style appears consistently in the photo and every video frame.
- The environment is already present in the photo and will not need to be invented by the video model.
- Optional styling elements never outweigh, obscure or alter the product.
- The video prompt freezes the product's position and limits motion to the camera or lighting; any hand remains completely still beside the guide.
- The spoken line does not claim protection, transformation, certification, durability, or any unsupported result.

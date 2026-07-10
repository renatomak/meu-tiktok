---
name: tiktok-product-video-pipeline
description: Create one faithful master product photo and one ready-to-use 8-second TikTok/Flow video prompt for a cataloged product. Use whenever the user asks for a new product video, new photo plus video prompt, or the next creative for a product.
---

# TikTok Product Video Pipeline

Run the complete product-to-video workflow in one request: identify the cataloged product, use original references as the visual source of truth, generate a new photo with the environment and scale already defined, and return a Flow-ready video prompt. Produce one photo and one video prompt per request unless the user asks for a different quantity.

## Workflow

1. Resolve the product.
   - Prefer the product ID or slug supplied by the user.
   - If the user says “este produto” or “a guia”, search the product catalog and its `product.json` first.
   - Load original product photos, any supplied macro/detail references, and relevant listing screenshots. Treat product photos and macro references as authoritative for visual identity; use descriptions and reviews only for confirmed context.
   - For the guide product, use the confirmed 60 cm length from the customer screenshot and use a hand as a scale reference.

2. Build the master-photo specification.
   - Keep the product completely unchanged: category, color, shape, pattern, texture, apparent material, proportions, quantity, visible details, and variant.
   - Treat a macro reference as a hard identity lock. For this guide, preserve the cluster of large irregular rounded-rectangular/barrel-shaped beads with black and dark-red marbling, visible separations/grooves, glossy finish, and its exact connection to the small red/black beads. Do not replace it with smooth round beads, uniform cylinders, gemstones, or a different count or silhouette.
   - Define the final environment in the photo itself. Make it refined, attractive, product-appropriate, and stable enough to become the video's first frame.
   - Prefer a clear, separated arrangement over a tangled or crowded one. When a hand is needed for scale, place it beside the guide, parallel and close enough to show proportion, but never touching, holding, crossing over, or covering any bead or section of the product. Keep the entire hand outside the guide's outline.
   - When the user supplies a nail reference, use it for the hand in both the photo and the video: match nail length, shape, colors, finish, pattern and decorative details. Copy only the manicure/hand styling, never the reference image's product or background.
   - Use portrait 9:16 when the image will feed a vertical video. Do not invent scale unless a reference confirms it.
   - Include hard negatives: no extra pieces, altered colors, changed proportions, invented accessories, logos, text, watermark, or unsupported claims.

3. Generate the photo with the built-in image generation tool.
   - Pass the original product image and every supplied macro/detail image as identity references, not merely style references.
   - Pass any scale, lifestyle or nail image as a secondary reference and state exactly what to borrow from each one (for example, hand scale only; nail reference only for manicure styling; place the hand beside the guide without contact or overlap; never copy phone UI or unrelated background).
   - Inspect the result before accepting it. Reject and regenerate if the product is shortened, duplicated, rearranged, missing parts, or visually different.
   - Save project-bound outputs as a new versioned asset; never overwrite the original reference.

4. Write the Flow video prompt from the accepted photo.
   - Start with: `VÍDEO 1: Foto em anexo: use a foto em anexo como referência visual exata e obrigatória do cenário e do produto.`
   - Specify 8 seconds, vertical 9:16, ultra-realistic POV/TikTok Shop language, iPhone Pro Max look, and the exact environment from the photo.
   - Treat the photo as the first frame and visual lock. Animate only camera movement or light. If a hand appears, freeze it completely beside the guide and preserve the exact nail reference styling; do not animate fingers, grip, touch, pull, or reposition it.
   - For fragile or intricate products, prohibit pulling, unrolling, rearranging, morphing, or any motion that makes the model reconstruct the product.
   - Include a simple Brazilian Portuguese voice line that identifies the product, uses only supported benefits, sounds like a customer who bought and approved it, and fits approximately 8 seconds. Avoid “parece”, “talvez” and “aparentemente”.
   - Include negative restrictions: no extra accessories, color changes, quantity changes, text overlays, logos, phone screen, interface, face, or full body.

5. Deliver the accepted photo and ready-to-paste video prompt, plus the product ID and saved path when useful. Do not produce alternatives unless requested.

## Fidelity gates

Before delivering, verify:

- The generated photo still depicts the same real product, not a stylized approximation.
- The macro identity detail matches: large marbled beads keep the same irregular silhouette, black/dark-red pattern, grooves, gloss, spacing and connection to the small beads.
- Product scale matches any confirmed measurement or hand reference.
- If a hand is used for scale, it stays beside the guide with no contact, overlap, or obstruction of any product detail.
- If a nail reference is supplied, the same nail style appears consistently in the photo and every video frame.
- The environment is already present in the photo and will not need to be invented by the video model.
- The video prompt freezes the product's position and limits motion to the camera or lighting; any hand remains completely still beside the guide.
- The spoken line does not claim protection, transformation, certification, durability, or any unsupported result.

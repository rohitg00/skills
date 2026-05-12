---
name: image-generation
description: Use when creating or editing raster images, visual concepts, product graphics, launch assets, diagrams, posters, thumbnails, reference sheets, UI mock images, or image prompts that need source-grounded claims, readable text, brand direction, and post-generation verification.
---

# Image Generation

Use this skill for image work where the output should be a generated or edited bitmap image. This is the broad image workflow; use more specific skills when the request clearly asks for Product Hunt carousel images or dense technical diagram images.

## Routing

- Use `producthunt-launch-images` for multi-image launch carousels.
- Use `technical-diagram-image` for one dense architecture/reference diagram image.
- Use this skill for everything else: concept art, product graphics, thumbnails, banners, social cards, hero images, illustration direction, UI mock images, image editing, and general image prompts.

## Required Workflow

### 1. Define The Image Job

Capture:

- User goal.
- Audience.
- Number of images.
- Format/aspect ratio.
- Style direction.
- Brand constraints.
- Required visible text.
- Required facts, commands, dates, prices, metrics, or product claims.
- Whether the task is image generation or image editing.

If the image includes factual claims, inspect sources before prompting.

### 2. Build A Fact Sheet

Use this when the image refers to a product, repo, company, event, person, or technical system:

```text
Subject:
Audience:
Use case:
Required dimensions/aspect:
Brand colors:
Allowed logo/visual identity:
Visible headline:
Visible subtext:
Verified facts:
Commands/URLs/ports:
Metrics/counts/dates:
Source links/files:
Unknowns to omit:
Negative constraints:
```

Never invent metrics, dates, commands, screenshots, logos, claims, or product UI. If a fact is not verified, omit it or label it as conceptual.

### 3. Choose The Image Type

| Type | Best structure |
|---|---|
| Product graphic | headline, product surface, proof chips, command strip |
| Social card | one hook, one visual metaphor, one verified fact |
| Thumbnail | large readable phrase, one focal object, high contrast |
| Hero image | realistic subject/product, atmospheric background, no text-heavy layout |
| Technical visual | topology, labels, arrows, source-grounded nodes |
| Poster | compact header, sections, tables, diagrams, legend |
| Edit | preserve key subject, list exact changes, list what must remain unchanged |

### 4. Write The Prompt

A strong prompt includes:

- Subject and purpose.
- Target format and aspect ratio.
- Visual style.
- Composition and layout.
- Exact visible text.
- Brand/color rules.
- Source-grounded facts only.
- What to avoid.
- Verification priorities.

Template:

```text
Create <number/type> image for <subject>.
Use case: <launch/docs/social/reference/thumbnail/etc>.
Audience: <who should understand it>.
Format: <aspect ratio/dimensions if known>.

Style: <specific visual style, product surface, screenshot, poster, editorial, technical, etc>.
Composition: <foreground/midground/background, panels, cards, grid, table, diagram, focal object>.
Visible text: "<exact text>".
Facts to include: <verified facts only>.
Brand/color rules: <colors and semantic meanings>.

Negative constraints: no fake metrics, no malformed commands, no stock art, no unwanted logos, no tiny unreadable text, no unsupported claims.
Verification priority: <what must be correct>.
```

### 5. Generate And Verify

After generation, inspect the output for:

- Correct subject.
- Correct project/product/person name.
- Readable required text.
- Accurate commands, URLs, metrics, dates, and claims.
- Brand consistency.
- Layout fit.
- No unwanted artifacts, broken UI, or unsupported claims.

Regenerate only the failed image when possible. Make the next prompt shorter, more explicit, and more constrained around the failure.

## Editing Existing Images

For image edits:

1. Identify what must change.
2. Identify what must stay unchanged.
3. Preserve identity, composition, lighting, and brand unless asked otherwise.
4. Give exact edit instructions.
5. Verify the edit did not damage important unchanged areas.

Edit prompt template:

```text
Edit the provided image.
Change: <specific changes>.
Preserve: <faces/products/text/layout/colors/background/items>.
Style match: <lighting, texture, camera, illustration style>.
Avoid: <unwanted changes>.
```

## Text In Images

Image models can mangle text. Keep visible text:

- short.
- large.
- high contrast.
- repeated only when necessary.
- exact for commands, URLs, names, metrics.

For text-heavy needs, prefer fewer words and more structure. If a dense table is required, consider a diagram-specific skill and verify carefully.

## Color Semantics

Use semantic color when the image explains a system:

- Green: success, local, free, default, safe, verified.
- Orange: optional, paid, external, model call, warning.
- Blue: network, API, cloud, integration.
- Red: error, blocked, risk, destructive path.
- Gray/black: structure, labels, inactive states.

State the semantic rule in the prompt when colors carry meaning.

## Quality Bar

The image should:

- communicate the intended point within three seconds.
- look specific to the subject, not generic.
- avoid fake product evidence.
- use realistic surfaces where possible.
- keep text legible.
- match the requested format.
- survive a quick visual audit.

## Output Format

For a single image, return the absolute path:

```text
/absolute/path/to/image.png
```

For multiple images, return ordered paths:

```text
1. /absolute/path/01-name.png
2. /absolute/path/02-name.png
3. /absolute/path/03-name.png
```

## Common Pitfalls

- Asking for too much tiny text.
- Trusting generated text without visual review.
- Inventing product metrics.
- Using decorative color with no meaning.
- Making generic hype art when the user needs proof.
- Forgetting aspect ratio.
- Editing too broadly and damaging what should stay unchanged.
- Reusing outdated facts from memory.

## Checklist

- [ ] Image type selected.
- [ ] Facts checked when claims appear.
- [ ] Exact visible text specified.
- [ ] Brand/color direction specified.
- [ ] Negative constraints included.
- [ ] Generated or edited image was visually checked.
- [ ] Final answer returns usable file paths.

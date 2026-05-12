---
name: producthunt-launch-images
description: Use when creating Product Hunt launch carousel images for developer tools, AI tools, open-source projects, GitHub launches, or technical products. Research comparable launches, inspect the project, extract verified proof points, then generate 4-5 launch-ready images with consistent branding, product surfaces, readable copy, and source-grounded claims.
---

# Product Hunt Launch Images

Use this skill to create a Product Hunt image carousel for a software project, especially AI coding tools, developer tools, open-source infrastructure, GitHub launches, local-first products, API tools, or technical SaaS.

The target is not a generic promotional poster. The target is a 4-5 image launch sequence that looks credible to developers: product surfaces, proof, commands, architecture, workflow change, and a clear reason to try the tool now.

Strong outputs combine:

- A clear launch-cover promise.
- Realistic UI, terminal, editor, dashboard, or browser surfaces.
- One workflow image showing before and after.
- One proof image with traceable metrics or concrete capability evidence.
- One architecture or integrations map.
- One quick-start image with exact commands and expected first result.

## When To Use

Use when the user asks for:

- Product Hunt images.
- Launch carousel images.
- App launch screenshots for a GitHub project.
- Developer-tool promotional images.
- A visual package for an open-source tool.
- Product graphics where proof and quick start matter.

Do not use for:

- A single dense architecture diagram. Use `technical-diagram-image`.
- A general image request with no launch context. Use `image-generation`.
- Marketing hero page implementation.
- Social post copy only, unless launch images are also requested.

## Required Workflow

### 1. Learn From Comparable Launches

Inspect Product Hunt examples or search current launch images first. If direct pages are blocked, use web search, browser snapshots, cached snippets, screenshots, repo docs, or comparable public images.

For AI and developer tools, useful launch references include:

- AI IDEs and coding agents: product screenshots, editor surfaces, model/interface announcements, small number of strong images, minimal fluff.
- Browser or app builders: idea-to-app surfaces, before/after flow, browser preview, terminal command.
- Open-source coding assistants: dark or grid style, VS Code/editor framing, repo proof, install commands.
- Infrastructure tools: architecture diagram, benchmark proof, CLI quick start, integrations map.

Extract patterns, not exact layouts:

- They show the product doing something.
- They make the product name and promise visible at thumbnail size.
- They use short, legible headlines.
- They include proof only when credible.
- They show commands, screenshots, or workflows instead of stock art.

### 2. Inspect The Project

For GitHub projects, inspect at least:

- README.
- package metadata.
- docs or getting-started guide.
- benchmark docs, if claims exist.
- architecture docs or agent instructions, if relevant.
- CLI entrypoint docs, if commands matter.
- source files for formulas, defaults, ports, route counts, and registry counts when using technical metrics.

Capture:

- One-line purpose.
- Project audience.
- Install command.
- Demo or quick-start command.
- Doctor/status/health command.
- Local ports or URLs.
- Supported integrations.
- License.
- Current version.
- Benchmarks and source files.
- Counts such as tools, endpoints, plugins, tests, commands, hooks, adapters, or routes only if present in source/docs.
- What is free/local/open-source.
- What is optional/paid/cloud/model-dependent.

Never invent metrics. If a number is not in README, docs, benchmark files, package metadata, boot logs, or source, do not use it. Prefer omitting weak numbers over making a carousel look more impressive.

### 3. Choose The Carousel Structure

Default 5-image structure:

1. Cover: product promise, UI screenshot/mock, proof chips.
2. Workflow: before/after story, what changes for the user.
3. Proof: benchmark table, capability matrix, cost/token comparison, or source-backed metric panel.
4. Architecture: integrations, surfaces, ports, server/data flow.
5. Quick start: exact commands, local URL, first success output.

Default 4-image structure:

1. Cover.
2. Workflow.
3. Proof or architecture, whichever is stronger.
4. Quick start with compact architecture strip.

If the project has no verified metrics, make the proof slide a "verified capabilities" slide: checklist, source-backed feature matrix, real commands, supported integrations, or workflow evidence.

### 4. Define Brand And Color Semantics

Use the project's existing brand if available. If not, derive a clean developer-tool brand:

- Background options: light graph paper, dark IDE canvas, terminal black, high-contrast docs layout, or subtle product screenshot collage.
- Typography: bold sans for headline, mono for commands and metrics.
- Surfaces: browser windows, terminal cards, editor panels, tables, diagrams.
- Color semantics must mean something.

Common color bindings:

| Color | Meaning |
|---|---|
| Signal green | local, free, default, cached, success, deterministic, open-source |
| Ember orange | paid, optional, external provider, model call, expensive path |
| Blue | network, API, cloud, integration |
| Purple | AI/model layer, only if the project already uses it |
| Neutral black/gray | scaffolding, labels, secondary paths |

Do not use color only as decoration. If green and orange appear, the legend or visual hierarchy should make their meaning clear.

## Prompt Pattern

Use one generated image prompt per carousel image. Each prompt should include:

- `Product Hunt launch carousel image N of M for <Project>`.
- Slide focus.
- Visual inspiration from successful developer-tool Product Hunt launches.
- Brand colors and semantic color rules.
- Exact headline text.
- Exact commands or metrics only when verified.
- Realistic product surfaces to show.
- Negative constraints: no mascots, no stock art, no fake metrics, no glossy 3D, keep text readable.

### Cover Prompt

```text
Product Hunt launch carousel image 1 of 5 for <Project>.
Create a polished launch cover in the style of successful developer-tool Product Hunt launches: real product surface, strong headline, crisp screenshot composition, no generic illustration.

Brand: <brand tokens>. Signal green means <local/free/default/success>. Ember orange means <optional/paid/external/model>.

Large headline: "<core promise>."
Subhead: "<audience or supported ecosystem>."

Center: desktop UI mockup showing <viewer/app/editor/dashboard> with <realistic cards/logs/search/results>.
Bottom terminal strip: `<install or demo command>`.
Proof chips: "<verified metric or feature>", "<verified integration>", "<license/version>", "<local URL or port>".

Keep text readable at Product Hunt carousel size. No mascots, no stock art, no fake metrics, no glossy 3D, no tiny paragraphs.
```

### Workflow Prompt

```text
Product Hunt launch carousel image 2 of 5 for <Project>.
Focus: workflow transformation from <pain> to <outcome>.
Use a clean technical product screenshot style: split-screen, real app surfaces, minimal copy, strong before/after.

Title: "<pain-killer headline>."
Left panel labeled "Before": <current painful workflow, missing context, manual steps, slow setup, fragmented tools>.
Center pipeline: <capture> -> <process> -> <index/route/build> -> <result>.
Right panel labeled "After": <specific product outcome with retrieved result, app preview, generated artifact, or working command>.
Include command strip: `<demo command>`.

No abstract neon, no fake dashboards, no vague AI magic.
```

### Proof Prompt

```text
Product Hunt launch carousel image 3 of 5 for <Project>.
Focus: proof and credibility.

Header: "<proof headline>."
Main panel: <benchmark table, capability matrix, verified counts, or source-backed comparison>.
Rows or cards: <verified facts only>.
Side panel: <source labels, package version, benchmark scope, test count, or doc path>.
Footer: "Source: <README.md / benchmark file / package.json / source path>".

Make numbers large and readable. If exact metrics are unavailable, use a verified feature matrix instead of invented numbers.
```

### Architecture Prompt

```text
Product Hunt launch carousel image 4 of 5 for <Project>.
Focus: architecture and integration map.

Title: "<architecture headline>."
Left column: <callers, agents, SDKs, users, inputs> as labeled pills.
Middle: <server/core/engine> with layers: <surfaces>, <processing>, <state>, <indexes>, <workers>.
Right column: outputs: <results, UI, API responses, files, dashboards, deployments>.
Bottom strip: exact ports, commands, or integrations only if verified.

Color semantics: signal green for <local/free/default path>. Ember orange for <optional/paid/model/external path>.
Use orthogonal arrows, readable labels, and technical surfaces. No decorative node soup.
```

### Quick-Start Prompt

```text
Product Hunt launch carousel image 5 of 5 for <Project>.
Focus: quick start and first value.

Headline: "<time-to-value headline>."
Large terminal card with exact commands:
`<install>`
`<demo or run>`
`<doctor/status/health>`

Side browser/app card: <local URL or expected first result>.
Footer chips: <runtime>, <license>, <version>, <important dependency>, <supported platform>.

Style: product screenshots and commands over hype. All command text must be large and readable.
```

## Project Fact Sheet Template

Before generating, fill this mentally or in notes:

```text
Project:
Repo:
Audience:
One-line purpose:
Install command:
Demo command:
Doctor/status command:
Local URLs/ports:
License:
Version:
Top integrations:
Verified metrics:
Source files:
Local/free path:
Optional/paid path:
Risks or caveats:
```

## Verification

After generation, inspect at least the key images:

- Cover: headline readable, product name correct, no wrong brand, command not broken.
- Workflow: before/after makes sense and does not invent a fake product capability.
- Proof: metrics match source and are readable.
- Architecture: data flow is coherent, semantic colors are used correctly.
- Quick start: command text is readable and exact.

If one image fails, regenerate that image only with a shorter, stricter prompt.

## Output Format

Return generated image paths in carousel order:

```text
1. /absolute/path/01-cover.png
2. /absolute/path/02-workflow.png
3. /absolute/path/03-proof.png
4. /absolute/path/04-architecture.png
5. /absolute/path/05-quickstart.png
```

## Common Pitfalls

1. README-only design. Launch images need proof and UI surfaces, not just the tagline.
2. Invented metrics. Developers may check GitHub immediately.
3. Too much text. Dense is allowed, but the headline, command, and main proof must be legible.
4. Generic AI glow. Product screenshots and terminal commands beat abstract effects.
5. Color without meaning. Bind color to user-relevant semantics.
6. One-image thinking. A carousel needs narrative progression.
7. Wrong command formatting. Exact CLI commands matter.
8. Not verifying generated text. Image models can mangle labels.

## Checklist

- [ ] Comparable launches were inspected or searched.
- [ ] Project README/package/docs/source were checked.
- [ ] Every metric and count is source-backed.
- [ ] Carousel has 4-5 images with distinct jobs.
- [ ] Cover promise is readable.
- [ ] Workflow image explains before/after.
- [ ] Proof image includes source label.
- [ ] Architecture image uses semantic color.
- [ ] Quick-start image has exact commands.
- [ ] Generated images were visually verified.

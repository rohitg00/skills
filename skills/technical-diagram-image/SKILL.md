---
name: technical-diagram-image
description: Use when generating a single dense technical architecture, reference poster, or system diagram image for a software project. Produces a source-grounded bitmap diagram with topology, primitives, ingest/process flow, core logic, state scopes, tiers/modules, surfaces, runtime cards, and strict semantic color rules.
---

# Technical Diagram Image

Use this skill to generate one dense technical diagram image for a software project. The output is a bitmap image from the configured image tool, not HTML, SVG, Mermaid, or a manually coded diagram.

The target visual is a printed engineering reference sheet: topology, primitives, data flow, retrieval/core logic, state scopes, tiers, surfaces, boot/runtime cards, ports, commands, formulas, and source labels compressed into one readable landscape image.

## When To Use

Use when the user asks for:

- A technical architecture diagram image.
- A dense reference poster image.
- A single PNG/JPG summarizing a GitHub project architecture.
- A diagram for engineers, reviewers, launch assets, docs, or social proof.
- An image-generation version of a system reference sheet.

Do not use when:

- The user needs editable source-controlled SVG, Mermaid, or Excalidraw.
- The deliverable is an HTML infographic.
- The user wants a multi-image Product Hunt carousel. Use `producthunt-launch-images`.
- The user wants a simple marketing hero image.

## Required Workflow

### 1. Inspect The Project First

Before prompting the image generator, gather the technical substance.

For GitHub projects, inspect as many as are relevant:

- README.
- architecture docs.
- agent or contributor docs.
- package metadata.
- benchmark docs.
- CLI entrypoints.
- state/schema files.
- retrieval/search/core implementation.
- route/tool/function registries.
- server/app boot files.
- configuration defaults.

Capture:

- Project purpose in one line.
- Main callers and integrations.
- Trigger/function/tool/API surfaces.
- State scopes, tables, indexes, queues, caches, stores.
- Core retrieval/search/processing path.
- Optional paid/model/provider path, if any.
- Local/free/default path, if any.
- Important commands.
- Ports and URLs.
- Benchmarks, formulas, defaults, weights, counts.
- Source paths for every metric/default/formula.

Never invent metrics. If exact values are unavailable, use placeholders labeled as placeholders or omit the number.

### 2. Choose The Color Semantic

Pick one binary axis the project actually has.

| Project type | Good semantic axis |
|---|---|
| AI memory / agent tooling | free/local path vs paid/model path |
| Backend/API | sync/request path vs async/background path |
| Build/CI | cached/local path vs fresh/remote path |
| Database/state | durable state vs ephemeral state |
| Distributed system | primary/leader path vs follower/replica path |
| Security/compliance | trusted/verified path vs untrusted/unreviewed path |

Default for AI tooling:

- Signal green: free path, local path, deterministic path, BM25/search/cache, local state, success.
- Ember orange: paid path, optional path, LLM/model calls, embeddings, rerank, external provider.
- Neutral black/gray: scaffolding, labels, required structure, source paths.

The top legend must state this binding clearly. Every colored line, box, and label should honor it.

### 3. Use The Canonical Poster Layout

Landscape image. Dense technical reference sheet. Top to bottom:

1. Header strip:
   - project name.
   - "technical reference" or "architecture map".
   - repo/domain.
   - subtitle.
   - semantic legend.
2. Section 01 System topology:
   - callers/apps/agents/CLI/SDK on the left.
   - triggers/tools/API/routes/workers in the middle.
   - core/state/engine to the right.
   - outputs on far right.
3. Section 02 Primitives table:
   - primitive, role, shape, notes, source file.
4. Section 03 Ingest/process pipeline:
   - event/request/input ingestion.
   - queue/parse/normalize.
   - fork into local/default path and optional/external path.
   - merge into result/core/output.
5. Section 04 Core logic:
   - formula-like blocks, scoring, routing, scheduling, retrieval, build, or decision logic.
   - defaults/weights when verified.
   - source labels.
6. Section 05 State scopes:
   - lifecycle and storage groups.
   - ephemeral/session/durable/derived/cache/paid or project-appropriate groups.
7. Section 06 Tiers/modules cascade:
   - tier, content, producer, derivation, path color, output, source.
8. Section 07 Surfaces:
   - external APIs, CLI, SDK, workers, UI, MCP/tools, adapters, hooks, webhooks.
9. Section 08 Boot/runtime:
   - setup flow, key commands, environment flags, health check, local URLs/ports.

If a project lacks some areas, keep the section structure but adapt names. Prefer source-grounded "unknown/omitted" over fake specificity.

## Visual Style

Use these constraints:

- Landscape image, ideally 1536x1024 or similar.
- Cream or light graph-paper background.
- Fine 24px-style grid, low opacity.
- Black ink text and linework.
- Thin borders, boxed tables, boxed nodes.
- Dense but organized engineering poster.
- Monospace labels for tables, formulas, counters, commands, source paths.
- Bold sans or compressed sans for header and section labels.
- Numbered sections: `§01`, `§02`, etc.
- Top legend with semantic color chips.
- Orthogonal arrows and column dividers.
- Dotted/dashed lines only for optional or secondary paths.
- No decorative icons beyond simple technical pictograms.
- No glossy 3D, stock illustration, mascot, marketing gradient, or hero-art composition.
- Text should be as readable as possible; tiny source labels are acceptable only if the major structure is clear.

The poster should feel like an engineering map someone could print and keep near their desk.

## Canonical Prompt Template

```text
Create a single high-resolution technical reference poster image for <Project>, <repo/domain>.
Style: dense engineering system reference poster, not a marketing hero.
Use a cream graph-paper background with a fine grid, black ink text, muted linework, boxed tables, boxed nodes, bold technical headings, and monospace table labels.

Strict color semantics:
SIGNAL GREEN = <green meaning>.
EMBER ORANGE = <ember meaning>.
Include a clear top legend stating these meanings and use the colors consistently.

Layout must read like a printed technical architecture poster with numbered sections:
HEADER, §01 SYSTEM topology, §02 PRIMITIVES table, §03 INGEST pipeline, §04 CORE <core name> formula area, §05 STATE scopes, §06 TIERS/MODULES cascade, §07 SURFACES, §08 BOOT/runtime.

Header:
- title: "<PROJECT> technical reference"
- repo/domain: "<repo/domain>"
- subtitle: "<short system map subtitle>"
- legend: "SIGNAL GREEN = <meaning>" and "EMBER = <meaning>"

§01 SYSTEM topology:
<callers> on the left, <triggers/tools/functions/routes> in the middle, <state/core/engine> to the right, <outputs> on far right.
Use column dividers, boxes, and orthogonal arrows.

§02 PRIMITIVES table:
Rows for <verified primitives>, with columns primitive, role, shape, notes, source-file.

§03 INGEST pipeline:
Show <ingest source> -> <queue/parse/normalize> -> fork into green path (<local/free/default stages>) and ember path (<optional/paid/model/external stages>) -> merge into <result/core/output>.

§04 CORE:
Show <algorithm/core flow>. Include formula-like blocks for <formulas/defaults> with source labels <source files>. Do not invent exact values beyond verified ones.

§05 STATE:
Show state scopes grouped by lifecycle: ephemeral/session/durable/derived/cache/paid or project-appropriate groups. Include storage/source labels.

§06 TIERS/MODULES:
Show a derivation cascade or module stack with tier/module, content, producer, path color, output, source.

§07 SURFACES:
Show external interfaces: <API/CLI/SDK/tools/UI/workers/adapters/hooks>, with exact ports/counts only if verified.

§08 BOOT:
Show setup/runtime cards with exact commands: <commands>. Include env flags and health check only if verified.

Use source-grounded labels from these files: <source paths>.
No fake metrics. If uncertain, omit the number or mark it as placeholder.
Visual tone: canonical technical reference poster, dense but organized, minimal decoration beyond the grid, no stock art, no mascot, no glossy 3D, no marketing slogans, no serif, no italic, no em-dash typography.
Make the title, legend, section labels, topology node names, and commands readable.
```

## Project Fact Sheet Template

Fill this before prompting:

```text
Project:
Repo/domain:
Purpose:
Main callers:
Inputs/triggers:
Core engine:
State/storage:
Outputs:
Local/default path:
Optional/external path:
Commands:
Ports/URLs:
Verified counts:
Verified formulas/defaults:
Source paths:
Unknowns to omit:
```

## Adaptation Patterns

- AI agent/memory product: show agents -> hooks/tools -> memory/index/retrieval -> context/output.
- Build tool: show source -> cache/dependency graph -> compiler/bundler -> artifacts.
- API/backend: show clients -> routes -> services/workers -> database/queue/cache -> responses/events.
- Kubernetes/cloud tool: show CLI/API -> cluster resources/controllers -> reconciliation loop -> status/events.
- Security tool: show inputs -> scanning/rules -> trust boundary -> findings -> remediation.

## Verification

After generating, visually check:

- Header/project name is recognizable.
- Semantic legend is visible and coherent.
- Major section labels are present.
- Main topology is directionally correct.
- Commands and ports are not malformed.
- Counts and formulas match source or are omitted.
- Color is semantic, not decorative.
- No fake product UI or unsupported claims dominate the image.

If the image is too sparse, regenerate with stronger density requirements. If text is mangled, shorten visible labels and move detail into visual structure.

## Output Format

Return the final generated image path:

```text
/absolute/path/to/generated-diagram.png
```

## Common Pitfalls

1. Creating HTML when the user asked for an image.
2. Overfitting to tiny exact text. Prioritize major labels and structure.
3. Inventing counts, formulas, benchmarks, or port numbers.
4. Decorative color with no legend.
5. Too much hero space. This is a reference poster.
6. Sparse diagrams. The target is dense and table-heavy.
7. Marketing language instead of mechanisms, commands, ports, formulas, and source labels.
8. Forgetting to visually verify the generated image.

## Checklist

- [ ] Project sources were checked or facts were supplied.
- [ ] Color semantic is explicit and project-appropriate.
- [ ] Prompt requests a single bitmap image.
- [ ] Header and numbered sections are requested.
- [ ] Topology and pipeline are both requested.
- [ ] Core formula/default area cites sources or omits uncertain values.
- [ ] Counts/ports/commands are verified or omitted.
- [ ] Generated image was visually checked.

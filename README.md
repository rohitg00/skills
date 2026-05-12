# Skills

Portable AI agent skills collection for important reusable workflows.

## Included Skills

| Skill | Location | Purpose |
|---|---|---|
| Image Generation | `skills/image-generation` | General source-grounded image generation and verification workflow. |
| Product Hunt Launch Images | `skills/producthunt-launch-images` | 4-5 image launch carousel for developer tools and open-source projects. |
| Technical Diagram Image | `skills/technical-diagram-image` | Dense technical architecture/reference diagram image for software projects. |
| Internet Research | `external/internet-skill` | Deep web research workflow, tracked as a Git submodule. |
| Pro Workflow | `external/pro-workflow` | Battle-tested workflow skills, commands, agents, and context patterns, tracked as a Git submodule. |

## Clone With Submodules

```bash
git clone --recurse-submodules https://github.com/rohitg00/skills.git
```

If already cloned:

```bash
git submodule update --init --recursive
```

## Layout

- Local skills live under `skills/<skill-name>/SKILL.md`.
- Larger standalone skill repos live under `external/` as submodules.
- Keep skill folders portable and avoid agent-specific home-directory config.

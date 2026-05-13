# Mental Models — A Claude Skill

A library of structured analytical frameworks for Claude. Apply one framework when the problem maps cleanly; apply two or three together when the situation is high-stakes or ambiguous.

This skill is a companion to the *Mental Frameworks for the AI Era* series on Medium. New frameworks are added as the articles publish.

## What's included

| Framework | Use for |
|---|---|
| **Premortem** (Klein/Kahneman) | Surfacing how a plan could fail, before it does |
| **WICS** (Sternberg) | Asking what kind of thinking a situation needs |
| **Cynefin** (Snowden) | Sorting a problem into Clear / Complicated / Complex / Chaotic |
| **Double-Loop Learning** (Argyris) | Examining the governing assumptions behind repeated failures |

## Roadmap

Planned for future releases as the companion articles publish:

- Ladder of Inference
- First Principles
- Theory of Constraints

## Installing

> **Note:** Skills are available on paid Claude plans (Pro, Max, Team, Enterprise). Free plans do not currently support custom skill uploads.

### Claude.ai (web or desktop app)

1. Download `mental-models.zip` from the [latest release](../../releases/latest).
2. In Claude, click your profile icon (top right) → **Settings**.
3. Go to **Capabilities** and confirm **Code execution and file creation** is enabled.
4. Go to **Customize → Skills**.
5. Click the **+** button, then **+ Create skill**.
6. Upload `mental-models.zip`.
7. Toggle the skill on if it isn't already.

Start a new conversation and Claude will load the skill automatically when you ask for framework-based analysis.

### Claude Code (terminal)

```bash
git clone https://github.com/fpizzuta/mental-models.git
cp -r mental-models/mental-models ~/.claude/skills/
```

Start a new Claude Code session. Confirm the skill loaded by typing `/skills`.

### Claude API

Reference the skill folder in your API calls. See the [Anthropic Skills documentation](https://docs.claude.com) for current syntax.

## How to use

Ask Claude to apply a framework by name, or describe a decision and let Claude pick:

- *"Premortem this product launch."*
- *"Apply Cynefin and Double-Loop Learning to our onboarding flow."*
- *"I'm deciding whether to migrate to Postgres - pick the right framework and walk me through it."*

When you name two or three frameworks, Claude picks a synthesis pattern (sequential, interleaved, or lens-then-counter-lens) based on the problem shape.

## Repository structure

```
mental-models/                       # repo root
├── README.md                        # you are here
├── LICENSE
├── mental-models/                   # the skill itself (this is what gets packaged)
│   ├── SKILL.md
│   └── references/
│       ├── premortem.md
│       ├── wics.md
│       ├── cynefin.md
│       └── double-loop-learning.md
└── .github/
    └── workflows/
        └── build-skill.yml          # auto-builds .skill on release
```

`SKILL.md` is the thin router. Each framework file in `references/` is self-contained (summary, when to use, when to avoid, the steps, an example, an output template). Claude reads only the framework files needed for a given request, which keeps context cost low even as the library grows.

## Extending

To add a new framework:

1. Create a new file in `mental-models/references/` following the existing pattern.
2. Add a row to the Framework selector table in `mental-models/SKILL.md`.
3. Include the new framework name in the `description` field of `SKILL.md`'s YAML frontmatter.
4. Keep each framework file under ~200 lines.

## Releases

Releases are tagged with semver (v0.1.0, v0.2.0). A GitHub Action builds the `.skill` archive on each release and attaches it as a release asset.

## License

MIT. See `LICENSE`.

## About

Built by [Frank Garofalo](https://www.linkedin.com/in/YOUR-LINKEDIN), Principal Engineer at Inveniam Capital Partners. Part of the *Mental Frameworks for the AI Era* series.

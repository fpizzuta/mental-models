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

### Claude.ai (web or desktop app)

**One-time prerequisite:** Enable code execution. Go to **[Settings → Capabilities](https://claude.ai/settings/capabilities)** and turn on **Code execution and file creation**. Skills won't work without this.

**Install the skill:**

1. Download `mental-models.zip` from the [latest release](../../releases/latest).
2. Go to **[Customize → Skills](https://claude.ai/customize/skills)**.
3. Click the **+** button, then **+ Create skill**.
4. Select **Upload a skill**.
5. Upload `mental-models.zip`.
6. Toggle the skill on if it isn't already.

Start a new conversation and Claude will load the skill automatically when you ask for framework-based analysis.

> Skills are available on Free, Pro, Max, Team, and Enterprise plans. Team and Enterprise users may need an owner to enable Skills at the organization level first.

### Claude Code (terminal)

```bash
git clone https://github.com/fpizzuta/mental-models.git
cp -r mental-models/mental-models ~/.claude/skills/
```

Start a new Claude Code session. Confirm the skill loaded by typing `/skills`.

### Claude API

Reference the skill folder in your API calls. See the [Anthropic Skills documentation](https://docs.claude.com) for current syntax.

### Other AI coding tools

This skill uses the [Agent Skills open standard](https://agentskills.io), so it works in any agent that supports the `SKILL.md` format. That currently includes Cursor, OpenAI Codex CLI, Gemini CLI, and GitHub Copilot. The install pattern is the same idea on each: clone the repo and copy the `mental-models/` folder into the tool's skills directory.

```bash
git clone https://github.com/fpizzuta/mental-models.git
```

Then place the `mental-models/` folder where your agent expects skills to live. Check your tool's documentation for the exact path - it varies between tools but the skill content is identical.

### ChatGPT and Gemini (consumer apps)

The consumer products from OpenAI (ChatGPT) and Google (Gemini) use proprietary formats (Custom GPTs and Gems) rather than the Agent Skills standard. They are not currently supported by direct install. A companion Custom GPT and Gem may be released separately - see the repo issues for status.

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

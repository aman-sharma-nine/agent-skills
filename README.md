# Agent Skills

A small, curated library of reusable skills for AI coding and assistant agents
(Hermes, Codex, Claude Code, and others).

Each skill is a self-contained `SKILL.md` describing a repeatable workflow.
Skills are written to be portable: the core workflow lives in one place, and
per-agent packaging or metadata lives under `adapters/`.

## What is a skill?

A skill is a short, focused instruction file that tells an agent how to do a
recurring task well — the procedure, the decision rules, the pitfalls, and how
to verify the work. Unlike a knowledge base, a skill describes behaviour, not
facts.

## Structure

```
skills/
  learning-and-thinking-partner/   # Adaptive teaching and reasoning support
  watercolour-blog-art/            # Coordinated editorial illustrations
  vague-topic-to-article-outline/  # Vague topic -> researchable outline
  hermes-remote-mcp-setup/         # Install remote OAuth MCP servers in Hermes
adapters/
  codex/                           # Codex-specific skill packaging
catalog.yaml                       # Machine-readable index of skills
```

## Using a skill

Copy the skill's `SKILL.md` into your agent's skills directory, or follow the
agent's own skill-installation workflow. Each agent resolves skills from its own
location:

- Hermes: `~/.hermes/skills/<category>/<name>/SKILL.md`
- Codex: `~/.codex/skills/<name>/SKILL.md`
- Claude Code: `~/.claude/skills/<name>/SKILL.md`

Then invoke it naturally — for example:

> Help me learn a new topic using the learning-and-thinking-partner skill.

## Adding a new skill

1. Create `skills/<name>/SKILL.md`.
2. Keep the workflow portable — no personal names, absolute paths, or secrets.
3. Put agent-specific packaging under `adapters/<agent>/`.
4. Register the skill in `catalog.yaml`.

## Contributing

These skills are MIT-licensed. Contributions, issues, and pull requests are
welcome.

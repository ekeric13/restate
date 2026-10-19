# Restate Skill

A small skill built around this prompt:

> Restate in your own words what you think my goals are and what the problem I'm trying to solve is.

It returns a concise restatement grounded in the conversation, without proposing solutions or executing the task. The skill is in [`restate/`](./restate/SKILL.md).

## Explicit Invocation Only

Codex uses `policy.allow_implicit_invocation: false` in `agents/openai.yaml`. Claude Code uses `disable-model-invocation: true` in the skill frontmatter. Both settings disable automatic invocation in their respective harnesses. Other harnesses must support an equivalent policy to enforce this behavior.

## Install With skills.sh

```bash
npx skills@latest add ekeric13/restate
```

## Install For Codex

From a local clone:

```bash
mkdir -p ~/.codex/skills/restate
rsync -a restate/ ~/.codex/skills/restate/
```

Start a new session and invoke `$restate`.

## Install For Claude Code As A Plugin

```text
/plugin marketplace add https://github.com/ekeric13/restate
/plugin install restate@restate
```

Invoke `/restate:restate`.

## Install For Claude Code As A Personal Skill

```bash
mkdir -p ~/.claude/skills/restate
rsync -a restate/ ~/.claude/skills/restate/
```

Then invoke `/restate`.

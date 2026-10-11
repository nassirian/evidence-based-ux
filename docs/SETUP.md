# Set up Evidence-Based UX

Evidence-Based UX gives Claude 252 rules for designing and reviewing interfaces, drawn from 86 HCI papers and WCAG 2.2. Each rule cites its sources, carries an evidence grade and states its limits.

## Claude: upload the skill

1. Open **Customize → Skills → + → Create skill → Upload a skill**.
2. Upload `evidence-based-ux.zip` from the [latest release](../../../releases/latest), or zip the `skills/evidence-based-ux` folder yourself so the archive holds a single `evidence-based-ux/` folder.
3. Enable the skill and ask: "Use evidence-based-ux to review this checkout screen."

Skills require **Code execution and file creation** to be on, and organization settings may control availability. See [Claude's setup guide](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

## Claude Code

```bash
git clone https://github.com/nassirian/evidence-based-ux.git
cp -r evidence-based-ux/skills/evidence-based-ux ~/.claude/skills/
```

For a single project, copy the folder into that project's `.claude/skills/` instead.

## ChatGPT desktop and Codex: native skill

The `skills/evidence-based-ux` folder is a standard skill package, with optional OpenAI display metadata in `agents/openai.yaml`. Where standalone skills are available, pick it from the skill picker: `@` in ChatGPT, `$evidence-based-ux` in Codex.

## Check the behavior

Give it a screenshot or the code of a sign-up form with a small submit button, a red-only error state and a pre-checked marketing checkbox. The review should flag all three, cite rule IDs (for example `PT-2`, `TX-3`, `ET-2`), give each an evidence grade, and propose one concrete fix per finding. It should also say what a single static screen can't show, such as loading and error flows.

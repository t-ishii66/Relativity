# AGENT.md

## Project Overview

This repository contains “Making Sense of Relativity,” a bilingual,
reader-friendly introduction to special and general relativity.

The project is primarily a documentation and publishing project rather than a
software application. The content is published through GitHub Pages using
Jekyll, the Cayman theme, kramdown, and MathJax.

The intended readers range from interested beginners to readers who can follow
the equations of relativity but want a clearer physical interpretation.

## Repository Structure

- `README.md`
  - English GitHub Pages landing page.
  - Contains English metadata, navigation, and a summary of the project.
- `README-jp.md`
  - Japanese landing page.
  - Contains Japanese metadata, navigation, and a summary of the project.
- `docs/en/Relativity.md`
  - Main English manuscript.
- `docs/jp/Relativity.md`
  - Main Japanese manuscript.
- `docs/jp/LorentzInvariantIntroduction.md`
  - Beginner-level Japanese introduction to Lorentz transformations and the
    invariant spacetime interval.
- `images/`
  - Illustrations, diagrams, character images, and comics used by the
    manuscripts and landing pages.
- `_config.yml`
  - GitHub Pages and Jekyll configuration.
- `_includes/head-custom.html`
  - MathJax configuration loaded by the published site.
- `graphic.key`
  - Source presentation containing graphics used by the project.
- `Questions.md` and `PROBLEMS.md`
  - Local notes or working material; they are not part of the published site.

## Writing Principles

- Prefer clear physical interpretation over formal abstraction.
- Introduce new concepts before using their technical terminology.
- State what is being measured, who measures it, and in which coordinate
  system.
- Distinguish an event itself from the coordinates assigned to that event.
- Distinguish coordinate-dependent quantities from invariant or proper
  quantities.
- Explain equations in prose instead of presenting unexplained formulas.
- Preserve the conversational and thought-experiment style used by Alice,
  Bob, and Charlie where it helps understanding.
- Avoid assuming familiarity with tensors, differential geometry, or advanced
  calculus unless the section explicitly introduces them.
- Do not sacrifice physical correctness for simplicity. State the scope and
  assumptions of a simplified explanation.

## Mathematical Conventions

- The main manuscripts generally reduce space to one dimension when explaining
  special relativity.
- Use $c$ for the speed of light and $V$ for the relative velocity between
  inertial frames.
- Use SA and SB for the inertial frames associated with Alice and Bob when
  following the existing manuscript.
- Use subscripts such as $t_A$, $x_A$, $t_B$, and $x_B$ to identify the
  coordinate system.
- The manuscript defines

$$
w=ct
$$

  so that the time coordinate has units of length.
- Follow the existing metric-signature convention:

$$
ds^{2}=-dw^{2}+dx^{2}
$$

  or equivalently

$$
ds^{2}=-c^{2}dt^{2}+dx^{2}.
$$
- If the opposite signature is mentioned, explicitly state that it is an
  alternative convention and do not mix the two conventions in one
  derivation.
- Use `\Delta` for finite coordinate differences and `d` for infinitesimal
  quantities. Do not call a finite interval a line element without explaining
  the limiting step.
- Display equations with `$$` delimiters and inline mathematics with `$`
  delimiters so that they render through the configured MathJax setup.

## Bilingual Content

- Treat the Japanese and English manuscripts as parallel editions, but do not
  assume that every edit must be translated automatically.
- When a requested change affects both editions, preserve the meaning,
  notation, heading structure, figure references, and pedagogical progression
  across both languages.
- Write natural prose in each language rather than translating word for word.
- If only one edition is changed, report that the other edition remains
  unchanged.
- Keep the language links in `README.md` and `README-jp.md` working.

## User-Wide Claude Code Guidance

- Treat `~/.claude/CLAUDE.md` as user-wide instructions for this project.
- Before starting a task, check whether a relevant skill or agent definition
  exists under `~/.claude/skills/` or `~/.claude/agents/`.
- When a task matches one of these definitions, read the applicable
  `SKILL.md` or agent file completely and follow its workflow and conventions.
- If a Claude Code-specific command or agent cannot be invoked directly, use
  its definition as operating guidance and adapt the procedure to the
  available tools without claiming that the Claude Code component was run.
- Follow the scope explicitly requested by the user. For example, when the
  user requests a commit without a push, use the applicable commit workflow
  but omit the push step.
- Higher-priority runtime instructions and explicit user instructions take
  precedence if they conflict with the user-wide Claude Code guidance.

## Links and Images

- From a root-level Markdown file, reference an image as `images/name.png` or
  `./images/name.png`.
- From a manuscript under `docs/en/` or `docs/jp/`, reference an image as
  `../../images/name.png`.
- Use descriptive alternative text for prominent images.
- Before renaming or deleting an image, search the entire repository for all
  references to it.
- Do not modify binary image or Keynote assets unless the task explicitly
  requires it.

## GitHub Pages and Metadata

- Preserve valid YAML front matter in `README.md` and `README-jp.md`.
- Keep `_config.yml` consistent with the repository URL and GitHub Pages
  base path.
- Do not remove the MathJax include or change its delimiter configuration
  without checking every manuscript.
- Keep private notes and scratch files excluded from the generated site.
- Update `Last updated` only when the requested change warrants changing the
  public landing-page date.

## Validation

After editing Markdown or configuration:

1. Run `git diff --check`.
2. Inspect the complete diff for unintended changes.
3. Check that relative Markdown links and referenced image files exist.
4. Check that every display equation has matching `$$` delimiters.
5. If a working Jekyll environment is available, run:

   ```bash
   bundle exec jekyll build
   ```

6. If Jekyll dependencies are not installed, do not add them merely to perform
   validation; report that the local site build was not run.

## Change Discipline

- Preserve unrelated working-tree changes.
- Do not rewrite either full manuscript for a narrowly scoped correction.
- Keep edits focused and reviewable.
- Do not edit generated Jekyll output such as `_site/`.
- Do not commit, push, publish, or alter external services unless explicitly
  requested.

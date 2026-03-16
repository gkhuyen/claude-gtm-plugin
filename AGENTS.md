# Claude Instructions — GTM Plugin Development

This is the GTM Skills plugin repo. These guidelines are for AI assistants working on skills, commands, and plugin code in this repository.

## Repo Structure

```
gtm-plugin/
├── .claude-plugin/              # Root plugin manifest
│   ├── plugin.json
│   └── marketplace.json
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.yml       # YAML form template for skill bug reports
│       └── config.yml           # Issue template chooser config
├── AGENTS.md                    # This file — dev guidelines (CLAUDE.md symlinks here)
├── ALL_SKILLS.md                # Auto-generated skill listing
├── skills/                      # Core skills (root-level, ships with every install)
│   └── issue-reporting/
│       └── SKILL.md
├── plugins/
│   ├── seo/                     # Each domain is a sub-plugin
│   ├── content/
│   ├── social/
│   ├── outbound/
│   ├── sales/
│   ├── growth/
│   ├── analytics/
│   ├── strategy/
│   ├── ads/
│   └── crm/
├── scripts/                     # Build and validation scripts
│   ├── bump-version.sh          # Bump semver across all manifests
│   └── generate-skills-readme.sh # Regenerate ALL_SKILLS.md + README skills section
└── validate-skills.sh           # Skill spec validator
```

Each sub-plugin follows this layout:

```
plugins/<domain>/
├── .claude-plugin/
│   └── plugin.json              # Sub-plugin manifest with version
├── commands/
│   └── bootstrap.md             # /bootstrap onboarding command
└── skills/
    └── <skill-name>/
        ├── SKILL.md             # Skill definition (YAML frontmatter + markdown)
        ├── references/          # Supporting reference material
        ├── assets/              # Templates, examples
        └── rules/               # (optional) Organized guidelines
```

## User Project Structure (the `/bootstrap` convention)

When bootstrap runs in a user's project, it creates this structure. **All skills and commands must reference these paths consistently.**

```
user-project/
├── CLAUDE.md                    # AI instructions: repo structure, naming, workflow, routing
├── about/
│   └── me.md                    # Personal voice, writing style, personality, biography
├── strategy/
│   └── brand.md                 # Brand positioning, messaging, audience, competitors, voice
├── content/
│   ├── ideas.md                 # Content idea backlog with status
│   ├── calendar.md              # Publishing schedule
│   ├── <platform>/
│   │   ├── drafts/              # Work-in-progress content
│   │   └── published/           # Archive of published content
│   └── ...                      # linkedin/, twitter/, reddit/, blog/, email/
└── assets/
    ├── logos/                   # Logo files
    └── brand/                   # Brand visual references
```

### What each folder is for

| Path | Purpose | Who writes to it |
|---|---|---|
| `CLAUDE.md` | AI instructions — repo structure, what to read first, naming, workflow | Bootstrap creates it; rarely updated |
| `about/` | Personal and team context | User provides; skills read before voice-matched content |
| `strategy/` | Brand foundation — positioning, messaging, voice, audience, competitors | Bootstrap creates; updated when brand evolves |
| `content/` | Day-to-day content engine — ideas, planning, drafts, published | Skills create drafts; user publishes |
| `assets/` | Reusable visual assets — logos, brand files | User provides |

### Content naming convention

All content files (drafts and published) use:

```
YYYY-MM-DD_short-topic-slug.md
```

### Content lifecycle

1. **Idea** → add a line to `content/ideas.md`
2. **Draft** → create file in `content/<platform>/drafts/`
3. **Publish** → move file from `drafts/` to `published/`
4. **Repurpose** → new draft in target platform's `drafts/`, referencing original

## Writing Skills — Conventions

### Reading user context

When a skill needs brand or personal context, use these paths. Check if they exist before reading:

```
# Brand context (strategy, positioning, voice)
strategy/brand.md

# Personal voice context
about/me.md

# Alternate legacy paths (check as fallback)
.claude/product-marketing-context.md
.agents/product-marketing-context.md
```

**Pattern for skills:**
```markdown
Check for `strategy/brand.md` first. If it exists, read it before asking questions.
Use that context and only ask for information not already covered.
```

### Generating content

Skills that produce draft content must:

1. Save to `content/<platform>/drafts/` (not root, not `artifacts/`)
2. Use the `YYYY-MM-DD_short-topic-slug.md` naming convention
3. Never write generated content into `strategy/`, `about/`, or `CLAUDE.md`

### Routing new learnings

When a skill discovers new information during execution:

- Brand shifts, new messaging, audience insights → `strategy/brand.md`
- Writing preferences, voice discoveries → `about/me.md`
- New content ideas → `content/ideas.md`

### Referencing internal skill files

Skills can bundle their own reference material in `references/`, `assets/`, or `rules/` subdirectories. Reference them with relative paths:

```markdown
See [references/templates.md](references/templates.md) for examples.
```

## Writing Commands — Conventions

### Bootstrap commands

Each sub-plugin has its own `commands/bootstrap.md`. All bootstrap commands must:

1. Generate the same unified folder structure (see above)
2. Create `CLAUDE.md`, `about/me.md`, `strategy/brand.md` as foundational files
3. Create all content platform folders with `.gitkeep` in empty leaf directories
4. Use the same interview stages (orientation → identity → brand → voice → person → channels → success)
5. **Not** create `BRAND.md`, `SOUL.md`, or `MEMORY.md` (these are deprecated)

### Deprecated patterns (do not use)

| Old | New | Notes |
|---|---|---|
| `BRAND.md` | `strategy/brand.md` | Brand context lives in strategy folder |
| `SOUL.md` | `about/me.md` | Personal voice lives in about folder |
| `MEMORY.md` | _(removed)_ | No longer used |
| `artifacts/` | `content/<platform>/drafts/` | Content organized by platform |
| `.agents/product-marketing-context.md` | `strategy/brand.md` | Unified in strategy |
| `.claude/product-marketing-context.md` | `strategy/brand.md` | Unified in strategy |

## Versioning

- Root plugin version: `.claude-plugin/plugin.json`
- Sub-plugin versions: `plugins/<domain>/.claude-plugin/plugin.json`
- Bump both when making changes that affect a sub-plugin
- Use semver: patch for fixes, minor for new features/structure changes, major for breaking changes

## Validation

Run before committing:

```bash
./validate-skills.sh
```

Checks frontmatter fields, naming conventions, description quality, and file structure against the [Agent Skills spec](https://agentskills.io/specification).

The validator scans `plugins/` by default. To validate root-level core skills separately:

```bash
./validate-skills.sh skills
```

## Rollout Flow

Follow this sequence when shipping changes. **Every step must pass before proceeding to the next.**

### 1. Validate skills

```bash
./validate-skills.sh
./validate-skills.sh skills   # if core skills were changed
```

Both must exit clean (warnings are OK, errors are not).

### 2. Regenerate skill listings

If skills were added, removed, or renamed:

```bash
./scripts/generate-skills-readme.sh
```

This updates `ALL_SKILLS.md` and the Skills section in `README.md`.

### 3. Bump version

Use semver — patch for fixes, minor for new skills/features, major for breaking changes:

```bash
./scripts/bump-version.sh patch   # 1.3.0 → 1.3.1
./scripts/bump-version.sh minor   # 1.3.0 → 1.4.0
./scripts/bump-version.sh major   # 1.3.0 → 2.0.0
./scripts/bump-version.sh 2.1.0   # explicit version
```

This updates `.claude-plugin/plugin.json` (root) and all `plugins/*/.claude-plugin/plugin.json` (sub-plugins) in one pass.

### 4. Commit and push

```bash
git add -A
git commit -m "description of changes"
git push
```

### Quick reference

```bash
# Full rollout — validate, regenerate, bump, commit, push
./validate-skills.sh && \
./validate-skills.sh skills && \
./scripts/generate-skills-readme.sh && \
./scripts/bump-version.sh minor && \
git add -A && \
git commit -m "add new skills" && \
git push
```

## Issue Templates

Bug reports use a YAML form template at `.github/ISSUE_TEMPLATE/bug_report.yml`. The template covers:

- **Skill name** — which skill misbehaved
- **Bug type** — wrong advice, not activating, missing context, crash, etc.
- **Prompt used** — what the user asked Claude
- **Actual vs expected** — what happened vs. what should have happened
- **Context files present** — whether `strategy/brand.md`, `about/me.md`, `CLAUDE.md` existed (most common cause of "wrong advice" is missing context)
- **Regression flag** — whether it worked in a previous version
- **Plugin version and install method** — for reproduction
- **Impact severity** — Critical / High / Medium / Low

When updating the template, keep the `context_files` checklist in sync with the actual paths skills read from.

## Core Skills

Core skills live in `skills/` at the repo root (not inside `plugins/`). They ship with every install regardless of which domain sub-plugins are selected.

Current core skills:

| Skill | Purpose |
|---|---|
| `issue-reporting` | Guides users through reporting skill bugs with proper detail |

Core skills follow the same SKILL.md format as domain skills (YAML frontmatter + markdown body). They are validated with `./validate-skills.sh skills`.

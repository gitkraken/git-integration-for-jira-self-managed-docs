# Git Integration for Jira Data Center: product notes for the docs-authoring skill

This folder is **local to this docs repo**. The shared skill files (SKILL.md,
references/, scripts/) are owned by GK-WP-HC-Design and replaced on every
distribution; `product/` never is. Edit it here.

| | |
| --- | --- |
| Content folder | `git-integration-for-jira-self-managed/` (images in `_images/`) |
| WordPress category | `git-integration-for-jira-data-center`: pages publish at `/git-integration-for-jira-data-center/<slug>/` |
| Home page | `git-integration-for-jira-home-self-manged` (`page_type: main-index`) |
| Nav file | `GK-WP-HC-Plugin/config/products/gijdc.json` in GK-WP-HC-Design: label-only groups and links |
| Nav depth | up to 5 levels |
| Right-hand TOC | H3 and H4 |
| Unlabelled code panels | "Code" |

`config.json` beside this file holds the same facts in the form
`scripts/check_pages.py` and GK-WP-HC-Design's `preview/` read.

## Metadata (FRONTMATTER-SCHEMA.md)

Every page carries the Core fields (`references/metadata.md`).
Conditional fields required here: `git_hosts`, `deployment`, `role_required`, `version_required`.
Allowed where they apply: `og_image`.
Constants: `product: Git Integration for Jira Data Center`, `deployment: Jira Data Center`.
`plan_required` values: `all`, `Standard`, `Advanced`.

## Decisions for this help center

The settled design decisions are in GK-WP-HC-Design
`redesign-expansion/PER-PRODUCT-DECISIONS.md`, section "Git Integration for Jira Data Center". Record
conventions that only apply here (naming, recurring page shapes, words to use)
below this line.

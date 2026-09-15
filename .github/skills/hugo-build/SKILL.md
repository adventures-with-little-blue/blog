---
name: hugo-build
description: Build and validate the motoblog Hugo site after content, layout, configuration, or i18n changes. Use when checking Hugo rendering, build errors, generated output, or deployment readiness.
---

# Hugo Build

Use this skill when validating changes to the Hugo site.

## Build procedure

- Use the repository's canonical command:

  ```powershell
  hugo build --cleanDestinationDir --minify
  ```

- Run the smallest relevant validation after a change. Use the canonical build for changes to Hugo content, layouts, configuration, i18n, assets, or the theme integration.
- Treat Hugo warnings and errors as actionable. Identify the affected source files instead of modifying generated output.

## Generated-file boundaries

- The build writes output below `public/` and may update generated resources.
- Never edit files below `public/`, `resources/_gen/`, or `static/_gen/` by hand, even though `public/` is used by the current deployment workflow.
- Do not include generated-file changes in a content or configuration change unless the user explicitly asks for generated output to be updated.

## Project conventions

- Read `hugo.yaml` before changing language configuration or content-directory behavior.
- Swedish (`content/sv`) is the source language; Finnish (`content/fi`) and English (`content/en`) are translations.
- Prefer site-level layouts and configuration over changes below `themes/ananke/`.

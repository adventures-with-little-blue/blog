# Copilot Instructions for motoblog

This repository is a multilingual Hugo site with a simple structure.

## Project rules

- Treat Swedish (`content/sv`) as the source language.
- Treat Finnish (`content/fi`) and English (`content/en`) as translations of the Swedish source unless the user explicitly asks to write original content.
- Before creating or updating a translation, compare it with its Swedish source and its existing target-language counterpart when present.
- Follow the site configuration in `hugo.yaml`, especially the language setup and Hugo content directories.
- Prefer minimal, local changes. Do not refactor layouts, theme files, or generated output unless the task requires it.
- Do not edit generated files under `public/`, `resources/_gen/`, or `static/_gen/`, including when `public/` is used for deployment.
- Prefer editing site-level files over bundled theme files in `themes/ananke/` unless the task is specifically about the theme.
- The canonical build command is `hugo build --cleanDestinationDir --minify`.

## Hugo content rules

- Preserve Hugo front matter keys, structure, dates, slugs, draft state, tags, and params unless the user asks to change them.
- Preserve Markdown structure, headings, lists, shortcode syntax, image paths, and internal links.
- Keep language-specific content in the matching language directory.
- Reuse existing i18n keys and file patterns before introducing new ones.

## Language review workflow

- For a language review, identify and apply all intended local corrections in one edit before validating.
- Run the Hugo build once after the complete set of language-review corrections has been applied; do not run a build between individual proofreading edits unless the user requests incremental validation.

## Translation rules

- Translate title, description/summary when present, headings, body text, alt text, and captions; preserve dates, slugs, params, and image filenames.
- Translate tags to existing target-language tags if they exist, otherwise keep the original tag.
- Translated posts should keep the same relative image references and should not duplicate bundle images unless the user explicitly asks.
- Do not invent facts, locations, names, URLs, or historical details.
- Keep proper nouns in their original form unless there is a standard target-language form.
- Keep numbers, dates, route data, product names, motorcycle model names, and technical part names unchanged unless the translation is obvious and standard.
- My motorcycle's name is "Lilla Blue" in Swedish and should be translated to "Pikku-Blue" in Finnish and "Little Blue" in English.
- Preserve tone and level of detail from the Swedish source.

## Linked resource rules

- When a Swedish post links to an external resource with known language variants, prefer the correct target-language version for the translated post.
- For `luontoon.fi` links, use the matching language version in translations: Swedish `/sv/destinationer/`, Finnish `/fi/kohteet/`, and English `/en/destinations/`. Verify the target-language page and its language-specific slug; do not construct a slug by direct translation.
- For every Wikipedia link in a translation, actively check the source article's language links for a matching target-language article before retaining a source-language URL. Use that linked article's exact URL and title; do not infer a URL from a translated title or slug. For example, `sv.wikipedia.org/wiki/Haukkavuori_utsiktstorn` links to `fi.wikipedia.org/wiki/Haukkavuoren_n%C3%A4k%C3%B6torni`.
- If no reliable target-language variant can be identified, keep the original URL instead of guessing. Then add "(sv)" after the link text to indicate it's in Swedish.
- Do not create or rewrite external URLs based on loose similarity.

## Style guidance for Copilot outputs

- Keep edits small and easy to review.
- Match the existing writing and formatting style of the repository.
- Prefer concrete content over generic filler.
- When generating translated posts, output valid Hugo Markdown that can be saved directly into the matching language directory.
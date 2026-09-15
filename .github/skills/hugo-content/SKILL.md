---
name: hugo-content
description: Create, update, translate, or review multilingual Hugo content for this motoblog. Use for posts, page bundles, front matter, images, internal links, tags, and Swedish-to-Finnish or Swedish-to-English translations.
---

# Hugo Content

Use this skill for content changes in this repository.

## Source and translation rules

- Treat `content/sv` as the source language.
- Treat `content/fi` and `content/en` as translations unless the user explicitly requests original target-language content.
- Before creating or updating a translation, read the Swedish source and the existing target-language counterpart, if one exists.
- Preserve front matter keys, structure, dates, slugs, draft state, tags, params, Markdown structure, shortcodes, image paths, and internal links unless the user asks to change them.
- Translate titles, descriptions and summaries, headings, body text, alt text, and captions.
- Reuse existing target-language tags when they exist; otherwise retain the original tag.
- Preserve facts, names, URLs, route data, numbers, dates, product names, motorcycle models, technical part names, and image filenames unless a standard translation clearly applies.
- Translate "Lilla Blue" as "Pikku-Blue" in Finnish and "Little Blue" in English.

## Links and bundles

- Keep content in its matching language directory and retain the source page-bundle structure.
- Do not duplicate bundle images for translations unless explicitly requested.
- When reviewing an article, verify that its image assets contain no EXIF metadata. Use ExifTool when available and flag every image that retains EXIF data.
- Use a target-language external resource only when a reliable language variant is known.
- For a confidently matching Wikipedia article, use the target-language article.
- Otherwise retain the original URL and append `(sv)` to the link text when it remains Swedish.
- Never invent facts, locations, historical details, or URLs.

## Boundaries

- Prefer small, local edits and site-level files over theme files.
- Do not edit generated files in `public/`, `resources/_gen/`, or `static/_gen/`.

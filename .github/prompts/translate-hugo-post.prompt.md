---
agent: ask
model: GPT-5
tools: ["codebase", "editFiles"]
description: Translate a Swedish Hugo post to Finnish or English while preserving Hugo structure and localizing safe external links.
---

# Translate Hugo Post

Translate a Hugo post from Swedish to either Finnish or English.

## Inputs to collect

If the user does not provide these, ask for the missing ones before producing the translation:

1. Target language: `fi` or `en`
2. Source file path or source markdown
3. Whether to create a new translated file or only return the translated text

## Rules

- Swedish is the source language.
- Preserve Hugo front matter keys and structure.
- Preserve Markdown formatting, headings, lists, shortcodes, image paths, and internal Hugo links.
- Translate title, summary, captions, alt text, and body text.
- Tags have language version, translate them to existing target-language tags if they exist, otherwise keep the original tag.
- In the English translation, translate place names to Finnish if the city in question has a majority Finnish-speaking population, otherwise keep the Swedish names.
- In the Finnish translation, translate place names to Finnish if they have a well-established Finnish form, otherwise keep the Swedish names.
- Keep dates, coordinates, route information, product names, and technical terms unchanged unless there is a clear standard translation.
- Keep proper nouns unless there is a well-established target-language form.
- Do not add facts, explanations, or commentary that are not present in the source.

## Link localization

- If the source contains external links with language-specific versions, use the matching target-language version when it can be identified confidently.
- For Wikipedia, replace a Swedish article link with the corresponding Finnish or English article if it clearly exists.
- If a target-language page cannot be identified confidently, keep the original URL.
- Never fabricate or guess a localized link.

## Output

- Output only the finished translated Hugo Markdown unless the user explicitly asks for notes.
- If a link could not be localized confidently and the user asked for notes, add a short note after the translation listing the unchanged links.
- If asked to create the file, place the translation in the matching language directory and preserve the page bundle structure.
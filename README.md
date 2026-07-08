# articles

Template: `example.mdx`

## Localization

- `posts/*.mdx` — English (default / fallback)
- `posts/zh-TW/*.mdx` — Traditional Chinese translations
- `posts/ja/*.mdx` — Japanese translations

A translation must keep the **same `id`** in its frontmatter as the English
original — the site matches translations to the original by `id` and falls back
to English when a translation is missing. Translate `title` and `description`;
keep `date`, `tags`, and image paths (`./img/...`) unchanged.

Support:

- heading h1 to h6
- list
- table
- code block
- inline code
- iframe tag copied from youtube

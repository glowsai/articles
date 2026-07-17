# Publishing workflow

## Required blog translations

When creating or materially revising a blog post, complete the English edition first, then create matching Traditional Chinese and Japanese editions before handoff.

- Store the three editions under `posts/blog/en/`, `posts/blog/zh-tw/`, and `posts/blog/ja/` using the same numbered filename.
- Keep `date` and `lastUpdated` synchronized across the three frontmatter blocks.
- Use locale-specific IDs ending in `_en`, `_zh_tw`, and `_ja`.
- Translate the title, meta description, H1/H2 headings, CTA, FAQ, and related-guide section for the local reader; do not leave an English placeholder.
- Preserve code blocks, commands, model names, prices, dates, and source URLs unless a localized equivalent is verified.
- Update internal links to a localized article where that edition exists; otherwise retain the working source-language link.
- Before handoff, verify that every published blog topic has all three editions and that their metadata and core section structure match.

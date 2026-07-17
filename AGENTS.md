# Publishing workflow

## Required blog translations

When creating or materially revising a blog post, complete the English edition first, then create matching Traditional Chinese and Japanese editions before handoff.

- Store the three editions under `posts/blog/en/`, `posts/blog/zh-TW/`, and `posts/blog/ja/` using the same numbered filename.
- Keep `date` and `lastUpdated` synchronized across the three frontmatter blocks.
- Use locale-specific IDs ending in `_en`, `_zh_tw`, and `_ja`.
- Translate the title, meta description, H1/H2 headings, CTA, FAQ, and related-guide section for the local reader; do not leave an English placeholder.
- Preserve code blocks, commands, model names, prices, dates, and source URLs unless a localized equivalent is verified.
- Update internal links to a localized article where that edition exists; otherwise retain the working source-language link.
- Before handoff, verify that every published blog topic has all three editions and that their metadata and core section structure match.

## Merge-conflict prevention

### Root cause: PR #31

PR #31 conflicted with `main` for two related reasons:

- The branch changed the same frontmatter `date` fields across existing English, Traditional Chinese, and Japanese posts while also adding `lastUpdated`; `main` changed those same `date` lines. Git could not choose between the competing metadata values, so the conflict repeated across every affected post.
- `main` renamed the Traditional Chinese locale directory from `posts/blog/zh-tw/` to `posts/blog/zh-TW/`, while the branch added translations under the old path. Git therefore needed a decision about the destination of those new files.

### Required branch sync before a PR

- Treat `posts/blog/zh-TW/` as the canonical Traditional Chinese directory; never add or recreate files under `posts/blog/zh-tw/`.
- Before opening or updating a PR, fetch and integrate the latest `main`, then resolve conflicts in the branch rather than leaving them for the PR merge.
- If a change updates shared frontmatter across existing posts, sync with `main` immediately before opening the PR and confirm the intended `date` and `lastUpdated` values for all three editions.
- When `main` moves or renames a locale directory, move branch files to the destination used by `main` before pushing.
- Before handoff, run `git diff --check`, confirm there are no conflict markers, and repeat the three-edition metadata and structure checks above.

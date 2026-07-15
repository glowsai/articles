# Distribution Pack Spec

Every blog post in `articles/posts/blog/en/` gets a folder here:
`articles/distribution/<NN>-<slug>/` (slug = filename without number prefix and `.mdx`).

Reference example (match its structure, headers, and tone exactly):
`articles/distribution/28-cheap-gpu-cloud-real-cost/`

Each folder contains 5 files:

## 1. `x-thread.md`
- Header block: `# X Thread — <Post Title>`, source path, link.
- 8–12 numbered tweets (`**1/**` style). Each tweet ≤ 280 chars.
- Tweet 1 = a hook with a concrete number or contrarian claim from the post. No "🧵 a thread on…" filler openers beyond one thread emoji.
- Middle tweets: the post's actual data, scenarios, and lists — specifics, not vibes.
- Last tweet: link to the post. If the post is Glows.ai-favoring (comparison pages), add a transparent one-liner acknowledging the bias (see the #28 example).

## 2. `linkedin.md`
- Header block: `# LinkedIn Post — <Post Title>`, source, link, one-line angle.
- Business/TCO/decision-maker framing. 150–250 words. Uses 2–3 concrete numbers from the post. 📊 bullets welcome, no engagement-bait. Ends with the link + 3–4 hashtags.

## 3. `threads.md`
- Header block: `# Threads Post — <Post Title>`, source, note on voice.
- Casual, build-in-public, lowercase-friendly, deliberately not "scheduled-feeling". ≤ 500 chars. One link. Optionally one short follow-up reply (poll or question).

## 4. `facebook-zh-tw.md`
- Header block in zh-TW: `# Facebook 貼文（zh-TW）— <中文標題>`, 來源, 定位.
- Repurpose from the zh-TW version of the same post: `articles/posts/blog/zh-tw/<same filename>`. Use ITS title and ITS frontmatter `id` for the link. Traditional Chinese, friendly/educational tone for TW AI Facebook groups, emoji bullets (🔹/1️⃣), ends with zh-TW article link + zh/en hashtags.

## 5. `reddit-notes.md`
- NOT a post. Manual-sharing notes per the 90/10 rule (see `glows-ai-gtm-phase-0/docs/content-strategy/content-funnel-automation.md`).
- Sections: relevant subreddits + the question patterns this post answers; a reply skeleton (helpful answer first, link as citation, "adapt, never paste verbatim"); the disclosure warning.
- For "X vs Glows.ai" comparison posts: note that vendor-comparison content is extra-high-risk on Reddit — only cite it when someone explicitly asks for provider comparisons, and disclose affiliation.

## Links
Article URL = `https://glows.ai/article/<frontmatter id>` (read `id:` from each post's frontmatter; en id for X/LinkedIn/Threads/Reddit, zh-tw id for Facebook).

## Differentiation rule for the comparison pages (12, 21–27, 29–32)
Do NOT reuse the same hook shape across them. Each pack must lead with that post's unique numbers or its competitor's specific weakness/strength (e.g. Vast.ai = marketplace variance, Lambda = availability, Nebius = enterprise scale, DeepInfra = serverless-only). Honest about when the competitor wins — same as the posts themselves.

## General
- Pull numbers, prices, and claims ONLY from the source post. Never invent stats.
- No AI-slop phrasing ("game-changer", "in today's fast-paced world", "let's dive in").
- Files are drafts for human review — do not publish anywhere.

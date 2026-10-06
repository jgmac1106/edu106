# Agent instructions for the optional IndieWeb starter

EDU106's primary student publishing workflow is **ChatGPT Sites**. Do not present GitHub, GitHub Pages, repository forking, or Codex as required steps for current students. Direct students to the current syllabus and class-site publishing guidance; see [README.md](README.md) for this repository's role.

This repository preserves the optional / legacy static IndieWeb starter for students with no prior coding experience. The instructions below apply only when maintaining this repository or helping someone who has chosen to use this starter.

## Protect the learning design

- Keep the site static and lightweight.
- Use only plain HTML and CSS unless the student explicitly asks for something that truly requires JavaScript.
- Do not introduce React, Vue, Astro, Jekyll, npm, package managers, build tools, databases, or external frameworks.
- Prefer small changes that a beginning student can inspect and explain.
- Use accessible semantic HTML.
- Keep navigation and page structure simple.

## Protect Microformats2

The blog must remain readable by Microformats2 parsers and services such as Granary.

When editing posts or templates, preserve these classes when they are relevant:

- `h-card`
- `h-feed`
- `h-entry`
- `p-name`
- `p-note`
- `p-author`
- `dt-published`
- `e-content`
- `u-url`
- `u-uid`
- `u-in-reply-to`
- `u-bookmark-of`

Every blog post should have a permalink (`u-url u-uid`), publication date (`dt-published`), title (`p-name`), content (`e-content`), and author (`p-author h-card`).

Reply posts must also include `u-in-reply-to` pointing to the original post or page being answered.

Bookmark posts must also include `u-bookmark-of` pointing to the resource being saved.

## When a student asks for a new post

1. Copy the structure of `posts/hello-world.html`.
2. Use a lowercase hyphenated filename ending in `.html`.
3. Update the title and ISO 8601 `datetime` value.
4. Add a corresponding `h-entry` to the top of the feed in `index.html`.
5. Keep the visible writing supplied by the student; do not silently rewrite their ideas unless asked.

## When a student asks for a reply post

1. Copy the structure of `posts/reply-example.html`.
2. Replace the example target URL in `u-in-reply-to` with the URL the student is replying to.
3. Keep the reply text inside `e-content`.
4. Add the reply to the top of the feed in `index.html` with the same `u-in-reply-to` relationship.
5. Do not remove the relationship markup just because the site is redesigned.

## When a student asks for a bookmark post

1. Copy the structure of `posts/bookmark-example.html`.
2. Replace the example target URL in `u-bookmark-of` with the URL the student wants to save.
3. Keep any note about the resource inside `e-content`.
4. Add the bookmark to the top of the feed in `index.html` with the same `u-bookmark-of` relationship.
5. Do not remove the relationship markup just because the site is redesigned.

## When a student asks to redesign the site

You may change layout, spacing, typography, and other CSS, but preserve semantic HTML, accessibility, and all Microformats2 classes.

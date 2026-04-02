# Future: Blog Committer

**Status:** Planned
**Priority:** Medium

## Concept

An automated flow that takes blog posts from the `Blog pipeline/ ✅ approved` stage in Notion, formats them, and commits them to a blog repository or publishing platform — removing the manual copy-paste step.

## Possible Features

- Watch for approved blog entries in Notion Blog pipeline
- Pull content + format as markdown with frontmatter
- Commit to a blog repo (GitHub Pages, Astro, Hugo, etc.)
- Auto-generate slug, tags, and publish date
- Optional: push to a CMS API (Ghost, WordPress, etc.)

## Open Questions

- Which blog platform to target first?
- Should Claude auto-commit or create a PR for review?
- How to handle images and embedded content?
- Publish schedule: immediate on approval, or batched?

## Notes

_This is a stub. Update this doc as the feature takes shape._

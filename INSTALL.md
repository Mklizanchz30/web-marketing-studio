# Install Web Marketing Studio v0.2.0 in ChatGPT web

ChatGPT web does not install an arbitrary local ZIP directly. Use this repository as a workspace marketplace source.

## Requirements

- A GitHub repository that the workspace administrator can read.
- ChatGPT workspace administrator access for the import step.

## Install

1. Extract this archive and push all contents to the root of the same GitHub repository used for the previous version. Replace the older files and preserve the hidden `.agents` directory.
2. In ChatGPT web, open **Admin > Plugins**.
3. Select **Add > Import marketplace**.
4. Enter the GitHub repository URL. Leave **Path** empty when these files are at the repository root.
5. Import the marketplace and review the result.
6. Open `web-marketing-studio`, set the installation and role policy, and make it available to the intended users.
7. In **Plugins**, install the plugin from the workspace tab.
8. Start a new chat or Work session so its bundled Skills load.

If you are not a workspace administrator, send the repository to your administrator for steps 2–6. For a personal local marketplace, use the ChatGPT desktop app or Codex CLI; that route does not make a local ZIP directly installable in ChatGPT web.

## Smoke test

Start a new Work session and try:

- `Use $local-service-leadgen to audit this service page for trust, local SEO, and lead friction.`
- `Use $design-first-ui-prompting-web to turn this idea into an implementation-ready UI brief.`
- `Use $video-to-superprompt-web to analyze this screen recording and create a build prompt.`
- `Use $build-awwwards-quality-sites to art-direct and build this premium website.`
- `Use $audit-ai-design-slop to review this interface without editing it.`
- `Use $scroll-scrubbed-visual-sequence to implement this reversible scroll sequence.`

## Included Skills

- `local-service-leadgen`
- `design-first-ui-prompting-web`
- `video-to-superprompt-web`
- `reference-brand-worlds-web`
- `reference-originality-web`
- `web-animation-performance`
- `build-awwwards-quality-sites`
- `no-ai-design-slop`
- `audit-ai-design-slop`
- `scroll-scrubbed-visual-sequence`
- `scroll-progress-timeline`
- `scroll-scrubbed-word-reveal`
- `reveal-hover-effect`
- `web-technique-to-skill`

## Official references

- [Package a plugin](https://developers.openai.com/plugins/build/plugins)
- [Use and install plugins](https://learn.chatgpt.com/docs/plugins?surface=app)
- [Import a workspace marketplace](https://learn.chatgpt.com/docs/enterprise/plugin-management)

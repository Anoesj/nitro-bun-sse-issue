# Nuxt + Bun + SSE issue
## Issue description
See: https://github.com/unjs/nitro/issues/2719

## Steps to reproduce
- Install using `bun i` with bun version 1.1.27.
- Run `bun --bun run build` (note that the Nitro preset is set to `bun` in `nuxt.config.ts`).
- Run `bun --bun run preview` and open the preview URL.
- Click the "Start SSE" button, see received event contents in the console.
- Click the "Cancel SSE" button, the Nuxt app crashes.

## Additional info
- When switching to Nitro preset `node-server` by commenting `preset: 'bun',` in `nuxt.config.ts`, and repeating the build and preset steps, the issue is not present.
- When running the app in dev mode using `bun --bun run dev`, the issue is not present.
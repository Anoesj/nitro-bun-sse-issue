# Nuxt + Bun + SSE issue
## Issue description
See: https://github.com/unjs/nitro/issues/2719

## Steps to reproduce
1. Install using `bun i` with bun version 1.1.27.
2. Run `bun --bun run build` (note that the Nitro preset is set to `bun` in `nuxt.config.ts`).
3. Run `bun --bun run preview` and open the preview URL.
4. Click the "Start SSE" button, see received event contents in the console.
5. Click the "Cancel SSE" button, the Nuxt app crashes.

## Additional info
- When switching to Nitro preset `node-server` by commenting `preset: 'bun',` in `nuxt.config.ts`, and repeating the step 2-5, the issue is not present.
- When running the app in dev mode using `bun --bun run dev`, the issue is not present.
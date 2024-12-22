# snek

This is a demo of the new `bundleStrategy: 'inline'` option in SvelteKit.

In `vite.config.js`, `assetsInlineLimit: Infinity` is set, causing all assets (fonts, images, audio) to be inlined into the JavaScript. In turn, `bundleStrategy: 'inline'` in `svelte.config.js` causes the JavaScript (and styles) to be inlined into the HTML. Finally, `router.type === 'hash'` in `svelte.config.js` makes it possible to navigate between pages.

The result is a fully self-contained `.html` file containing the entire app.

# ⚠️ Disclaimer

> **Important:**  
> This single HTML file relies on **external CDN endpoints** for parsing and Markdown rendering.

### What This Means

- Markdown parsing is loaded from a CDN  
- Math rendering (KaTeX) is loaded from a CDN  
- Syntax highlighting is loaded from a CDN  
- Styling (TailwindCSS) is loaded from a CDN  

If you go offline and these files are not cached, certain features **will not function properly**.

---

### To Make It Fully Offline

Download all external dependencies locally and replace CDN links with local file paths.

# Local -- AI Chat Interface (Frontend Only)

A fully client-side ChatGPT-style interface built with pure HTML,
TailwindCSS, and vanilla JavaScript.

------------------------------------------------------------------------

## Overview

`Index.html` is a completely self-contained AI chat frontend.

Everything runs in the browser: - UI rendering - Markdown parsing
(Marked.js) - Math rendering (KaTeX) - Code highlighting
(Highlight.js) - HTML sandbox previews - Dynamic DOM syncing

No build tools. No frameworks. No backend required unless you connect
your own API.

------------------------------------------------------------------------

## Features

-   Markdown support
-   LaTeX math rendering
-   Syntax-highlighted code blocks
-   Live HTML preview toggle inside code blocks
-   Copy-to-clipboard buttons
-   Citation sidebar system
-   Dark / Light theme support
-   Settings modal
-   Notes system

------------------------------------------------------------------------

## How It Works

### 1. Markdown + Math Rendering

All messages pass through:

``` js
renderMarkdownAndMath(element, text)
```

Process: 1. Protect math blocks (`$$`, `\(`, `\[`, `$`) 2. Parse
markdown with Marked.js 3. Render math with KaTeX 4. Apply custom link
and code formatting

------------------------------------------------------------------------

### 2. Custom Code Block Renderer

Code blocks are overridden to provide:

-   Language detection
-   Syntax highlighting
-   Copy button
-   HTML preview toggle (sandboxed iframe)

------------------------------------------------------------------------

### 3. DOM Sync Engine

Instead of replacing entire message HTML, a custom DOM diffing system:

-   Preserves scroll position
-   Prevents UI flicker
-   Maintains iframe state

------------------------------------------------------------------------

## Dependencies (CDN)

-   TailwindCSS
-   Marked.js
-   KaTeX
-   Highlight.js
-   Font Awesome

All dependencies are loaded directly inside `Index.html`.

------------------------------------------------------------------------

## Usage

1.  Open `Index.html`
2.  Connect your backend (optional)
3.  Deploy as static site if desired

------------------------------------------------------------------------

## License

Use freely. Modify as needed.

# mkgrid

> **An Instagram Grid Planner That Never Phones Home**
> *Don't post it before you mock it. YOUR feed. YOUR pixels. YOUR machine.*

<div align="center"><img src="assets/images/mkgrid-banner.png" alt="mkgrid — make grid" width="100%"></div>

---

mkgrid is a single-file, browser-based tool for planning your Instagram grid *before* you post. Drag in your photos, arrange the feed, crop every tile, span an image across a whole row, rearrange rows, preview the whole profile, and export post-ready images — or the entire feed as one picture. Nothing uploads to servers. Nothing tracks you. Nothing leaves your machine.

Built for people who want to plan a beautiful feed without handing unreleased work to big-tech surveillance capitalism 

> The privacy isn't a setting you toggle. It's the architecture. There is no backend to leak to. → **[privacy.html](https://mkgrid.app/privacy.html)**

## Quick Links

- [Quick Start](#quick-start)
- [Features](#features)
- [The Grid Is the Ad](#the-grid-is-the-ad)
- [Philosophy](#philosophy)
- [Privacy](#privacy)
- [Recommended Tools](#-recommended-tools)
- [Credits & Inspiration](#-credits--inspiration)
- [License](#-license)

---

## Why This Exists

Your Instagram grid is a first impression you only get to make once. The order of your posts, the color story across rows, a panorama sliced across three tiles — the grid is a composition, and once a post is up, re-sequencing it means deleting and re-uploading.

So people rehearse. The problem is *how*. Every existing grid planner wants you to create an account, upload your unreleased photos to their servers, and pay a monthly subscription to unlock basic features — all to preview a layout. You hand over your content and your data to plan a grid.

[mkgrid](https://mkgird.app) does the same job with none of that. It's one HTML file that runs entirely in your browser. Your photos are loaded, arranged, cropped, and exported on your own machine. There is no account, no upload, no server, no analytics. Close the tab and the only place your feed ever existed is your own browser.

The privacy of your work depends on the ownership of your work. 

It's `mkdir` for your feed: **make grid**.

---

## Quick Start

> **Never used a tool like this?** There's nothing to install and nothing to sign up for. It's a website.

**Step 1** — Open **[mkgrid.app](https://mkgrid.app)** in any modern browser (desktop or mobile).

**Step 2** — Drag your photos onto the grid, or click to pick them. They load instantly — and never leave your device.

**Step 3** — Arrange and crop:
- Drag a tile's grip to reorder
- Drag inside a tile to pan the crop; scroll or pinch to zoom
- Tap **SPAN** on a row to stretch one image across all three tiles

**Step 4** — Hit **EXPORT** for post-ready images (zipped), or the whole feed as a single picture.

That's it. Your work auto-saves locally, so it's there when you come back.

> **Tip:** Want proof nothing is uploaded? Open your browser's DevTools, watch the Network tab, and use the tool. Nothing goes out. That's the whole point.

---

## Requirements

- Any modern browser — Chrome, Safari, Firefox, Edge, Brave, LibreWolf, etc.
- That's it. No install, no account, no dependencies.

**Note on hardened browsers:** Tools with aggressive anti-fingerprinting (`privacy.resistFingerprinting` in LibreWolf / Mullvad / Tor) can interfere with canvas export. If your exported images come out striped, use a standard browser for the export step — the planning itself works everywhere.

---

## Features

### True 3:4 Grid
Instagram switched grid thumbnails to a 3:4 vertical crop in early 2025. mkgrid matches it by default, so what you plan is what posts — no surprise re-cropping when you upload. Toggle to **4:5** or **1:1** for legacy content.

### Drag, Arrange & Crop
Pointer-driven reordering with per-tile pan and continuous zoom — from whole-image (letterboxed) through fill, all the way to 5×. Every tile gets the exact crop you want. Works identically with mouse and touch.

### SPAN — One Image Across a Row
Stretch a single image seamlessly across all three tiles of a row for hero shots and panoramas. Pan and zoom the whole banner as one unit. This is the move no 1:1 planner can make.

### Editable Profile Mockup
Avatar, handle, name, bio, link, stats, and highlights — all editable, so you preview the *whole profile*, not just a grid of tiles. See exactly what a visitor sees.

### Two Exports, One Button
Individual post-ready images bundled to a single **ZIP**, or the **entire feed as one image** to hand a client or save for reference. Optional posting-order overlay numbers each tile.

### Local-Only Persistence
Your work auto-saves to **IndexedDB** — in your browser, on your device, never a server — and is restored on reload. Degrades gracefully to memory-only where storage is blocked.

### Plus
Undo / redo with keyboard shortcuts, downscale-on-import to keep things fast, and a fully responsive layout that works on desktop and mobile.

> *"The grid is the first thing they see. Plan it like it matters."*

---

## The Grid Is the Ad

Here's the trick the subscription apps can't do as cleanly: **plan one image spanned across three tiles, export the whole feed, and post it row by row.** Your profile grid becomes a single composition — a panorama, a manifesto, a billboard — assembled from individual posts that only line up because you planned them in advance.

The feed *is* the marketing. mkgrid is how you build it.

---

## Philosophy

mkgrid follows a strict set of principles:

**Privacy as architecture.** The privacy isn't a promise — it's the build. There is no backend, so there is nothing to leak, sell, or subpoena. The whole tool is a static file you can read top to bottom.

**Zero bloat.** One HTML file. No frameworks, no build step, no CDN, no `node_modules`. The ZIP writer and the canvas exporter are hand-rolled. If vanilla JS can't do it, it doesn't belong here.

**Free as in freedom.** *When everyone copyrights, copyleft.* Open source because a tool that handles your work should be one you can inspect, modify, and own — not rent.

**Don't trust me. Verify.** Open DevTools, watch the Network tab, read the source. The proof that nothing is uploaded is that there's nothing to find.

> *"A GUI makes easy tasks easy. A CLI makes difficult tasks possible. And if you're not the customer, you're the product — so mkgrid sells you nothing."*

---

## Privacy

Every action — importing, cropping, arranging, previewing, exporting — runs locally in your browser. **No image is ever transmitted anywhere.** No account, no cookies, no analytics, no third-party scripts. Your work saves to IndexedDB on your device.

The site itself is a static file hosted on GitHub Pages behind Cloudflare, which keeps standard access logs (IP, timestamp) for security — purged automatically. mkgrid itself records nothing.

> *"Privacy is not secrecy. A private matter is something one doesn't want the whole world to know, but a secret matter is something one doesn't want anybody to know. Privacy is the power to selectively reveal oneself to the world."* — Eric Hughes, *A Cypherpunk's Manifesto*

That's exactly what planning a feed is: deciding, in private, what you'll reveal in public.

**[→ Full privacy policy](https://mkgrid.app/privacy.html)**

---

## Tech Stack

- **HTML5 / CSS3 / Vanilla JS** — semantic, single-file, no frameworks
- **IndexedDB** — local persistence (memory-only fallback)
- **Canvas API** — all image + ZIP export, hand-rolled, zero libraries
- **Pointer Events** — unified mouse + touch
- **GitHub Pages** — static hosting · **Cloudflare** — DNS + SSL

> **⚠️ Cloudflare SSL:** keep mode on **Custom** (not Full Strict) with GitHub Pages — Full Strict throws Error 526. If the site 526s, check this first.

---

## 🔧 Recommended Tools

mkgrid is one piece of a private creative workflow. The broader stack worth building around it:

### Image & Metadata
- **[exiftool](https://exiftool.org)** — strip EXIF/GPS metadata from photos *before* posting. Prevents doxxing via image data.
- **[Adobe Photoshop](https://www.adobe.com/products/photoshop.html)** — useful for optimizing and editing images prior to grid mockup
- **[GIMP](https://www.gimp.org/)** / **[Krita](https://krita.org/)** — open source image editors
- **[Squoosh](https://squoosh.app/)** — local, in-browser image compression (also zero-upload)

### Further Reading
Looking for more? I maintain an ever-evolving list of 1,000+ hand-picked privacy tools, books, and resources at **[chrisvrakas.com/resources.html](https://chrisvrakas.com/resources.html)** — also an open-source repo at **[github.com/chrisvrakas/awesome-polymathic-resource-stack](https://github.com/chrisvrakas/awesome-polymathic-resource-stack)**.

---

## 🙏 Credits & Inspiration

mkgrid is built on a belief that creative tools can be private *and* good. In that spirit:

- **[@chris_vrakas](https://instagram.com/chris_vrakas)** — years of hand-planning a feed in Photoshop, the workflow this tool replaces
- Every cypherpunk, hacker, and contrarian who proved software can respect you and still be a joy to use
- **The FOSS community** — for the radical idea that the tools you depend on should be ones you can read and own
- **[GitHub Pages](https://pages.github.com)** & **[Cloudflare](https://cloudflare.com)** — free static hosting + SSL that just works

---

## 📄 License

**When everyone copyrights, copyleft.**

Open source under the [MIT License](LICENSE) — fork it, modify it, learn from it. Just give credit where it's due.

> Copyright wasn't handed down from on high. In 1710 the Statute of Anne broke the Stationers' monopoly on knowledge by *limiting* copyright — and for the first time, works like Shakespeare's escaped the control of monopoly publishers. Free culture was born from a limit on control, not an expansion of it. mkgrid is built in that tradition: a tool you can read, fork, and own.

---

## 📬 Contact

**Chris Vrakas**

- Website: [chrisvrakas.com](https://chrisvrakas.com)
- Instagram: [@chris_vrakas](https://instagram.com/chris_vrakas) · [@mkgrid.app](https://instagram.com/mkgrid.app)
- GitHub: [@chrisvrakas](https://github.com/chrisvrakas)
- X: [@chris_vrakas](https://x.com/chris_vrakas)
- Medium: [@chrisvrakas](https://medium.com/@chrisvrakas)

---

## ⚡ Fast Facts

- **Zero install** — no npm, no build step, no dependencies. One HTML file.
- **Zero tracking** — no analytics, no cookies, no fingerprinting, no phoning home
- **Zero upload** — your photos never leave the browser. There's no server to send them to.
- **Zero trust** — in subscription creator-tools, in surveillance capitalism, in the idea that planning a grid should cost you your data
- **100% HTML/CSS/JS** — readable, auditable, forkable, yours
- **Shows its work** — open the source or the Network tab. Nothing is hidden, because nothing is happening behind your back.

---

<div align="center">

*"In the age of algorithmic surveillance, curate in private and publish in public."*

<br>

**[mkgrid.app](https://mkgrid.app)** · **[@mkgrid.app](https://instagram.com/mkgrid.app)** · **[GitHub](https://github.com/chrisvrakas/mkgrid)**

<br>

*Don't post it before you mock it.*

</div>

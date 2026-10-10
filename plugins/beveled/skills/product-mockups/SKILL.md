---
name: product-mockups
description: Make product mockups, App Store screenshots, social images, showreels and launch videos from screenshots or a running app with the Beveled MCP tools. Use when the user asks for a mockup, device frame, hero image, App Store / Play Store screenshots, Product Hunt or Open Graph images, or "make my app look good" visuals.
---

# Product mockups with Beveled

Beveled has two studios:
- **2d**: flat frames like a design tool. Screenshot styles, browser windows, device frames, headlines with highlighted words, App Store layouts. Best for marketing images with copy.
- **3d**: photoreal, lit devices (iPhone, Pixel, Galaxy, iPad, MacBook, Studio Display, Apple Watch) in sets such as a dark room, a concrete or oak desk, or a white cyclorama. Best for hero shots and video.

## Workflow

1. If you haven't yet, call `list_mockup_options` once and pick ids from it. Never guess template or device ids.
2. Get the screen:
   - A file or URL the user gave you → `create_mockup`.
   - A public webpage → `capture_page_mockup`. The hosted connector cannot access local files or localhost; use the local MCP package for those inputs. Use `viewport: "phone"` for mobile layouts, `"laptop"` for web apps, and `full_page: true` for long pages.
   - Several app screens with one design → `create_app_store_set`.
   - A collection of work (portfolio pieces, renders, clips) → `create_showreel`. Default template `viewfinder`; `darkroom`, `turntable`, `gallery-walk` and `negative` are other Studio originals. Use `1080x1350` for Instagram, `1080x1920` for Reels/Stories, `1920x1080` for headers.
3. Check the preview image that comes back. If the device is too big or too small use `zoom`; if the copy is too long, shorten the headline; then render again.
4. Return the preview and embedded finished file. Video calls may take several minutes; hosts with a fixed one-minute timeout may stop waiting before rendering completes.

The hosted connector processes supplied content on Cloudflare. Use non-sensitive demo content. Setup and troubleshooting: https://beveled.app/mcp.html. Privacy: https://beveled.app/privacy.html.

## Choosing well

- Match the device to the screenshot's shape: tall → phone (`iphone-17-pro`), wide → `browser` (2d) or `macbook-pro-14` / `studio-display` (3d), square-ish → `ipad-pro-13`.
- Headlines: 2 to 6 words, and wrap the key word in `*stars*` to highlight it. Put detail in `subtitle`.
- Sizes: `app-store-iphone-6-9` (1320×2868) for App Store, `instagram-post`, `x-twitter-post`, `linkedin-post`, `product-hunt-gallery`, `youtube-thumbnail`, or `WIDTHxHEIGHT`.
- `background`: prefer a backdrop id from the `backgrounds` list in `list_mockup_options`. Studio sweeps (`sweep-paper`, `sweep-charcoal`, `sweep-ember`) suit 3D hero shots; soft gradients (`grad-apricot`, `grad-sage`, `grad-coast`) and solids (`solid-bone`) suit 2D marketing images. Raw colours also work (one for solid, several for a gradient), and `"transparent"` gives a cut-out PNG (3d works best for this). Avoid saturated purple-blue gradients; they read as generic.
- Stills of animated templates: set `time` (seconds) to capture mid-move instead of the first frame.
- Video: `format: "mp4"` with an animated template (marked `animated` in the options) renders the camera move.
- Defaults are good. Only set what the user asked for, plus the device and size that fit.

# Windows Codex layout fixes

These selectors were observed in a Windows Store/MSIX Codex build on 2026-10-13. Inspect the current DOM, computed styles, and screenshot before reusing them. Apply only selectors that still match, then visually verify the result.

## Audit every place the wallpaper affects readability

Capture the home screen, a normal conversation, and the edit form with the sidebar both expanded and collapsed. Repeat at a narrower window width. For each screenshot, identify text, icons, or controls that blend into the image, including title bar buttons, header text, message timestamps, links, the composer, and dialogs. Check the actual rendered result and click targets, not only whether CSS injected successfully.

For a problem area, select its smallest stable DOM container and add a semi-transparent surface, localized `backdrop-filter: blur(...)`, and a border or shadow when needed. Set explicit foreground and caret colors on text inputs. Tune surface opacity and text contrast together: blur alone cannot guarantee legibility. Keep the wallpaper itself sharp outside the affected container and avoid broad rules that cover the whole page or block pointer events. After each change, confirm text remains legible, controls remain usable, the image still reads as an image, and expanded/collapsed layout stays aligned. Treat the snippets below as build-specific examples, not selectors to paste blindly.

## Keep the image visible

If the generated background disappears, check the computed background at `#root`. Chromium may discard a combined declaration that mixes a data URL with `color-mix()`. Prefer a plain `background: url(...) right center / cover no-repeat` declaration and put translucent overlays on the relevant child surfaces.

## Separate the top bar and clarify window controls

A pale translucent surface and border make title text and upper-right controls readable against a busy sky.

```css
[class*="_ApplicationMenuTopBar_"] {
  background: linear-gradient(90deg,
    color-mix(in srgb, var(--heige-surface) 72%, transparent),
    color-mix(in srgb, var(--heige-surface) 97%, transparent)) !important;
  backdrop-filter: blur(14px) !important;
  color: var(--heige-text) !important;
  border-bottom: 1px solid color-mix(in srgb, var(--heige-accent) 24%, transparent) !important;
}

header[class*="_ApplicationMenuPageHeader_"] {
  background: color-mix(in srgb, var(--heige-surface) 86%, transparent) !important;
  backdrop-filter: blur(10px) !important;
  color: var(--heige-text) !important;
  border-top: 1px solid color-mix(in srgb, var(--heige-accent) 30%, transparent) !important;
  border-bottom: 1px solid color-mix(in srgb, var(--heige-accent) 36%, transparent) !important;
}
```

## Make the composer fade follow the content width

When the left sidebar collapses, a page-wide white rectangle behind the composer looks abrupt. After identifying the actual composer and overlay nodes, constrain only the fade overlay to the content width and soften its edges.

```css
[class*="thread-composer-bottom-inset"] > [class*="-top-8"][class*="z-0"] {
  left: 50% !important;
  right: auto !important;
  width: min(100%, var(--thread-content-max-width, 48rem)) !important;
  transform: translateX(-50%) !important;
  background: linear-gradient(180deg,
    transparent 0%,
    color-mix(in srgb, var(--heige-surface) 42%, transparent) 42%,
    color-mix(in srgb, var(--heige-surface) 68%, transparent) 100%) !important;
  backdrop-filter: blur(7px) !important;
  -webkit-mask-image: linear-gradient(90deg, transparent, #000 7%, #000 93%, transparent);
  mask-image: linear-gradient(90deg, transparent, #000 7%, #000 93%, transparent);
}
```

## Make editing a sent message readable

The normal message bubble may have a pale surface while its edit form remains translucent. Scope the background to the form and its editable textbox so the text and caret remain visible without covering neighboring messages.

```css
[class*="group/user-message"] form:has([role="textbox"][contenteditable="true"]) {
  color: var(--heige-text) !important;
  background: color-mix(in srgb, var(--heige-surface) 92%, transparent) !important;
  border: 1px solid color-mix(in srgb, var(--heige-accent) 32%, transparent) !important;
  box-shadow: 0 8px 24px color-mix(in srgb, var(--heige-text) 14%, transparent) !important;
  backdrop-filter: blur(10px) !important;
}

[class*="group/user-message"] form [role="textbox"][contenteditable="true"] {
  color: var(--heige-text) !important;
  caret-color: var(--heige-accent) !important;
}
```

The observed computed style after the fix had a 92% pale-purple surface, `blur(10px)`, and dark text near `rgb(48, 35, 62)`. Open an actual edit form in the current Codex version to confirm.

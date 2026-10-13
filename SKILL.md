---
name: codex-bunbun-wallpaper
description: Check Codex Desktop's native image-background support, create, apply, or freely switch supported image wallpapers through the theme center, and repair persistence, blur, layout, and text readability on Windows. Use for this in-app wallpaper workflow, not Windows wallpaper or ChatGPT Pets.
---

# Purple Bunbun wallpaper for Codex Desktop

Create or apply a persistent image background **inside Codex Desktop**. The bundled `assets/purple-bunbun-wallpaper.png` is the default example; a user can request a different image. The character must remain visible and text and controls readable. A plain purple color does not fulfill an image-wallpaper request.

## Scope and preparation

- Confirm the target is the Codex app interface, not Windows wallpaper or ChatGPT Pets.
- Run the [native capability check](references/native-capability-check.md) on the installed Codex build before selecting an implementation. Record observed results rather than claiming that all Codex versions lack wallpaper support. Do not reinstall Codex just to apply the wallpaper.
- Inspect the current Codex installation, existing theme, HeiGe Codex Skin Studio installation, and persistence mechanism before changing them.
- Use HeiGe only after reviewing its source, installer side effects, and local CDP connection method. Its CDP endpoint is unauthenticated within the local user session; keep it local and close it when no longer needed.
- Back up the active theme JSON, wallpaper, and CSS before editing. Keep credentials, conversation content, local personal paths, and screenshots out of any published repository.

## Choose or create the image

If the user wants a new subject, palette, or composition, follow [wallpaper design](references/wallpaper-design.md). Use an available image-generation capability to create the requested wallpaper, inspect it, and use the approved result. Otherwise use the bundled image or a user-provided image. Do not silently substitute a solid color or claim that a generated illustration is an official game asset.

## Switch wallpapers in the theme center

The user may replace the visible wallpaper whenever they want. Follow [switching wallpapers](references/switch-wallpaper.md) for HeiGe's **主题 → ＋ 自定义图片** flow. A new upload becomes a selectable custom theme; it does not necessarily edit the bundled Bunbun theme in place or preserve its palette and readability fixes. Recheck the new theme's layout and contrast. If the panel says **仅本机快捷・未写入启动器**, treat the image as session/local only until launcher persistence is verified.

## Apply the image

1. If this Codex build has a native image-background setting, use it and verify the result in the actual window and after a restart. Otherwise use the reviewed HeiGe route below.
2. Use the installed HeiGe tool's image-theme creation flow with the selected image. For the bundled image, a suggested palette is pale purple surface `#f5edfa`, dark text `#30233e`, accent `#aa75dc`, and border `#ddc4ef`.
3. Apply the generated theme to the verified Codex Desktop window. For Windows Store/MSIX installations, inspect the real executable path, CDP port, theme storage path, and persistence setup instead of assuming a conventional install location.
4. If the user wants the theme to survive restart, configure and verify the HeiGe persistence task. Record what launches it, when it runs, and how to pause or remove it.
5. Check the actual Codex window and computed styles at `#root`. A successful injection response alone does not prove the image is visible. If the app falls back to a solid color, inspect the background URL, stacking order, and whether a `color-mix()` or data-URL combination was discarded.

## Readability and responsive layout

Run the screenshot and contrast audit in [Windows layout fixes](references/windows-layout.md). It covers the top bar and window controls, the composer fade when the left sidebar collapses, the edit form for an already sent message, and any newly obscured surface. Inspect the live DOM and computed styles before applying selectors: Codex class names and layout can change between releases.

## Acceptance checks

- Report the installed build's native capability check: setting found or absent, image import result if available, visible result, and persistence result. "No setting found in this build" is not a claim about every Codex release.
- The requested image is clearly visible inside Codex; title text, window controls, normal messages, and the composer remain readable.
- With the sidebar both open and collapsed, the bottom fade tracks the composer/content width and does not leave a large rectangular block.
- In edit-message mode, typed text, caret, Cancel, and Send remain easy to see. Do not alter the original message content.
- Check the home screen and a conversation at normal and narrower window widths. Repair any newly obscured text or control with a local translucent/blurred surface and adequate text contrast, then inspect a fresh screenshot.
- Verify persistence from the actual task or launcher state and by reopening Codex once when feasible. Report separately what was applied, what is visible now, and what remains unverified.

This Skill documents a workflow; it does not contain the HeiGe source code or installer.

---
name: codex-bunbun-wallpaper
description: Apply or repair this purple Bunbun image wallpaper inside Codex Desktop on Windows, including persistence and text readability. Use for this specific in-app theme, not Windows wallpaper or ChatGPT Pets.
---

# Purple Bunbun wallpaper for Codex Desktop

Apply `assets/purple-bunbun-wallpaper.png` as a persistent image background **inside Codex Desktop**. The user wants the character visible, with readable text and controls. A plain purple color does not fulfill this request.

## Scope and preparation

- Confirm the target is the Codex app interface, not Windows wallpaper or ChatGPT Pets.
- Inspect the current Codex installation, existing theme, HeiGe Codex Skin Studio installation, and persistence mechanism before changing them. Do not reinstall Codex just to apply the wallpaper.
- Use HeiGe only after reviewing its source, installer side effects, and local CDP connection method. Its CDP endpoint is unauthenticated within the local user session; keep it local and close it when no longer needed.
- Back up the active theme JSON, wallpaper, and CSS before editing. Keep credentials, conversation content, local personal paths, and screenshots out of any published repository.

## Apply the image

1. Use the installed HeiGe tool's image-theme creation flow with this Skill's `assets/purple-bunbun-wallpaper.png`. Suggested palette: pale purple surface `#f5edfa`, dark text `#30233e`, accent `#aa75dc`, and border `#ddc4ef`.
2. Apply the generated theme to the verified Codex Desktop window. For Windows Store/MSIX installations, inspect the real executable path, CDP port, theme storage path, and persistence setup instead of assuming a conventional install location.
3. If the user wants the theme to survive restart, configure and verify the HeiGe persistence task. Record what launches it, when it runs, and how to pause or remove it.
4. Check the actual Codex window and computed styles at `#root`. A successful injection response alone does not prove the image is visible. If the app falls back to a solid color, inspect the background URL, stacking order, and whether a `color-mix()` or data-URL combination was discarded.

## Readability and responsive layout

Read [Windows layout fixes](references/windows-layout.md). They cover the top bar and window controls, the composer fade when the left sidebar collapses, and the edit form for an already sent message. Inspect the live DOM and computed styles before applying selectors: Codex class names and layout can change between releases.

## Acceptance checks

- The Bunbun image is clearly visible inside Codex; title text, window controls, normal messages, and the composer remain readable.
- With the sidebar both open and collapsed, the bottom fade tracks the composer/content width and does not leave a large rectangular block.
- In edit-message mode, typed text, caret, Cancel, and Send remain easy to see. Do not alter the original message content.
- Verify persistence from the actual task or launcher state and by reopening Codex once when feasible. Report separately what was applied, what is visible now, and what remains unverified.

This Skill documents a workflow; it does not contain the HeiGe source code or installer.

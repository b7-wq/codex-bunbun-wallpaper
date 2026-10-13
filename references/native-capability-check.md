# Native wallpaper capability check

Codex Desktop changes between releases. Test the installed build before deciding how to apply an image. Record the app version, Windows distribution (Store/MSIX or other), date, and any relevant appearance setting. Do not infer a universal product limitation from one build.

1. Inspect Codex Settings > Appearance (and any theme/background controls) in the actual installed app. Check current official Codex documentation or release notes when available. Look specifically for importing or selecting an **image** as the app background; a color theme or pet is not equivalent.
2. If an image option exists, use a temporary user-provided or bundled image. Confirm that the image appears behind the Codex interface, not on the Windows desktop, and that it remains visible with the sidebar open and collapsed.
3. Close and reopen Codex once when feasible. Check whether the image persists without a third-party launcher. If a feature is documented but the setting fails in this build, record the observed failure and diagnostic details.
4. If no image option is present, record "no native image-background control found in this build" with the version and inspected screens. Continue with the reviewed HeiGe route if the user wants the background applied.

Report these separately: **setting present**, **image accepted**, **image visibly rendered**, **persists after restart**. Use "not tested" for checks that could not be performed. A color or solid-purple result does not pass the image-rendered check.

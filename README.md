# Codex purple Bunbun wallpaper

A purple Bunbun image wallpaper **inside Codex Desktop for Windows**, packaged as a reusable Codex Skill. It checks whether the installed Codex build can set an image background natively, can guide generation of a different requested image, and repairs readability with local blur and contrast adjustments.

## What the Skill does

- Checks the installed Codex version and its actual Appearance controls for native image-background support. It tests image rendering and restart persistence when that control exists; absence is reported for that build only.
- Uses the included image, a user-provided image, or an image generated from the user's description when an image-generation tool is available.
- Applies the image through a native setting when available, or through a separately reviewed HeiGe installation. It verifies the visible result and persistence.
- Audits the top bar, message text, composer, edit form, dialogs, and narrower layouts. It adds translucent blur and stronger text contrast only where the wallpaper makes content hard to read.

## Demo / 效果预览

![Purple Bunbun wallpaper running in Codex Desktop](assets/demo-codex-bunbun.png)

*Screenshot from Codex Desktop on Windows. Conversation titles in the sidebar are blurred.*

## Use

Install this repository as a Codex Skill, or copy `SKILL.md`, `references/`, and `assets/` into a `codex-bunbun-wallpaper` folder under your Codex skills directory. Then ask Codex to apply the purple Bunbun wallpaper, or describe a new image to create and apply. The original wallpaper image is [included here](assets/purple-bunbun-wallpaper.png).

The Skill uses the separately installed HeiGe Codex Skin Studio as its theme engine. This repository does not bundle or claim ownership of that tool. Review its source and installer before using it.

## Search terms / 搜索关键词

Codex Desktop wallpaper · Codex theme · Codex skin · Codex Skill · purple Bunbun wallpaper · purple rabbit theme · Windows Codex customization · Codex 壁纸 · Codex 主题 · 紫色兔球 · 兔球球背景

This is an unofficial customization. It relies on the current Codex Desktop page structure and may need adjustment after app updates. The wallpaper is a custom generated illustration from this conversation, not an official game asset.

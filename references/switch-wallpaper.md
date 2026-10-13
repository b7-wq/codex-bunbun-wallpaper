# Switch to any supported image wallpaper

This Skill is not locked to the bundled Bunbun picture. In an installed HeiGe theme center, open **主题**, click **＋ 自定义图片**, and choose a local PNG, JPG/JPEG, or WebP image. HeiGe creates a selectable custom theme and may adjust the light/dark appearance and palette based on the image. Select that theme and inspect the actual Codex window. To use an AI-generated or scripted image, the reviewed `create --image` and Windows `apply.ps1` path in the HeiGe Skill is another route.

"Any wallpaper" means any suitable image that passes the tool's format, size, and dimensions checks. The new picture may be a different custom theme rather than a replacement inside the existing Bunbun theme. Do not promise that its original colors or CSS overlays automatically carry over. When the user wants to keep the same visual treatment, apply the previous palette and the relevant [layout fixes](windows-layout.md) to the new image, then verify with a screenshot.

Check persistence separately from an on-screen switch. If the theme center shows **仅本机快捷・未写入启动器** or **控制通道不可用**, the current image may be only a local/session selection. Check the launcher or persistence-task state and reopen Codex when feasible. Report "visible now" and "persists after restart" separately. Do not describe the image as permanently installed until both are verified.

For the screenshots in the README, the theme-center screenshot demonstrates the image chooser and also shows the local-shortcut warning; the second screenshot demonstrates another image visibly applied in Codex. They do not, by themselves, prove restart persistence.

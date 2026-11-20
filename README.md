# Video Editor AI

A standalone video editing skill for Claude Code and Codex. Review footage, decide what to reshoot, plan a cut with source timecodes, refine captions and export locally when your environment supports it.

**Видеомонтажёр и видеоредактор для Claude Code и Codex.** Разбирает исходники, предлагает монтаж с таймкодами и помогает собрать готовый файл локально.

[Website · Инструкция на русском](https://bearatol.github.io/video-editor-ai/) · [Issues](https://github.com/bearatol/video-editor-ai/issues)

## Install

In Claude Code, run these commands in a conversation:

```text
/plugin marketplace add bearatol/video-editor-ai
/plugin install video-editor-ai@video-editor-ai-plugins
```

Open a new conversation and invoke `/video-editor-ai:video-editor`.

For Codex CLI with plugin support:

```sh
codex plugin marketplace add bearatol/video-editor-ai --ref main
codex plugin add video-editor-ai@video-editor-ai-plugins
```

Open a new session and select the `video-editor` skill. These instructions install from GitHub.

## Example requests

- Review this interview and tell me which sections to keep, trim, or reshoot.
- Plan a 45-second vertical cut. Give me source in/out timecodes and caption cues.
- Export the approved cut locally at 1080 × 1920. Preserve the original clips.

## Local export

The skill uses existing FFmpeg and ffprobe for media inspection and local export. If they are unavailable, it can still return a footage review or a timecoded cut plan. An explicit request to install FFmpeg authorizes one installation through an existing supported package manager within the host's permissions. The skill checks both executables before proceeding. An editing request alone does not authorize installation. The package has no bundled executable scripts.

Use footage and transcripts you are authorized to share. The skill keeps media in the host environment and does not send it to a separate renderer. The host application and public site have their own data handling. See [privacy](https://bearatol.github.io/video-editor-ai/#privacy).

## Migrating from CEO AI

The former `ceo-ai:video-editor` skill now lives here. Use `video-editor-ai:video-editor` for video work. Your existing media and editing projects can be used with the new skill.

## License

[MIT](LICENSE). The skill is extracted from the MIT-licensed CEO AI release 0.10.4.

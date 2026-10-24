# Changelog

## Unreleased

- **Content capture is asked for by default.** The Desktop extension's "Also share prompts, responses and tool details" setting is on by default; turn it off to share usage only. The Cowork helper asks for tool details on `connect` and for content on `connect --local` unless `--no-tool-details` or `--no-content` is passed; the old flags are still accepted. Turning the Desktop setting off now stops content at the next sync even on a device that connected with it on, and any value but an explicit `true` counts as off. Nothing beyond usage is sent until an owner or administrator grants it in Sabia, which now asks for that grant on every connect (dashboard-langfuse#498).

## 0.6.1

- Moved here from `Sabia-Partners/sabia-claude-plugin`, with history, so that repository holds only the Claude Code plugin listed in Anthropic's directory. The Desktop extension and the Cowork helper are unchanged; earlier history is in that repository's changelog up to 0.6.0.
- The release now attaches `sabia.mcpb` and `sabia-claude-desktop.tar.gz`. Sabia links to this repository's `releases/latest/download/sabia.mcpb`.

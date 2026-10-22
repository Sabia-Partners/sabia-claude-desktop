# Sabia for Claude Desktop

Sabia is AI Work Intelligence for teams: it shows what work came out of the AI
tools a company already pays for, and what that work cost. This repository holds
the parts of Sabia's Claude integration that run beside Claude Desktop rather
than inside Claude Code.

[![Checks](https://github.com/Sabia-Partners/sabia-claude-desktop/actions/workflows/ci.yml/badge.svg)](https://github.com/Sabia-Partners/sabia-claude-desktop/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

| Folder | What it is |
| --- | --- |
| [`desktop-extension`](desktop-extension) | **Sabia for Claude Desktop** (`sabia.mcpb`, attached to each release): shares Claude Cowork usage from any Claude plan. Sabia links to `releases/latest/download/sabia.mcpb`. |
| [`cowork`](cowork/README.md) | The command-line engine behind the extension, and an administrator helper for Cowork's own OpenTelemetry export on Team and Enterprise. |

The Claude Code plugin is a separate repository,
[Sabia-Partners/sabia-claude-plugin](https://github.com/Sabia-Partners/sabia-claude-plugin),
and is listed in Anthropic's plugin directory. The Desktop extension is
distributed directly from Sabia.

## What the extension sends

On first start it opens Sabia's approval page once. After that it reads the
usage Claude Desktop records for your Cowork sessions on this device (per turn
and model: token counts, number of calls, time and session id) and sends it to
your Sabia organization every ten minutes while Claude is open. Prompts,
responses and tool details are sent only when you turn on content sharing in
the extension's settings **and** an owner or administrator approves it in Sabia.
[`cowork/README.md`](cowork/README.md) covers the details.

## Development

```text
pnpm install --frozen-lockfile
pnpm check
pnpm test
pnpm build:extension   # dist/sabia.mcpb
```

To release, raise the version in `package.json` and
`desktop-extension/manifest.json`, then tag `vX.Y.Z`. The release workflow runs
the checks and attaches `sabia.mcpb` and `sabia-claude-desktop.tar.gz`. The
asset name `sabia.mcpb` must not change.

## Security and license

Report vulnerabilities privately. [SECURITY.md](SECURITY.md) explains how.
Support: [sabiapartners.ca/contact](https://sabiapartners.ca/contact). Released
under the [MIT License](LICENSE).

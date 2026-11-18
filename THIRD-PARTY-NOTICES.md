# Third-Party Notices

Last updated: 2026-11-18

This file covers the archival `v1.1.0` baseline snapshot and every direct
third-party dependency declared by that version. Full license texts are kept in
[`licenses/`](licenses/), and the original project license is in
[`LICENSE`](LICENSE).

## Project provenance and original license

- Upstream project: `qingnian108/magpie-agent-console`
- Upstream tag: `v1.1.0`
- Upstream commit: `6e5c7e43472d434b0802e47324ae52e12ec59bc1`
- Original license: MIT
- Original copyright: `Copyright (c) 2026 qingnian108`

This repository only archives that upstream version. The maintained, modified
Quick Chat fork is
`TGOTYL/magpie-agent-console-quick-chat`.

The project's architecture and UI were informed by these projects. According
to the upstream project's notice, only design ideas and protocol shapes were
used, not copied source code:

- **Paseo** - <https://github.com/getpaseo/paseo>
  - persistent daemon + WebSocket event push
  - provider-session abstraction
- **T3 Code** - <https://github.com/pingdotgg/t3code> (MIT)
  - timeline item shapes such as tool groups, permission cards and plan cards
  - three-column workbench layout

## Runtime dependencies installed with the plugin

These packages are declared in `package.json` and are installed for users.

| Package | Version | License | Notes |
|---|---:|---|---|
| `@agentclientprotocol/sdk` | 2.1.0 | Apache-2.0 | ACP client/runtime support |
| `ignore` | 7.0.14 | MIT | `.gitignore` handling |
| `node-pty` | 1.2.0-beta.15 | MIT | Optional native terminal dependency |
| `node-addon-api` | 7.1.1 | MIT | Transitive dependency of `node-pty` |
| `ws` | 8.22.0 | MIT | WebSocket server |
| `zod` | 4.6.7 | MIT | Runtime schema validation |

`@agentclientprotocol/sdk` declares `@modelcontextprotocol/server` as an
optional peer dependency. It is not installed or bundled by this project.

`node-pty` is optional. Its `bufferutil` and `utf-8-validate` peers are optional,
are not installed by this project, and are not distributed here.

## Frontend libraries bundled into `app/app.js`

The following packages are built into the browser bundle:

| Package | Version | License |
|---|---:|---|
| `@tanstack/react-virtual` | 3.14.24 | MIT |
| `@tanstack/virtual-core` | 3.19.9 | MIT |
| `@xterm/addon-fit` | 0.11.0 | MIT |
| `@xterm/xterm` | 6.0.0 | MIT |
| `dompurify` | 3.4.17 | MPL-2.0 OR Apache-2.0 |
| `highlight.js` | 11.12.0 | BSD-3-Clause |
| `marked` | 18.1.2 | MIT |
| `react` | 19.3.1 | MIT |
| `react-dom` | 19.3.1 | MIT |
| `scheduler` | 0.28.0 | MIT |
| `zustand` | 5.0.16 | MIT |

`dompurify` may be used under either MPL-2.0 or Apache-2.0. Both license texts
are included.

## Declared frontend dependencies not distributed in the built bundle

These packages are declared in `package.json`, but the source has no import of
them and they are not present in the production browser bundle. Their license
texts are still included for completeness.

| Package | Version | License |
|---|---:|---|
| `clsx` | 2.1.1 | MIT |
| `lucide-react` | 1.64.0 | ISC |

## Build and test dependencies

These packages are development-only and are not installed for plugin users and
are not shipped inside the plugin:

| Package | Version | License |
|---|---:|---|
| `@types/dompurify` | 3.0.5 | MIT |
| `@types/node` | 26.6.6 | MIT |
| `@types/react` | 19.3.0 | MIT |
| `@types/react-dom` | 19.3.0 | MIT |
| `@types/ws` | 8.18.2 | MIT |
| `esbuild` | 0.28.2 | MIT |
| `esbuild-wasm` | 0.28.2 | MIT |
| `playwright-core` | 1.64.1 | Apache-2.0 |
| `typescript` | 7.0.2 | Apache-2.0 |
| `vitest` | 5.0.5 | MIT |

The complete transitive dependency graph and exact resolved versions are
recorded in `package-lock.json`.

## OpenAI Codex app-server schema

The JSON files under `daemon/src/providers/codex/schema/` were generated from
the OpenAI Codex app-server schema with
`codex app-server generate-json-schema`. They are used only for protocol
integration with Codex.

- Project: OpenAI Codex - <https://github.com/openai/codex>
- License: Apache-2.0
- Full text: [`licenses/APACHE-2.0-openai-codex.txt`](licenses/APACHE-2.0-openai-codex.txt)
- Upstream notice: [`licenses/NOTICE-openai-codex.txt`](licenses/NOTICE-openai-codex.txt)

## Full license texts

Every bundled or installed package listed above has its full upstream license
text in [`licenses/`](licenses/). File names identify the SPDX license and
package. The MIT and Apache-2.0 texts are repeated per package so each
package's original notice remains attached to its corresponding terms.

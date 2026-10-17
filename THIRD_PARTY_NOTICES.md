# Third-Party Notices

This project includes third-party components. Redistribution of this extension should preserve the applicable third-party license notices and terms.

> Informational notice: this file is a practical compliance aid and not legal advice.

## Project License

- Version 2.0.0 and later of this extension are proprietary commercial software
  licensed under the End User License Agreement (see `LICENSE.md`). Versions
  1.1.104 and earlier were licensed under MIT (reproduced in section 20 of
  `LICENSE.md`).

## Runtime dependencies (Node.js, packaged in the VSIX)

Shipped as files in `node_modules/` (native CLR bridges, loaded at run time):

- `electron-edge-js` (43.0.0) — MIT
- `edge-js` (25.0.1) — MIT
- `edge-cs` (1.3.7) — MIT
- Transitive:
  - `nan` (2.28.0) — MIT (build-time only, not packaged)

Bundled (minified) into `out/extension.js` — the localhost MCP server and its
dependencies:

- `@modelcontextprotocol/sdk` (1.30.1) — MIT, Copyright (c) 2024 Anthropic, PBC
- `zod` (4.6.5) — MIT, Copyright (c) 2025 Colin McDonnell
- `zod-to-json-schema` (3.25.2) — ISC, Copyright (c) 2020, Stefan Terdell
- `ajv` (8.20.0) — MIT, Copyright (c) 2015-2021 Evgeny Poberezkin
- `ajv-formats` (3.0.1) — MIT, Copyright (c) 2020 Evgeny Poberezkin
- `fast-deep-equal` (3.1.3) — MIT, Copyright (c) 2017 Evgeny Poberezkin
- `json-schema-traverse` (1.0.0) — MIT, Copyright (c) 2017 Evgeny Poberezkin
- `fast-uri` (3.1.5) — BSD-3-Clause, Copyright (c) 2011-2021, Gary Court;
  Copyright (c) 2021-present The Fastify team
- `hono` (4.13.9) — MIT, Copyright (c) 2021 - present, Yusuke Wada and Hono contributors
- `@hono/node-server` (2.1.1) — MIT, Copyright (c) 2022 - present, Yusuke Wada and Hono contributors
- `content-type` (1.0.5) — MIT, Copyright (c) 2015 Douglas Christopher Wilson

The license texts are available in each package's repository (linked from its
npm page). The list reflects the esbuild bundle of the current build — re-check
it when dependencies change (see the checklist below).

## .NET viewer library

- `dotnet/TiaViewer` — intentionally **zero-dependency** (no runtime NuGet
  packages); only the `net48` build ships. It references only .NET Framework
  platform assemblies: `System.IO.Compression` (xlsx tag tables),
  `System.Net.Http` (PLC web API), `System.Management` and `System.Security`
  (license hardware fingerprint and protected license store).
  No third-party .NET binaries are redistributed.

## Build-time tools (not redistributed)

- `Obfuscar` (2.2.50) — MIT — NuGet package that obfuscates the shipped
  `TiaViewer.dll` at build time (`npm run build:dotnet`).
- `esbuild` — MIT — bundles the extension and minifies the embedded viewer
  scripts.
- `@vscode/vsce`, `typescript`, `ts-node`, `mocha` and the xUnit test
  packages — development and packaging only.

## Vendored web assets (embedded in the viewer library)

- `uPlot` (1.6.32) — MIT, https://github.com/leeoniya/uPlot
  (`dotnet/TiaViewer/Assets/uplot.min.js` / `uplot.min.css`; vendored
  unmodified, used by the online trend chart page of the PLC web preview).
  Copyright (c) 2022 Leon Sorokin. The MIT license text is available at
  https://github.com/leeoniya/uPlot/blob/master/LICENSE.

## No Siemens components

Unlike the companion CMsoft Import for TiaPortal extension, this viewer does **not**
use, reference or redistribute any Siemens TIA Portal Openness assemblies
(`Siemens.Engineering.*`) or NuGet packages. It only reads export files from
disk, so no Siemens license terms apply to this package.

## Recommended compliance checklist

- Keep this `THIRD_PARTY_NOTICES.md` file in source and packaged artifacts.
- Preserve the project `LICENSE.md` file.
- Do not remove third-party copyright/license notices from redistributed artifacts.
- Re-run dependency license checks before each release (`npm`) because dependency graphs can change — including the packages esbuild bundles into `out/extension.js` (build with `--metafile` to list them).

## Audit basis (current snapshot, 2026-10-05)

- Node dependencies from `package.json`, installed `node_modules` metadata and
  the esbuild metafile of the extension bundle.
- .NET dependencies from `dotnet/TiaViewer/TiaViewer.csproj`.
- Public npm/NuGet package pages for license details where exposed.

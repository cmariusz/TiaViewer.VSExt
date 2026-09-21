# Third-Party Notices

This project includes third-party components. Redistribution of this extension should preserve the applicable third-party license notices and terms.

> Informational notice: this file is a practical compliance aid and not legal advice.

## Project License

- Version 2.0.0 and later of this extension are proprietary commercial software
  licensed under the End User License Agreement (see `LICENSE.md`). Versions
  1.1.104 and earlier were licensed under MIT (reproduced in section 20 of
  `LICENSE.md`).

## Runtime dependencies (Node.js, packaged in the VSIX)

- `electron-edge-js` (43.0.0) — MIT
- `edge-js` (25.0.1) — MIT
- `edge-cs` (1.3.7) — MIT
- Transitive:
  - `nan` (2.28.0) — MIT (build-time only, not packaged)

## .NET viewer library

- `dotnet/TiaViewer` — intentionally **zero-dependency** (no NuGet packages);
  targets `net48` + `netstandard2.0` and references only the .NET Framework
  platform assembly `System.IO.Compression` (for reading xlsx tag tables).
  No third-party .NET binaries are redistributed.

## Vendored web assets (embedded in the viewer library)

- `uPlot` (1.6.32) — MIT, https://github.com/leeoniya/uPlot
  (`dotnet/TiaViewer/Assets/uplot.min.js` / `uplot.min.css`; vendored
  unmodified, used by the online trend chart page of the PLC web preview).
  Copyright (c) 2022 Leon Sorokin. The MIT license text is available at
  https://github.com/leeoniya/uPlot/blob/master/LICENSE.

## No Siemens components

Unlike the companion TIA Portal Import extension, this viewer does **not**
use, reference or redistribute any Siemens TIA Portal Openness assemblies
(`Siemens.Engineering.*`) or NuGet packages. It only reads export files from
disk, so no Siemens license terms apply to this package.

## Recommended compliance checklist

- Keep this `THIRD_PARTY_NOTICES.md` file in source and packaged artifacts.
- Preserve the project `LICENSE.md` file.
- Do not remove third-party copyright/license notices from redistributed artifacts.
- Re-run dependency license checks before each release (`npm`) because dependency graphs can change.

## Audit basis (current snapshot)

- Node dependencies from `package.json` and installed `node_modules` metadata.
- .NET dependencies from `dotnet/TiaViewer/TiaViewer.csproj`.
- Public npm/NuGet package pages for license details where exposed.

# Security Policy

**Product:** CMsoft Viewer for TiaPortal (formerly TIA Viewer) — Visual Studio Code extension (`MariuszCzyrnek.tia-viewer`)
**Manufacturer:** Mariusz Czyrnek CM-SOFT, trading as CMsoft, Kornatka 23, 32-410 Dobczyce, Poland, VAT-ID: PL 894-253-07-59
**Version:** 1.2 — 2026-10-12

This policy describes how CMsoft handles security vulnerabilities in the
Software, in line with the vulnerability-handling requirements of Regulation
(EU) 2024/2847 (Cyber Resilience Act).

---

## 1. Reporting a vulnerability

Send reports **confidentially** by e-mail to `office@cmsoft.com.pl` with the
subject starting with `[SECURITY]`. Please **do not** open a public issue for
security problems.

A useful report contains:

- the affected extension version and VS Code / Windows versions;
- a description of the problem and its possible impact;
- steps to reproduce or a proof of concept;
- whether you are aware of the vulnerability being actively exploited;
- how you would like to be credited (or that you prefer to stay anonymous).

Do not include real customer projects, PLC programs or credentials in the
report — a minimal reproduction is enough.

## 2. What happens next

| Step                                                             | Target                                                              |
| ---------------------------------------------------------------- | ------------------------------------------------------------------- |
| Acknowledgement of receipt                                       | within **5 business days**                                    |
| Initial assessment (confirmed / not reproducible / out of scope) | within **15 business days**                                   |
| Fix for a confirmed vulnerability                                | as soon as possible, normally within **90 days** of the report |

If a fix depends on a third party (for example Siemens, Microsoft or an
open-source component) or is unusually complex, we agree an extended timeline
with the reporter. We keep the reporter informed about progress.

Where the Cyber Resilience Act requires it, we notify actively exploited
vulnerabilities and severe incidents to the competent CSIRT and ENISA within
the statutory deadlines, and inform affected users.

## 3. Disclosure

After a fix is available — or when the agreed period ends — we publish a
security advisory in the [`CHANGELOG.md`](CHANGELOG.md) and on the project's
issue tracker [https://github.com/cmariusz/TiaViewer.VSExt](https://github.com/cmariusz/TiaViewer.VSExt). The advisory
names the affected versions, the fixed version, a short description of the
issue and, where applicable, a CVE identifier, which we request ourselves.
Reporters are credited unless they ask otherwise.

We ask reporters not to disclose details publicly before the advisory is
published.

## 4. Supported versions

| Version                                           | Security updates                          |
| ------------------------------------------------- | ----------------------------------------- |
| Latest released version                           | Yes                                       |
| Any older version (including 1.1.104 and earlier) | No — please update to the latest version |

**Support period:** security vulnerabilities are handled until at least
**September 2031** (5 years from the release of version 2.0.0), or longer where
required by law. An extension of the support period is announced in this file.

Vulnerabilities are fixed **only in the latest released version**, as permitted
by Article 13(10) of the Cyber Resilience Act. Updating to the latest version is
free of charge for every user, including users of the Free Features only, and an
active license remains valid after the update. Updates are delivered through the
Visual Studio Marketplace and the Open VSX Registry.

## 5. Scope

In scope:

- the extension code and the bundled .NET viewer library (`TiaViewer.dll`);
- the PLC online features (web-server session handling, HTTPS/certificate
  guidance, the Accessible/Writable attribute checks before reads and writes);
- the language model tools (`tia_viewer_plc_sessions`, `tia_viewer_plc_read`,
  `tia_viewer_plc_write`, `tia_viewer_trend_data`), including the per-write
  confirmation and the `tiaViewer.lmTools.autoConfirmPlcWrites` safeguard;
- the built-in MCP server (`127.0.0.1` binding, per-session Bearer token
  handling, request authentication, the `/health` and `/mcp` endpoints);
- handling of License Keys and PLC credentials by the extension
  (Visual Studio Code SecretStorage);
- the generated webview and standalone HTML output (script injection, CSP).

Out of scope (please report to the respective vendor):

- TIA Portal, the SIMATIC S7 web server and other Siemens products;
- Visual Studio Code, GitHub Copilot and other AI Assistants or MCP clients;
- vulnerabilities that require an attacker who already controls your Windows
  user account.

## 6. Good-faith research

We will not take legal action against anyone who, in good faith, researches and
reports a vulnerability in accordance with this policy, provided they do not
access or modify other people's data, do not disrupt production systems or
PLCs, and give us reasonable time to fix the issue before disclosure.

## 7. Contact

`office@cmsoft.com.pl` — subject prefix `[SECURITY]`

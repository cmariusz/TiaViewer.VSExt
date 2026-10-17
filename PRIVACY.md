# Privacy Policy

**Product:** CMsoft Viewer for TiaPortal (formerly TIA Viewer) — Visual Studio Code extension (`MariuszCzyrnek.tia-viewer`)
**Controller:** Mariusz Czyrnek CM-SOFT, trading as CMsoft, Kornatka 23, 32-410 Dobczyce, Poland, VAT-ID: PL 894-253-07-59 — `office@cmsoft.com.pl`
**Version:** 1.4 — 2026-10-12 (applies to extension version 2.0.0 and later)

---

## 1. Summary

| Question                                                                            | Answer                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Does the extension collect telemetry or usage analytics?                            | **No.**                                                                                                                                                                                                                                                                                                                                     |
| Does it send your project files, PLC programs, tags or source code to the Licensor? | **No.** The extension itself keeps everything on your machine.                                                                                                                                                                                                                                                                              |
| Can project or PLC data reach an AI provider?                                       | **Yes, if you use an AI Assistant** (for example GitHub Copilot or another MCP client) with the extension's language model tools or the built-in MCP server. The assistant receives the results of the tools it calls and forwards them to its model provider — see Section 2a.                                                                                                             |
| Does it phone home on start-up?                                                     | **Not for Free Features.** The extension contacts the license server at start-up only when a license stored on the computer is close to or past its end date (renewal check) or when a purchase started in the license panel has not reached the computer yet (Section 3). The license panel — which opens by itself on the first start of a new major version and, at most once a day, when a license is about to expire or has expired — loads the current plans from the license server; this request carries no personal data. |
| What leaves your machine?                                                           | Only what you submit when you start a trial, buy, activate, refresh or cancel a license (Section 3), the license checks described in Section 3, connections to your own PLC when you go online (Section 2), data forwarded by AI Assistants you use (Section 2a), and requests the Visual Studio Code Marketplace / Open VSX make to deliver updates (Section 5). |

## 2. Data processed locally only

The extension reads export files inside your workspace (SimaticML `.xml`,
`.s7dcl`, `.db`, `.scl`, `.udt`, `.s7res`), renders previews, generates HTML
files you explicitly request, and writes diagnostic messages to the *CMsoft Viewer for TiaPortal*
output channel. This processing happens **entirely on your computer**. The
Licensor has no access to it.

When you press **Go online** in a preview, the extension connects over HTTP(S)
directly from your machine to the web server of the SIMATIC S7 CPU at the
address you provide, using the credentials you enter. PLC credentials are stored
in Visual Studio Code SecretStorage (and, in browser-based web previews, kept in
memory only) and are never sent anywhere except to that PLC. No online values,
tag names or project data are transmitted to the Licensor.

## 2a. Data forwarded by AI Assistants you use

When an AI Assistant (for example GitHub Copilot) calls the extension's
language model tools (`tia_viewer_plc_sessions`, `tia_viewer_plc_read`,
`tia_viewer_plc_write`, `tia_viewer_trend_data`), it receives their results —
for example the hosts of your online PLC sessions, tag and block names, online
variable values and trend recordings. The AI Assistant usually sends this
content, together with your prompts, to its model provider (for example
Microsoft/GitHub, Anthropic, OpenAI, Google, or a local model you run
yourself).

The same tools are exposed by the built-in MCP server
(`tiaViewer.mcp.enabled`, enabled by default — set it to `false` if you do not
use it). The server listens on `127.0.0.1` only and requires a per-session
Bearer token stored in `.tia/mcp-viewer.json`; it is not reachable from
outside your machine. Local programs you connect to it (for example Claude
Desktop or other MCP clients and agents) receive the same tool results; what
those programs do with the data is governed by their own terms, not by the
Licensor.

- This transfer is performed by the AI Assistant, under the provider's terms
  and privacy policy. The Licensor does not receive, see or store this data and
  is neither controller nor processor for it.
- You decide whether an AI Assistant may access your workspace and your online
  PLC sessions. Check your confidentiality obligations and your customer's
  requirements before doing so, in particular for projects containing personal
  data or know-how of third parties.
- PLC credentials are stored in Visual Studio Code SecretStorage and are never
  passed to the AI Assistant — the tools reuse the online session without
  exposing the credentials.

The extension does not send automatic error reports. Diagnostic logs leave your
machine only if you attach them yourself, for example to a support e-mail or an
issue.

## 3. Data processed for trials and licenses

Free Features need no license and send nothing to the Licensor. A trial, a
purchase, the activation, refresh or cancellation of a license happen only
when you request them in the license panel or with a license command; the
panel asks for your consent before an order. The following data may then be
transmitted to the Licensor (its license server) or to the payment provider
acting as merchant of record:

| Data | Purpose | Legal basis (GDPR) |
| --- | --- | --- |
| E-mail address you enter | Issuing and delivering the license key, license support | Art. 6(1)(b) — performance of a contract |
| Company name and country you enter in the order form (your name instead of a company if you buy as a consumer) | Identifying the licensee on the license (the company also appears in the license key), license administration and support | Art. 6(1)(b) — performance of a contract |
| Billing data | Invoicing, tax obligations | Art. 6(1)(b) and 6(1)(c) |
| Derived hardware identifier and the four one-way hashes of machine characteristics it is computed from (never the raw serial numbers) | Binding each license to the one workstation it covers, preventing abuse | Art. 6(1)(b) and 6(1)(f) — legitimate interest in protecting against unlicensed use |
| Product name, extension version, operating-system version | Issuing a compatible key, technical support | Art. 6(1)(b) |
| Version of the license terms you accepted and the time of acceptance | Proof that the license terms were accepted before the license was issued | Art. 6(1)(b) and 6(1)(f) — legitimate interest in documenting the contract |
| License status, activation and deactivation events | Seat management, revocation | Art. 6(1)(b) |
| E-mail address and hardware identifier sent when the extension fetches a license bought for this computer — *Refresh license status*, and a purchase whose license panel was closed before the payment was confirmed (checked at start-up and when the panel opens, for at most 7 days) | Delivering the purchased license to the computer it was bought for: it is handed out only to a computer holding a seat of the license and only for an e-mail address the license belongs to; recording that the key reached the extension | Art. 6(1)(b) |
| License key (license identifier, e-mail address, company, hardware identifier, validity) sent for renewal checks — within 7 days before the end of the license and after it, when the license panel opens, on *Refresh license status*, once after you enter a key — and when you cancel a subscription | Delivering renewed keys, showing the plan and renewal status, cancelling the subscription at your request, removing revoked licenses from the computer | Art. 6(1)(b) and 6(1)(f) |
| For a free trial: the hardware identifier and the e-mail address | Granting one trial per product, computer and e-mail address | Art. 6(1)(f) — legitimate interest in preventing repeated trials |

*Order by e-mail* opens a message in your own e-mail program, addressed to the
Licensor, with your e-mail address, company, country, hardware identifier,
extension version and the activation token; it is transmitted only if you send
it. *Copy HWID* and **Generate Activation Token** only copy the token to the
clipboard.

**No project content is ever transmitted** — no block sources, tag tables, device
names, project names, PLC online values or file contents.

## 4. Retention

- Order and invoicing data: for the period required by tax and accounting law
  (in Poland, 5 years from the end of the tax year).
- Activation and license records (e-mail, company, country, hardware identifier
  hash, license status, when the license key reached the extension): for the
  duration of the license plus 12 months, for renewal and dispute handling.
- On your computer, a purchase started in the license panel is noted (e-mail
  address, start time) until its license arrives, for at most 7 days.
- Support correspondence: up to 24 months from the last message.

## 5. Recipients and third parties

- **Payment provider / merchant of record** — processes your payment and billing
  data as an independent controller or processor under its own privacy policy;
  identified on the purchase page.
- **Microsoft Corporation (Visual Studio Marketplace)** and **Eclipse Foundation
  AISBL (Open VSX Registry)** — distribute the extension package and process
  download/update requests under their own privacy policies. The Licensor
  receives only aggregated, anonymous install and rating statistics from them.
- **E-mail provider** — used to deliver license keys and support replies.

The current list of service providers that process personal data on the
Licensor's behalf (for example hosting of the license service, e-mail delivery)
is published on the product purchase page and is available on request.
Business Customers are informed by e-mail at least 30 days before a new
processor is added; if they raise a justified objection that cannot be
resolved, they may terminate the affected subscription with a pro-rata refund.

**Data processing agreement.** Where the Licensor processes personal data on
behalf of a Business Customer (for example the names and e-mail addresses of
users to whom the customer assigns licenses), it does so as a processor under
Article 28 GDPR, only for license administration. A data processing agreement
with the content required by Article 28(3) GDPR is available on request at
`office@cmsoft.com.pl`.

The Licensor does not sell personal data and does not use it for advertising or
profiling.

## 6. International transfers

Data is processed within the European Economic Area wherever possible. If a
processor operates outside the EEA, transfers are based on the European
Commission's Standard Contractual Clauses or an adequacy decision.

## 7. Your rights

You have the right to access, rectify, erase and port your data, to restrict or
object to processing, and to lodge a complaint with a supervisory authority (in
Poland: Prezes Urzędu Ochrony Danych Osobowych, ul. Stawki 2, 00-193 Warszawa).
To exercise any of these rights, write to `office@cmsoft.com.pl`.

Erasing your activation record will deactivate the corresponding license key.

On request, sent from the e-mail address registered with your license, you
receive a copy of your account and license data in a structured,
machine-readable format (JSON) within one month (Articles 15 and 20 GDPR).
Erasure does not cover data that must be retained under tax and accounting law
(Section 4).

## 8. Security

License data is stored encrypted at rest on the Licensor's side. On your
machine, the license key is stored using Visual Studio Code SecretStorage and
the Windows Data Protection API (DPAPI); it is not written to `settings.json`
and is not included in Settings Sync. The extension also keeps, in Visual
Studio Code's local extension storage (not included in Settings Sync), the
history of your acceptances of the license terms, the last renewal status of
each license and, until its license arrives, the e-mail address of a purchase
in progress. PLC credentials are kept in SecretStorage and are never written
to plain-text settings or workspace files.
The MCP server token in `.tia/mcp-viewer.json` is regenerated on every
extension start and deleted when the server stops.

How to report a security vulnerability is described in
[`SECURITY.md`](SECURITY.md).

## 9. Children

The Software is a professional engineering tool and is not directed at persons
under 16 years of age.

## 10. Changes

This policy may be updated for future versions of the Software. The version and
date at the top of this document indicate the applicable revision. Material
changes will be announced in the [`CHANGELOG.md`](CHANGELOG.md).

## 11. Contact

**Mariusz Czyrnek CM-SOFT**
Kornatka 23, 32-410 Dobczyce, Poland
VAT-ID: PL 894-253-07-59
E-mail: `office@cmsoft.com.pl`
Web: [https://shop.cmsoft.com.pl](https://shop.cmsoft.com.pl)

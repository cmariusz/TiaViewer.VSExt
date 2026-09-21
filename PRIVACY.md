# Privacy Policy

**Product:** TIA Viewer — Visual Studio Code extension
**Controller:** CmSoft, Kornatka 23, 32-410 Dobczyce, Poland, NIP PL 894-253-07-59 — `office@cmsoft.com.pl`
**Version:** 1.0 — 2026-09-21 (applies to extension version 2.0.0 and later)

---

## 1. Summary

| Question                                                                     | Answer                                                                                                                                                                                                                               |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Does the extension collect telemetry or usage analytics?                     | **No.**                                                                                                                                                                                                                        |
| Does it send your project files, PLC programs, tags or source code anywhere? | **No.** Everything stays on your machine.                                                                                                                                                                                      |
| Does it phone home on start-up?                                              | **No.**                                                                                                                                                                                                                        |
| What leaves your machine?                                                    | Only what you explicitly submit when activating a paid plan (Section 3), connections to your own PLC when you go online (Section 2), and requests the Visual Studio Code Marketplace / Open VSX make to deliver updates (Section 5). |

## 2. Data processed locally only

The extension reads export files inside your workspace (SimaticML `.xml`,
`.s7dcl`, `.db`, `.scl`, `.udt`, `.s7res`), renders previews, generates HTML
files you explicitly request, and writes diagnostic messages to the *TIA Viewer*
output channel. This processing happens **entirely on your computer**. The
Licensor has no access to it.

When you press **Go online** in a preview, the extension connects over HTTP(S)
directly from your machine to the web server of the SIMATIC S7 CPU at the
address you provide, using the credentials you enter. PLC credentials are stored
in Visual Studio Code SecretStorage and are never sent anywhere except to that
PLC. No online values, tag names or project data are transmitted to the
Licensor.

## 3. Data processed when you activate a paid plan

Activation is **optional** and only happens when you explicitly request it. When
you do, the following data may be transmitted to the Licensor or to the payment
provider acting as merchant of record:

| Data                                                                                                    | Purpose                                                                | Legal basis (GDPR)                                                                   |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| E-mail address you enter                                                                                | Issuing and delivering the license key, license support                | Art. 6(1)(b) — performance of a contract                                            |
| Company / billing data                                                                                  | Invoicing, tax obligations                                             | Art. 6(1)(b) and 6(1)(c)                                                             |
| Derived hardware identifier (a one-way hash of machine characteristics — never the raw serial numbers) | Binding the license to the purchased number of seats, preventing abuse | Art. 6(1)(b) and 6(1)(f) — legitimate interest in protecting against unlicensed use |
| Product name, extension version, operating-system version                                               | Issuing a compatible key, technical support                            | Art. 6(1)(b)                                                                         |
| License status, activation and deactivation events                                                      | Seat management, revocation                                            | Art. 6(1)(b)                                                                         |

**No project content is ever transmitted** — no block sources, tag tables, device
names, project names, PLC online values or file contents.

## 4. Retention

- Order and invoicing data: for the period required by tax and accounting law
  (in Poland, 5 years from the end of the tax year).
- Activation records (e-mail, hardware identifier hash, license status): for the
  duration of the license plus 12 months, for renewal and dispute handling.
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

## 8. Security

License data is stored encrypted at rest on the Licensor's side. On your
machine, the license key is stored using Visual Studio Code SecretStorage and
the Windows Data Protection API (DPAPI); it is not written to `settings.json`
and is not included in Settings Sync.

## 9. Children

The Software is a professional engineering tool and is not directed at persons
under 16 years of age.

## 10. Changes

This policy may be updated for future versions of the Software. The version and
date at the top of this document indicate the applicable revision. Material
changes will be announced in the [`CHANGELOG.md`](CHANGELOG.md).

## 11. Contact

**CmSoft**
Kornatka 23, 32-410 Dobczyce, Poland
E-mail: `office@cmsoft.com.pl`
Web: [https://www.cmsoft.com.pl](https://www.cmsoft.com.pl)

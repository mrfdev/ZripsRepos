# TradeMe README evidence review

- **Status:** local proposal; not submitted upstream
- **Reviewed:** 2026-08-07
- **Upstream repository:** `Zrips/TradeMe`
- **Upstream commit:** `1b1634ccf79c691829cc3b7f1cff1de202a0254c`
- **Proposal:** [`proposals/README.md`](proposals/README.md)

## Claim-to-source review

| Claim group | Evidence | Result |
|---|---|---|
| Repository role | The default branch contains only `.gitignore` and the one-line `README.md`; GitHub Issues contains current bug and feature reports, including issue #34 from 2026 | Verified as the repository's current observed use |
| Paid plugin and maintainer | The official SpigotMC resource/discussion identifies TradeMe as a paid resource submitted by Zrips | Verified |
| GUI player trading | Zrips' original resource description calls it a player trading plugin and the official discussion and current issue reports describe its inventory trading GUI | Verified |
| Items, money, and experience | Zrips' original resource description explicitly lists these trade types | Verified |
| Integrations and custom API | Maintainer-authored update posts document optional trade modes such as Residence and PlayerPoints; the official resource title advertises an API for custom trades | Verified without presenting an exhaustive integration list |
| CMILib requirement | The official CMILib resource lists TradeMe as using CMILib since TradeMe 6.1.0.0; the TradeMe 6.1.0.0 update announced the dependency | Verified |
| Download, documentation, and support links | The official resource is SpigotMC resource `7544`; GitHub Issues is enabled and actively used; `zrips.net` is the maintainer's site | Verified |
| Installation | Standard server `plugins` directory installation is consistent with the official CMILib instructions and TradeMe dependency behavior | Verified at documentation level; not runtime-tested |

## Accuracy decisions

- The proposal does not copy a command, permission, placeholder, or exhaustive integration list because the repository has no public source or plugin metadata from which to verify current details.
- It does not state a fixed supported-version range. That range has changed over time and belongs on the maintained resource page.
- It describes the repository as *currently serving* as an issue tracker rather than claiming that Zrips formally designated its permanent role.
- It states that no source, download, or build files are present instead of implying that this paid plugin is open source or buildable from GitHub.
- Security-sensitive reports are directed to private official support before public reproduction details, consistent with the repository hub's disclosure policy.

## Known limitations

- The paid TradeMe jar was not downloaded or inspected, so runtime behavior, current commands, permissions, embedded metadata, and the full integration matrix were not independently verified.
- SpigotMC currently requires a logged-in account to open resource `7544` directly. Maintainer-authored public discussion pages and the official CMILib resource were used for the factual review.
- No build or runtime test is possible from this repository because it contains no source or build definition.

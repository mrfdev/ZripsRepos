# BottledExp README evidence review

- **Status:** passed for proposal
- **Reviewed:** 2026-08-07
- **Upstream repository:** `Zrips/BottledExp`
- **Upstream commit:** `7205230745a68de1ef3897f5fe0a1f9d9d68fe0d`
- **Proposal:** [`proposals/README.md`](proposals/README.md)

## Claim-to-source review

| Claim group | Evidence | Result |
|---|---|---|
| Purpose and XP-bottle conversion | `src/plugin.yml`, `Util.giveBoottles`, and the SpigotMC resource description | Verified |
| Stored/custom bottles | `BottledExpCommands.store`, `Util.giveStoredBottle`, `StoredBottledExp` NBT, generated name and lore | Verified |
| XP statistics and level estimate | `BottledExpCommands.stats` and `BottledExpCommands.until` | Verified |
| Player XP transfer and configurable loss | `BottledExpCommands.give` and `bottle.give.LostDurringTransfer` | Verified |
| Block interactions, item costs, economy costs, and recipes | `BlockInteractionEvent`, `ConfigFile`, `Util`, `Recipes`, and `recipes.yml` | Verified |
| Sacnoth0 origin credit | Maintainer-authored SpigotMC resource description and linked historical Bukkit page | Verified as maintainer statement |
| CMILib requirement | Hard `depend: [CMILib]` in `src/plugin.yml` and SpigotMC resource description | Verified |
| Optional Vault economy integration | `softdepend`, economy service setup, and guarded money configuration/withdrawal paths | Verified |
| Commands and arguments | All eight public methods in `BottledExpCommands`; optional `consume` amount confirmed by parser behavior | Verified from public source |
| Permission naming and groups | Dynamic `bottledexp.command.<subcommand>` check, `src/plugin.yml`, command-specific checks, interaction events, crafting, and version checker | Verified from public source |
| PlaceholderAPI status | No PlaceholderAPI dependency, registration, import, or expansion in the public source; bracket tokens are replaced internally | Verified for public source only |
| Build instructions | Eclipse `src/` layout, `.classpath` dependencies, resources under `src/`, legacy NMS adapters, and absence of Maven/Gradle files | Verified structurally; build not executed |
| Support and downloads | Enabled GitHub Issues and official SpigotMC download page | Verified |

## Corrections made during factual review

- Made the `/bottle consume` amount optional and documented its one-bottle default.
- Described wildcard permission groups by their actual declared child lists instead of assuming their names cover every command.
- Scoped the PlaceholderAPI statement to public source because separately published binary behavior was not inspected.

## Known limitations

- A clean build and runtime test were not performed because the repository has no portable build configuration and references local/legacy dependency jars.
- Public `src/plugin.yml` declares `3.2.3.2`, while SpigotMC distributes `3.2.4.0`. This does not prove code drift; the proposal makes no source/binary equivalence claim, and Floris will ask the maintainer separately.
- Minecraft versions shown on SpigotMC are maintainer-published compatibility claims and were not independently tested in this README review.

# Can a block logger tell Rewild what players built before it was installed?

Checked 2026-11-14 for K599, against a copy of the server taken just before its move to Paper 26.3. Nothing on the live server was read.

**Prism: no.** It went in on 2026-11-14, the same day Rewild started its dry run, so it has nothing older than Rewild's own record.

**CoreProtect: very little.** Its database on that copy covers 2026-11-07 23:24 to 2026-11-10 10:37:
- 317 block placements, by 3 players in 2 worlds;
- 91 removals and 1 other action.

The worlds are older than that, so most of what players built before Rewild isn't in any logger.

**What Rewild does instead stays the safe choice.** A chunk born before Rewild tracked it is unknown, and an unknown chunk never rewilds. A logger import couldn't change that, because it would still miss everything before 2026-11-07.

**Not built.** An importer for those 317 placements would cost more than it gives. If a world ever needs it, CoreProtect's `co_block` rows with `action = 1` hold the world, the position and the player for each placement.

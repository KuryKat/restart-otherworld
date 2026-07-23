# [Otherworld](https://otherworld.wiki/) Minecraft Server: Restart Automation

This simple, yet complete and comprehensive, GitHub Action keeps my modded Minecraft server ([**Otherworld D&D**](https://www.curseforge.com/minecraft/modpacks/otherworld-dnd), hosted on a Pterodactyl panel in a friend's dedicated server) restarting on schedule. Pterodactyl Schedules broke in his server, and the "Auto Restart" mod couldn't relaunch itself inside a Docker container no matter what I tried, so this repo does it instead, straight through the [Pterodactyl Client API](https://pterodactyl-api-docs.netvpx.com/docs/api/client/servers#send-console-command), on a cron with in-game warnings before each restart.

**Restart times (UTC):** `00:00`, `06:00`, `12:00`, `18:00`

_Expected last restart: 2026-07-23 18:00 UTC_

_Actual last restart: 2026-07-23 18:00 UTC (drift: +0m)_

Disclaimer: GitHub's own scheduled triggers can drift by 60-90+ minutes under load (see commit history for how bad this got), so this workflow no longer relies on `schedule:` to start the clock. A Cloudflare Worker using a Cron Trigger to a `scheduled()` event handler calls GitHub's `workflow_dispatch` API at the exact intended time instead, which starts almost instantly since it isn't sitting in the same deprioritized queue as scheduled runs.

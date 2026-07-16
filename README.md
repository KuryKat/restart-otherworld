# [Otherworld](https://otherworld.wiki/) Minecraft Server: Restart Automation

This simple, yet complete and comprehensive, GitHub Action keeps my modded Minecraft server ([**Otherworld D&D**](https://www.curseforge.com/minecraft/modpacks/otherworld-dnd), hosted on a Pterodactyl panel in a friend's dedicated server) restarting on schedule. Pterodactyl Schedules broke in his server, and the "Auto Restart" mod couldn't relaunch itself inside a Docker container no matter what I tried, so this repo does it instead, straight through the [Pterodactyl Client API](https://pterodactyl-api-docs.netvpx.com/docs/api/client/servers#send-console-command), on a cron with in-game warnings before each restart.

**Restart times (UTC):** `00:00`, `06:00`, `12:00`, `18:00`

_Expected last restart: 2026-07-16 18:00 UTC_ (manually triggered test run, not real numbers)

_Actual last restart: 2026-07-16 19:56 UTC (drift: +116m)_ (manually triggered test run, not real numbers)

Disclaimer: Times are not precise given GitHub's limitations on scheduled tasks, a different approach might be required soon if it proves unbearable.

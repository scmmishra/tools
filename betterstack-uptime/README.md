# Better Stack Uptime Support Tools

Read-only tools for checking uptime monitors and active incidents in Better Stack during support conversations.

## Included tools

- **List Better Stack Monitors** (`list_betterstack_monitors`) — lists monitors and their current states.
- **Get Better Stack Monitor** (`get_betterstack_monitor`) — retrieves one monitor by its Better Stack identifier.
- **List Active Better Stack Incidents** (`list_active_betterstack_incidents`) — lists incidents filtered to `resolved=false`.
- **Get Better Stack Incident** (`get_betterstack_incident`) — retrieves one incident and its diagnostic details.

## Requirements

- A Better Stack API token with access to the Uptime team and resources Captain needs to read.

The tools work with team-scoped Uptime API tokens or global API tokens. A global token can span teams, so prefer a team-scoped token when possible.

## Setup

1. Create or select a Better Stack API token with access to the required Uptime resources.
2. Import `toolset.yml` into Captain.
3. Enter the API token when prompted.
4. Review and enable the imported tools.

The tools send the token using Better Stack's documented `Authorization: Bearer <TOKEN>` header. They do not acknowledge, resolve, create, or modify incidents and monitors.

## References

- [List monitors](https://betterstack.com/docs/uptime/api/list-all-existing-monitors/)
- [Get a monitor](https://betterstack.com/docs/uptime/api/get-a-single-monitor/)
- [List incidents](https://betterstack.com/docs/uptime/api/list-all-incidents/)
- [Get an incident](https://betterstack.com/docs/uptime/api/list-a-single-incident/)
- [Better Stack API tokens](https://betterstack.com/docs/uptime/api/getting-started-with-uptime-api/)

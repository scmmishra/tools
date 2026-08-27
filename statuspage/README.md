# Statuspage Support Tools

Read-only tools for checking incidents and component health on an Atlassian Statuspage during support conversations.

## Included tools

- **List Statuspage Incidents** (`list_statuspage_incidents`) — lists incidents for the configured page.
- **Get Statuspage Incident** (`get_statuspage_incident`) — retrieves one incident by its Statuspage identifier.
- **List Statuspage Components** (`list_statuspage_components`) — lists page components and their current operational states.

## Requirements

- The page ID shown under **API info** in Statuspage.
- A current organization-level Statuspage API key.

Statuspage API keys can access management operations beyond the read-only requests in this toolset. Store the key securely, rotate it before expiry, and only enable tools you trust.

## Setup

1. Ask a Statuspage account owner to create an API key under **API info**.
2. Copy the target page ID from **API info**.
3. Import `toolset.yml` into Captain.
4. Enter the page ID and API key when prompted.
5. Review and enable the imported tools.

The tools send the key using Statuspage's documented `Authorization: OAuth <API_KEY>` header. They do not use the deprecated `api_key` query parameter.

## References

- [Statuspage API](https://developer.statuspage.io/)
- [Create and manage Statuspage API keys](https://support.atlassian.com/statuspage/docs/create-and-manage-api-keys/)
- [Statuspage components](https://support.atlassian.com/statuspage/docs/show-service-status-with-components/)

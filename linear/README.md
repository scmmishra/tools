# Linear Support Tools

Read-only Linear tools for retrieving issue details during support conversations. The tools use Linear's public GraphQL API.

## Included tools

- **Get Linear Issue** — retrieves an issue by its shorthand identifier or UUID.
- **List Recent Linear Issues** — returns the ten most recently updated issues visible to the API-key owner.

## Requirements

- A Linear personal API key.
- Access to the Linear workspaces and issues the assistant needs to read.

## Setup

1. Open Linear's Security & access settings and create a personal API key.
2. Import `toolset.yml` into Captain.
3. Enter the API key when prompted.
4. Review and enable the imported tools.

The issue lookup accepts shorthand identifiers such as `ENG-123` and Linear issue UUIDs. The API key is sent in Linear's documented raw `Authorization` header; it is not prefixed with `Bearer`.

## Permissions and data

These tools only execute GraphQL queries and do not contain mutations. Their responses can include issue descriptions, assignee names, workflow states, and other workspace data visible to the API-key owner. Create the key from a Linear account with only the access the support workflow requires.

## References

- [Linear GraphQL API and authentication](https://linear.app/developers/graphql)
- [Linear pagination and ordering](https://linear.app/developers/pagination)

# Mizaniya Pay docs

Two Mintlify sites in one repository:

| Folder | Site | Audience | Reference |
|---|---|---|---|
| `partner/` | Partner API | Public | `openapi/partner.json`: the `/external/v1` routes |
| `internal/` | Internal docs | Team only (protected) | `openapi/pos.json` and `openapi/admin.json`: both backends |

The `openapi/` files are generated from the backends by `npm run openapi:export` and arrive through sync PRs. Don't edit them by hand.

## Preview locally

You need Node 22 (`nvm use`). The Mintlify CLI supports Node 20.17 or later, except Node 25.

```bash
npm i -g mint@4.3.34
```

Run each site in its own terminal, from the repository root:

```bash
(cd partner  && mint dev)               # http://localhost:3000
(cd internal && mint dev --port 3001)   # http://localhost:3001
```

Before opening a PR, run these in the site folder: `mint format`, `mint validate`, `mint broken-links`, `mint a11y`.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the workflow and writing rules.

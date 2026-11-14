# Contributing to the Mizaniya Pay docs

## Workflow

1. One branch per page or group of pages: `docs/<topic>`, for example `docs/partner-quickstart`.
2. Write and preview locally with `mint dev` (see [README.md](README.md)).
3. Open a PR to `main` with a screenshot of the preview, and get a review from another team member.
4. When a route changes in a backend, its author updates the guide in a `docs/<topic>` PR that references the sync PR.
   Never push commits to a sync branch (`chore/sync-openapi-pos`, `chore/sync-openapi-admin`): the next sync resets it and the commits are lost.

Merging to `main` publishes both sites.

## Writing rules

- **Language:** the partner site is in English. The internal site uses one language across the whole site, as agreed by the team.
- **`openapi/` files:** never edit them by hand. They are generated from the backends. Fix the decorators in the backend instead.
- **Examples:** every example must run, and use fake data only. No real API keys, phone numbers or accounts.
- **Secrets:** the environment variables page lists each variable's name, purpose and an example value only. Never copy `.env` files or credentials.
- **Components:** use Mintlify's components (`Steps`, `CodeGroup`, `Note`, `Warning`) instead of custom HTML.
- **Formatting:** run `mint format` in the site folder before opening a PR.

## Page template

```mdx
---
title: "Gift cards"
description: "List, buy and deliver gift cards through the partner API."
---

<Steps>
  <Step title="List the available cards"> ... </Step>
  <Step title="Place the order"> ... </Step>
</Steps>

<CodeGroup>
  {/* one Node.js and one curl example per request */}
</CodeGroup>
```

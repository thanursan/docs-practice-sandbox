# Widget API Reference (Example)

> This is placeholder documentation for practice purposes only. Edit freely.

## Overview

The Widget API lets you create, retrieve, and delete widgets programmatically. All requests require an API key.

## Authentication

Include your API key in the `Authorization` header of every request:

```bash
curl https://api.example.com/v1/widgets \
  -H "Authorization: Bearer YOUR_API_KEY"
```

> **Note:** Replace `YOUR_API_KEY` with the key found in your account dashboard. Keys are scoped per project.

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/v1/widgets` | List all widgets |
| GET | `/v1/widgets/{id}` | Retrieve a single widget |
| POST | `/v1/widgets` | Create a new widget |
| DELETE | `/v1/widgets/{id}` | Delete a widget |

### Create a widget

**Request**

```bash
curl -X POST https://api.example.com/v1/widgets \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "example-widget",
    "color": "blue",
    "size": "medium"
  }'
```

**Response**

```json
{
  "id": "wdg_001",
  "name": "example-widget",
  "color": "blue",
  "size": "medium",
  "created_at": "2026-07-11T09:00:00Z"
}
```

### Delete a widget

```bash
curl -X DELETE https://api.example.com/v1/widgets/wdg_001 \
  -H "Authorization: Bearer YOUR_API_KEY"
```

Returns a `204 No Content` on success.

## Error handling

| Status code | Meaning |
|---|---|
| 400 | Malformed request body |
| 401 | Missing or invalid API key |
| 404 | Widget not found |
| 429 | Rate limit exceeded |

## Changelog

- [ ] *(Practice task: add a changelog entry here on a new branch, then open a pull request)*

---

### Practice tasks

1. Add a new section called `## Rate Limits` describing a made-up limit (e.g. "100 requests per minute").
2. Fix the intentional inconsistency: the overview says "create, retrieve, and delete" but there's no explicit "retrieve" example — add one for `GET /v1/widgets/{id}`.
3. Convert the error table into a bulleted list, then convert it back — good muscle memory for table syntax.

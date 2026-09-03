# POST /v1/projects/{id}/archive

Request:

```json
{ "reason": "string (1..500)" }
```

Responses:
- `200` archived project payload
- `400` validation error
- `403` forbidden
- `404` not found

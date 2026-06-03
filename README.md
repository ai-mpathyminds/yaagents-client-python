# yaagents-client

Python client for the **YAAgents Agentic REST Profile v0.3**.

Supports-YAAgents-Profile: **v0.3**

## Install

```bash
pip install yaagents-client==0.3.0
```

## Quickstart

```python
from yaagents_client import YaAgentsClient

with YaAgentsClient(
    base_url="https://api.example.com",
    token="<bearer-token>",
    tenant_id="<tenant-id>",
) as client:
    response = client.campaigns("camp-123").optimizations.create(
        {"goal": "ctr", "budget": 1000}
    )
    print(response.status_code, response.json())
```

## Headers

Every request carries:

| Header | Value |
|--------|-------|
| `Authorization` | `Bearer <token>` |
| `X-Tenant-ID` | value passed to constructor |
| `X-Correlation-ID` | auto-generated UUID v4 (overridable per call) |

## Resources

| Accessor | HTTP | Path |
|----------|------|------|
| `campaigns(id).optimizations.create(body)` | POST | `/campaigns/{id}/optimizations` |
| `campaigns(id).assets.generate(body)` | POST | `/campaigns/{id}/assets:generate` |

Source: https://github.com/ai-mpathyminds/yaagents-client-python

Community docs: https://github.com/ai-mpathyminds/yaagents

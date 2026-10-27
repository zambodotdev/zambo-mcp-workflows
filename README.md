# Zambo MCP Workflows

**Practical patterns for moving from an AI request to an observed result through one Zambo MCP connection.**

Connect first: [zambo.dev/mcp](https://zambo.dev/mcp)

```text
https://zambo.dev/api/mcp
```

This repository documents workflow patterns, not a second server and not a frozen catalog. Ask MCP discovery for the current tool names and schemas before adapting an example.

## The common flow

```text
GOAL → DISCOVER → CHECK → APPROVE IF REQUIRED → EXECUTE → INSPECT RECEIPT → RECOVER OR CONTINUE
```

## Copy-this prompts

### Research with evidence

```text
Use Zambo to find the safest live capability for researching this question. Show the sources or artifacts returned by the tool. If the provider is unavailable, say so instead of filling the gap from memory.
```

### Continue an interrupted job

```text
Resume my existing Zambo session. First show what was already completed, what remains, and whether any step requires my approval. Do not repeat successful consequential work.
```

### Plan before acting

```text
Use Zambo to check whether this request can be executed. Return a concrete plan and preview first. Ask for approval before any supported action that changes external state.
```

### Verify what happened

```text
Inspect the Zambo receipt for this job. Separate observed execution from external outcome evidence, and list anything still unknown or requiring human confirmation.
```

## Adapting a workflow

1. Call `tools/list` against the live MCP endpoint.
2. Choose a capability whose schema and side effects match the goal.
3. Preserve the same session/ownership context across check, approval, execution, and verification.
4. Treat preview, approval-required, unavailable, and failed states as non-success.
5. Store artifacts or receipts only where the user expects them to persist.

## Limits

External providers can fail or rate limit requests. Product-specific ownership and quota rules apply. These examples describe safe orchestration patterns; they do not guarantee that every catalog capability is available to every user or client.

---
next step: add zambo to your ai in one url, no key, no account: https://zambo.dev/add/?ref=zambo-mcp-workflows
got a receipt link from someone? check it in seconds: https://zambo.dev/verify/
every call returns a receipt. a receipt proves the saved bytes are unchanged. it does not prove the answer is right.

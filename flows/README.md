# Supporting Power Automate actions (reference)

Reference Workflow Definition Language exports for the two custom actions the topics in [`../topics`](../topics) call into. Both are triggered with the **Power Virtual Agents / Copilot Studio** request trigger, which is what makes them callable from a topic's `InvokeFlowAction` step.

- `identity-lookup-reset.json` — looks up the user in Microsoft Entra ID *before* doing anything, then invalidates sessions and sends a reset email. Returns `identityFound` so the topic can branch to escalation instead of guessing.
- `create-ticket.json` — the generic ticket-logging action every topic (or the escalation path) calls to write a `cr_helpdeskticket` row, per [`../dataverse/ticket-table-schema.json`](../dataverse/ticket-table-schema.json).

As with the other repos in this profile, connection references and table logical names are illustrative — recreate the connections and the Dataverse table in your own environment before importing.

# Topics (reference)

These YAML files mirror Copilot Studio's code/YAML view for a topic's adaptive dialog (Topic → **⋯** → **Edit in code editor**). They're the reference design for the three purpose-built topics described in the main README, each paired with a Power Automate action under [`../flows`](../flows).

| Topic file | Trigger phrases (sample) | Power Automate action | Dataverse outcome |
|---|---|---|---|
| `password-reset.yaml` | "reset my password", "I forgot my password" | `identity-lookup-reset.json` | Resolved, or Open if identity can't be verified |
| `access-request.yaml` | "I need access to an app", "request software access" | (approval-workflow flow, referenced but not duplicated here — see [power-automate-cloud-approval-workflow](https://github.com/Pooraniraju/power-automate-cloud-approval-workflow)) | Pending approval |
| `outage-check.yaml` | "is it just me", "is the system down" | `get-system-status` (status API call) | Resolved, with a ticket only if the system is unhealthy |

Each file has a `referenceInfo` block at the bottom — that's documentation for this repo, not part of the Copilot Studio schema itself; strip it out if you paste the dialog back into an actual agent.

Anything outside these three topics falls through to **generative answers**, grounded on an IT knowledge base (SharePoint/Dataverse source), per the main README.

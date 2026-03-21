---
name: SecretTracker
description: Manage the secrets and clues mechanic across sessions — track learned secrets, spending, NPC sharing, and endgame hoarding. USE WHEN secrets, track secrets, what secrets do we have, spend a secret, secret tracker, clues.
version: 0.1.0
---

# SecretTracker

Manage the campaign's secrets mechanic. Secrets are structural knowledge about the cosmic architecture — they have power as currency, can be spent for tactical advantage, and lose their power when shared with NPCs.

## Instructions

1. If no tracker file exists, create one at `Campaigns/[Campaign]/Secrets Tracker.md` with this structure:

```markdown
# Secrets Tracker

## Learned
- [ ] [Secret description] — Source: [scene/NPC] — Status: kept

## Spent
- [x] [Secret description] — Spent: [when/why] — Effect: advantage on d20 rolls for 1 minute

## Shared (Lost Power)
- [-] [Secret description] — Shared with: [NPC name] — Power lost
```

2. When the user says they learned a new secret, add it to the Learned section with source attribution.

3. When a secret is spent (whispered into the wind, used for tactical advantage), move it to Spent with the context.

4. When a secret is shared with an NPC, move it to Shared — it loses power immediately. The characters still know the information but cannot spend it.

5. Before a major encounter or session finale, report: how many secrets are kept (available for the endgame bonus), how many were spent, how many were shared.

6. The endgame bonus scales with secrets hoarded — more kept secrets = stronger position in the final confrontation. Exact mechanics are GM-determined per campaign.

## Mechanics Reference

**Spending:** Use an action to whisper the secret. Gone from all party members' minds. Every character gains advantage on d20 rolls for 1 minute.

**Sharing:** If characters tell an NPC a secret, it loses power immediately. Still known, but cannot be spent.

**Hoarding:** Kept secrets provide cumulative bonuses in the finale — the GM determines the specific benefit per secret.

## Constraints

- A secret can only be spent once
- Sharing with ANY NPC (even allies) destroys the secret's power
- The party learns secrets together — when one character learns it, all have it
- Track the source of each secret for continuity

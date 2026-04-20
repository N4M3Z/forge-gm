Scene frontmatter uses two status fields:

**`status/` tag** (workflow status): `draft` → `review` → `final`. Tracks the scene through the writing pipeline.

**`status:` field** (lore status): Controls what information the GM treats as settled.

| Value      | Meaning                                      |
| ---------- | -------------------------------------------- |
| `draft`    | Work in progress, subject to change          |
| `canon`    | GM truth, may contain secrets players lack   |
| `revealed` | Players have learned this information        |
| `secret`   | Players must not see this content            |

A scene can be `status/final` (writing is done) while containing entries marked `status: secret` (players haven't discovered them yet).

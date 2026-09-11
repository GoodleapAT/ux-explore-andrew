# Sources, global

**Things that outlive any one project. Project-specific sources are in the project's own sources file.**

> **Who may write to this file:** any surface that can write. One row per source. Edit in place. When
> you use a source, update its **Checked** date. When a source turns out to be unreachable, change its
> **Access** note rather than deleting the row, because knowing something is blocked is worth as much
> as knowing where it is.

**Access column, what the values mean**

| Value | Meaning |
|---|---|
| Local | Present in the enclosing folder. Readable by any surface with file access |
| Connector | Reachable through an MCP connector. May need authorising first |
| Connector, unauthorised | The connector exists but is not connected. Say so rather than working around it |
| Paste only | No surface can fetch it. Andrew has to paste the content in |
| Not located | Believed to exist, not found yet |

---

## Design system

| Source | Kind | Where | Access | Good for | Checked |
|---|---|---|---|---|---|
| **Merlin Design System Workspace** | Figma design file | File `0CTG6nlLdGLoiZ60lo0YNL` | Connector | The system used for Merlin work. Components page at `4:6`, example pages and their organisms at `5300:3768` | 31 Aug 2026 |
| **Project Merlin Dev Handoff** | Figma design file | File `esYZqwjYSqkxvJqPQ0oXZ8` | Connector | Source of truth for mockups delivered to developers, at `13347:39382`. Components not yet brought into the system file at `15107:187496` | 31 Aug 2026 |
| **Merlin shadcn sink** | Deployed page | `app.merlin-v12.com/dev/sink` | Browser, or paste | Most components with correct styling, live | 31 Aug 2026 |
| **Sol tokens and Pros Web utilities** | Stylesheet | `reference/merlin-sol-tokens.css` | Local | 113 Sol tokens, light and dark, extracted verbatim from Merlin's compiled production stylesheet on 24 Aug 2026, plus the Pros Web page utility classes. **Use this rather than inventing a palette** | 10 Sep 2026 |

**Known defect.** The shared token package ships two disagreeing colour palettes, so web and Flutter
diverge silently. Written up in the design-system investigations, which are still loose in the
enclosing folder.

**What the stylesheet does not carry.** Badge variant colours, because the design system bundle ships
them minified. They have been inferred from the accent token families. This does not matter while
`standards/mockup-density.md` forbids badges, but it will matter if that rule is relaxed.

---

## Product repositories

All in `loanpal-engineering` unless noted, all cloned in the enclosing folder, all readable and
editable locally but **not pushable from a session**.

| Repository | What it is | Checked |
|---|---|---|
| **merlin** | Merlin itself. Source of the design tokens, the app shell, the sidebar and the page layout values | 12 Aug 2026 |
| **gl-pros-flutter** | The Pros mobile app. In `loanpal-sawbridge`, not `loanpal-engineering` | 12 Aug 2026 |
| **pay-mfe** | Payments micro-frontend | 10 Aug 2026 |
| **origin-shell** | Origin shell | 10 Aug 2026 |
| **cases-mfe** | Holds the Origin Cases page | 31 Aug 2026 |
| **pipeline-mfe** | Holds both Leases and PPAs pages, under the TPO naming | 31 Aug 2026 |
| **origin-utils-mfe** | Origin utilities | 31 Aug 2026 |
| **react-dede** | DeDe, the assistant that raises suggested work | 31 Aug 2026 |
| **origin-mfe** | The main Origin app, where the two **Loans** financing pages live. **Not located** in the organisation. A message asking Joel's team for it was drafted and never answered | 31 Aug 2026 |

---

## Andrew's own repositories

| Repository | What it is | Access |
|---|---|---|
| **ux-explore-andrew** | This one, in `GoodleapAT`. Private. Working memory, project material, and the standalone prototypes in `prototypes/`. Renamed from `ux-hosted` on 11 Sep 2026 | Local, pushable by Andrew |

---

## Tooling quirks worth not rediscovering

| Tool | What to know |
|---|---|
| **Figma, FigJam boards** | The text extraction tool fails on large board nodes. Read a board as a rendered screenshot instead, at high enough resolution to read the small annotation, because the small annotation is usually where the argument is |
| **Figma, design system bundles** | A standalone export of a Claude Design prototype is a self-unpacking bundle. The page source and its data are gzipped inside a manifest, not in the visible markup. Extract the manifest and decompress to read them |
| **Atlassian** | Confluence is reachable through the connector. A tiny link identifier works directly as a page identifier. A parent page may return an empty body, in which case fetch its descendants |
| **The Linux sandbox** | Has no outbound network access to Figma or GitHub. Fetch through the connectors, not through the shell |

---

## People

| Who | Role | Notes |
|---|---|---|
| **Joel Feyereisen** | Owns the Upgrade to Pros team repository and wrote the scenario scripts | Contributions go to him as a pull request. Two code owners |
| **Daidipya** | Author of the Base Entity Map and its glossary | His Customer Profile card values were the source for the card styling |
| **John Gaquin** | Spotted that "Job" was being used for two different things | That observation produced the current spine and work split |

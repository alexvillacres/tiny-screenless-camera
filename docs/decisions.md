# Decision Log

This lightweight log records product and engineering choices. Status values are **accepted**, **provisional**, **superseded**, or **open**.

## D-001 — Delayed viewing is essential

- **Date:** 2026-10-13
- **Status:** Accepted
- **Decision:** The camera will not provide a screen, immediate preview, or automatic delivery of new photographs to a phone.
- **Why:** Remaining present and discovering images later is the central purpose of the product.

## D-002 — Use a single-button capture interaction

- **Date:** 2026-10-13
- **Status:** Accepted
- **Decision:** One physical shutter button is the only required control during capture.
- **Why:** The camera should remove decisions and friction at the moment a memory is preserved.

## D-003 — Favor lo-fi character over image quality

- **Date:** 2026-10-13
- **Status:** Accepted
- **Decision:** Modern phone-level image quality is not a goal. Imperfect early-digital character is welcome.
- **Why:** The memory and the candid act of capture matter more than technical perfection.

## D-004 — Reliability outranks polish

- **Date:** 2026-10-13
- **Status:** Accepted
- **Decision:** A press must result in either a durably saved photograph and a success cue, or a clearly different error cue.
- **Why:** A simple camera cannot ask the user to verify its work on a screen.

## D-005 — Start without wireless transfer

- **Date:** 2026-10-13
- **Status:** Accepted for MVP
- **Decision:** Store images on microSD and retrieve them later. Bluetooth, Wi-Fi, and a phone app are out of scope for the first prototype.
- **Why:** Local storage supports delayed discovery and keeps the first engineering milestone focused.

## D-006 — Start with USB power

- **Date:** 2026-10-13
- **Status:** Accepted for MVP
- **Decision:** Prove the capture loop while powered over USB before adding a battery or enclosure.
- **Why:** This isolates firmware and storage work from battery safety, charging, sleep, and packaging concerns.

## D-007 — Use XIAO ESP32-S3 Sense as the first candidate

- **Date:** 2026-10-13
- **Status:** Provisional
- **Decision:** Plan the bench prototype around the Seeed Studio XIAO ESP32-S3 Sense.
- **Why:** Its expected size, camera, microSD, USB, and future wireless capabilities align with the concept.
- **Revisit when:** Current specifications, pin availability, examples, and availability have been verified.

## D-008 — Do not simulate a limited film roll

- **Date:** 2026-10-13
- **Status:** Accepted
- **Decision:** Do not impose a 24- or 36-photo limit in the current concept.
- **Why:** Delayed viewing provides the meaningful constraint; scarcity would add anxiety without serving effortless capture.

## D-009 — Carrying mode

- **Date:** 2026-10-13
- **Status:** Open
- **Question:** Should the eventual object be optimized for a pocket, keychain, or clothing/bag clip?
- **Why it matters:** It affects dimensions, lens orientation, controls, durability, battery size, and attachment design.

## D-010 — Retrieval experience

- **Date:** 2026-10-13
- **Status:** Open
- **Question:** Should later retrieval use removable microSD, USB, or a deliberate wireless “develop photographs” action?
- **Constraint:** Retrieval must preserve intentional delay and must not be required for capture.

## Entry template

```markdown
## D-XXX — Short title

- **Date:** YYYY-MM-DD
- **Status:** Open | Provisional | Accepted | Superseded
- **Decision:** What was chosen.
- **Why:** The reasoning and tradeoffs.
- **Revisit when:** Optional trigger for reconsideration.
```


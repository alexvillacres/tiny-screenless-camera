# Tiny Screenless Camera

> Capture the moment. Experience it now. Revisit it later.

A pocket-sized, one-button digital camera for candid memory capture without the interruption of a phone, screen, preview, or menu.

The project takes inspiration from point-and-shoot film cameras and early digital cameras: imperfect images, simple operation, and the pleasure of discovering photographs after the moment has passed. The first prototype is intentionally modest—press a physical button and reliably save a JPEG to a microSD card.

## Why this exists

Pulling out a phone turns a moment into a small task: unlock, open the camera, compose, review, and sometimes retake. This camera aims to reduce that entire interaction to one gesture.

It is not trying to outperform a phone camera. It is trying to make preserving a memory feel effortless while keeping the photographer present.

## The experience

- Carry it in a pocket, on a keychain, or clipped to a bag.
- Point it generally toward the moment.
- Press one button.
- Receive subtle confirmation that the photograph was saved.
- Keep going—there is no screen and nothing to review.
- Retrieve the photographs later, deliberately.

## First prototype

The initial build is planned around a Seeed Studio XIAO ESP32-S3 Sense, microSD storage, a physical shutter button, and USB power.

**Milestone 1:** pressing the button saves a photograph reliably.

Battery operation, sleep behavior, enclosure design, and phone transfer come only after the basic capture loop works.

## Project status

This repository is at the research and prototype-planning stage. Hardware specifications, compatibility notes, and prices are working assumptions until they are verified against current manufacturer documentation or tested on the bench.

## Documentation

- [Product vision](docs/vision.md)
- [Design principles](docs/principles.md)
- [MVP requirements](docs/requirements.md)
- [Hardware research and BOM](docs/hardware.md)
- [System architecture](docs/architecture.md)
- [Milestones](docs/milestones.md)
- [Decision log](docs/decisions.md)

## Repository layout

```text
.
├── docs/       Product and engineering documentation
├── firmware/   Embedded software for the camera
└── hardware/   Wiring, enclosure, and future board files
```

## Guiding constraint

The photographs may be imperfect. The act of taking one should be simple, and saving it should be trustworthy.


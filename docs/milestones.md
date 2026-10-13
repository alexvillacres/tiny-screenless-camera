# Milestones

## M0 — Validate the plan

**Outcome:** enough verified information to purchase the first parts safely.

- Verify the current XIAO ESP32-S3 Sense specifications and board revision.
- Confirm camera and microSD example support.
- Identify a safe shutter-button pin.
- Choose the initial firmware framework and development setup.
- Update the BOM with sources, dates, and actual prices.

## M1 — One press, one saved photograph

**Outcome:** a USB-powered bench prototype reliably saves a JPEG to microSD.

- Bring up the camera and save a test frame.
- Read a physical button.
- Add debounce and one-shot behavior.
- Create collision-safe filenames.
- Signal success only after the file is closed.
- Distinguish initialization and write failures.
- Pass 20 consecutive capture tests.

## M2 — Understand the photographic character

**Outcome:** know what the stock hardware feels like as a camera.

- Take photographs indoors, outdoors, in motion, and in low light.
- Measure warm capture latency.
- Test viewfinder-free pointing and framing.
- Compare available sensor settings without chasing technical perfection.
- Choose a default image size and quality setting.

## M3 — Make it portable

**Outcome:** an untethered prototype can be carried and used for a day.

- Verify battery and charging requirements from official documentation.
- Select a safe battery and add a physical power strategy.
- Measure capture current, idle current, and shots per charge.
- Experiment with sleep and wake latency.
- Build a protective prototype enclosure.

## M4 — Test the real interaction

**Outcome:** learn whether the object supports presence and candid capture.

- Carry it in ordinary life.
- Compare pocket, keychain, and clip use.
- Record missed moments, accidental shots, and confusing feedback.
- Decide whether LED, haptic, or another confirmation best fits the experience.
- Refine the form and lens direction from use, not speculation.

## M5 — Deliberate photo retrieval

**Outcome:** retrieve images conveniently without undermining delayed discovery.

- Compare microSD, USB, Bluetooth Low Energy, and Wi-Fi transfer paths.
- Prototype a user-invoked “develop photographs” flow if software is warranted.
- Keep capture independent from the phone.
- Avoid background transfer or immediate preview by default.

## Someday / maybe

- Custom PCB for size and power optimization
- Wider-angle camera module
- Purpose-built mobile importer
- Day-based collections during import
- More durable enclosure and attachment system


# Architecture

## MVP system

```text
Physical button
      │
      ▼
ESP32-S3 firmware ──► camera sensor
      │                    │
      │                    ▼
      │               JPEG frame
      │                    │
      ▼                    ▼
status feedback ◄── save to microSD

USB-C provides power, firmware upload, and development logs.
```

## Capture flow

1. Initialize serial diagnostics, camera, microSD, shutter input, and feedback output.
2. Wait for a clean button press.
3. Debounce and prevent a held button from triggering repeatedly.
4. Request a JPEG frame from the camera.
5. Generate a collision-safe filename.
6. Write the full frame to microSD and close the file.
7. Confirm success only after the write completes; otherwise signal an error.
8. Release the frame buffer and return to the ready state.

## Proposed firmware boundaries

| Area | Responsibility |
|---|---|
| `camera` | Sensor initialization, frame capture, and frame-buffer lifetime |
| `storage` | SD initialization, filename allocation, complete writes, and errors |
| `shutter` | GPIO configuration, debounce, and one-shot button events |
| `feedback` | Ready, saved, busy, and error signals |
| `app` | Startup and coordination of the capture state machine |

Exact file layout will be chosen with the firmware framework.

## State model

```text
BOOT ──► READY ──button──► CAPTURING ──► SAVING ──► CONFIRM ──► READY
  │         │                  │             │
  └─────────┴──────────────────┴─────────────┴──error──► ERROR
```

The first implementation may remain awake and USB-powered. Later versions can place a low-power state between captures, but only after wake latency and peripheral power behavior are measured.

## Data model

For the first prototype, each capture is a standalone JPEG file. A simple monotonic filename such as `IMG_000001.JPG` is easy to inspect and does not require a real-time clock. The implementation must find the next safe value after restart and must not overwrite an existing image.

Timestamps and metadata are optional until the device has a trustworthy time source.

## Evolution path

### Portable prototype

Add battery power, charging validation, a power strategy, and a rough enclosure. Preserve the same one-button capture behavior.

### Refined physical object

Measure real carrying constraints, explore feedback and lens choices, and design an enclosure around verified components. A custom PCB is considered only if the development-board stack prevents the desired form.

### Deliberate retrieval

Explore USB or local wireless transfer as a user-invoked “develop photographs” action. The camera should not push previews or demand a phone connection while shooting.

## Architectural constraints

- Capture must not depend on a phone, account, or internet connection.
- The storage path is local-first.
- Confirmation means the image is durably written, not merely captured in memory.
- Wireless capability must not turn delayed discovery into immediate review by default.
- Optimizing battery life must not make the shutter feel untrustworthy.


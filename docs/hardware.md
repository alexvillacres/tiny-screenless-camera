# Hardware Research and Bill of Materials

## Verification status

This page is a planning document, not a purchasing authority. Unless a row says **verified**, specifications, pin assignments, compatibility, availability, and prices are **unverified working assumptions** carried forward from early research. Check current manufacturer documentation and seller listings before ordering or wiring parts.

## Candidate platform

### Seeed Studio XIAO ESP32-S3 Sense

Why it is the leading candidate:

- compact ESP32-S3 development board and camera expansion board;
- camera capture examples are expected to exist in the vendor ecosystem;
- microSD storage is expected on the Sense expansion board;
- USB-C development and power;
- Wi-Fi and Bluetooth Low Energy leave room for later experiments;
- approachable through Arduino or ESP-IDF tooling.

Planning assumptions to verify:

| Item | Working assumption | Status |
|---|---|---|
| Camera sensor | OV3660, approximately 3 MP / 2048 × 1536 | Unverified |
| Board dimensions | Main board approximately 21 × 17.8 mm; assembled camera stack is thicker | Unverified |
| Storage | microSD slot on Sense expansion board | Unverified |
| Wireless | 2.4 GHz Wi-Fi and Bluetooth Low Energy | Unverified |
| Battery support | Single-cell lithium battery connection/charging support may be available on the XIAO platform | Unverified; must confirm safety and exact behavior |
| Logic voltage | 3.3 V GPIO | Unverified |
| Typical price | Approximately US$14–20 | Unverified; price and region dependent |

## Prototype BOM

| Part | Purpose | Qty. | Planning price (USD) | Status / note |
|---|---|---:|---:|---|
| Seeed Studio XIAO ESP32-S3 Sense | Processor, camera, and microSD interface | 1 | $14–20 | Unverified price/specs |
| Compatible microSD card | Photo storage | 1 | $5–10 | Capacity and filesystem limits TBD |
| Momentary push button | Shutter input | 1 | $1–3 | Verify size and breadboard fit |
| Solderless breadboard | First wiring experiments | 1 | $4–8 | May be unnecessary with clip leads |
| Jumper wires | Button and indicator wiring | 1 set | $3–6 | Connector style TBD |
| USB-C data cable | Programming and initial power | 1 | $0–10 | Must support data, not charge-only |
| LED and resistor, if needed | Capture/error feedback | 1 each | <$1 | An onboard LED may be usable; verify |

**Estimated prototype total:** approximately **$27–58**, before shipping and tax. This range is unverified and assumes no battery or enclosure.

## Not needed for Milestone 1

- LiPo battery
- battery protection or additional charger hardware
- power switch
- vibration motor or haptic driver
- 3D-printed enclosure
- custom PCB
- phone app

## Hardware risks to test early

### Capture latency

Camera initialization and exposure may take long enough to miss a candid moment. Measure cold-start, already-awake, and eventual deep-sleep wake paths separately.

### Power consumption

The camera and microSD subsystem may draw meaningful current even when the processor sleeps. Battery life must be measured on the actual assembly; power-gating parts of the system may eventually be necessary.

### Pin availability

The camera and microSD expansion may consume pins that appear available on the base board. Confirm a safe shutter GPIO and whether an external feedback device can be driven at the same time.

### microSD reliability

Card compatibility, current spikes, filesystem corruption, and unsafe removal need testing. A success cue must happen after the image write is complete.

### Viewfinder-free framing

The stock lens may be too narrow for casual pointing. Test it before selecting a replacement or designing the enclosure.

### Battery safety

Do not add a lithium battery until the exact board revision, connector polarity, charging behavior, protection requirements, and cell compatibility are confirmed from current official documentation.

## Purchase gate

Before buying parts:

- [ ] Confirm the exact XIAO ESP32-S3 Sense revision and included camera sensor.
- [ ] Confirm that the package includes the camera expansion board and antenna, if required.
- [ ] Confirm microSD support and supported filesystem/card guidance.
- [ ] Confirm at least one free, suitable GPIO for the shutter button.
- [ ] Confirm USB cable and development environment requirements.
- [ ] Recheck current prices and shipping.


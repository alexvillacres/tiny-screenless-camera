# MVP Requirements

## MVP definition

The minimum viable prototype is a USB-powered, screenless camera that captures a JPEG to a microSD card when a physical button is pressed.

## Functional requirements

| ID | Requirement | Acceptance signal |
|---|---|---|
| MVP-01 | A physical button initiates capture. | A deliberate press triggers exactly one capture. |
| MVP-02 | The camera stores the image as a JPEG on microSD. | The card can be removed and the file opened on a computer. |
| MVP-03 | Each successful capture receives a unique filename. | Repeated captures do not overwrite earlier images. |
| MVP-04 | The user receives subtle success feedback. | An LED pattern or other cue occurs only after the file is closed successfully. |
| MVP-05 | Failures are distinguishable from success. | Missing card, initialization failure, or write failure produces a different cue. |
| MVP-06 | The device has no image preview. | No display or automatic transfer is present. |
| MVP-07 | Button bounce does not create accidental bursts. | A normal press creates one file in repeated testing. |

## Reliability targets for the first bench prototype

- Save at least 20 consecutive button-triggered images without a failed write.
- Recover safely from power-up with no card inserted.
- Preserve previously saved images after power loss between captures.
- Record useful diagnostic messages over USB serial during development.

These are prototype targets, not final product specifications.

## Out of scope for MVP

- Battery power and charging behavior
- Deep sleep and instant wake
- Bluetooth or Wi-Fi transfer
- Phone application
- Custom image processing or filters
- Custom PCB
- Final enclosure
- Production-ready weather, drop, or pocket durability
- Video, burst mode, zoom, or a viewfinder

## Open product questions

- Pocket, keychain, or clip as the primary carrying mode?
- Is an LED subtle enough, or would a brief vibration feel better?
- How much capture latency is acceptable in candid use?
- Is the stock lens wide enough for viewfinder-free framing?
- Should later retrieval happen through microSD, USB, or a deliberate wireless “develop” action?


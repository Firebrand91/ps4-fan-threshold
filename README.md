# PS4 Fan Threshold — PS4 FW 11.02

Precompiled PS4 Fan Threshold payloads for **PS4 firmware 11.02**, tested with **GoldHEN v2.4b18.10**.

This repository provides ready-to-use `.bin` payloads for three different fan temperature thresholds:

* **55°C**
* **60°C**
* **65°C**

The payloads were compiled from the original `ps4-fan-threshold` source and tested on a real PS4 running firmware **11.02**.

---

## Payloads

| Payload     | Fan Threshold |
| ----------- | ------------: |
| `fan55.bin` |          55°C |
| `fan60.bin` |          60°C |
| `fan65.bin` |          65°C |

All three payloads were successfully tested on **PS4 FW 11.02 + GoldHEN v2.4b18.10**.

---

## Compatibility

* **Console:** PlayStation 4
* **Firmware:** 11.02
* **GoldHEN:** v2.4b18.10
* **Payload format:** `.bin`
* **GoldHEN Payload Server:** TCP port `9090`
* **GoldHEN LaunchPad:** Tested
* **GoldHEN AutoRun Queue:** Tested

---

## Installation

Copy the desired `.bin` file to:

```text
/data/payloads/
```

For example:

```text
/data/payloads/fan65.bin
```

The payload can then be launched using **GoldHEN LaunchPad**.

The payload can also be added to the **GoldHEN AutoRun Queue**.

---

## Payload Server

GoldHEN's Payload Server can be used to send the `.bin` directly to the console.

The server listens on TCP port:

```text
9090
```

For example:

```text
PS4_IP:9090
```

The payloads in this repository were successfully tested using the GoldHEN Payload Server on PS4 firmware 11.02.

---

## AutoRun

The **65°C payload (`fan65.bin`)** was successfully tested with GoldHEN's **AutoRun Queue**.

This allows the fan threshold to be applied automatically after GoldHEN is activated, without manually sending the payload after every jailbreak.

GoldHEN also provides an option to skip the AutoRun queue during boot when required.

---

## Choosing a Threshold

### 55°C

More aggressive cooling.

The fan will generally react sooner, which can result in increased fan noise.

### 60°C

A balanced setting between cooling and fan noise.

### 65°C

Allows the console to reach a higher temperature before the fan controller increases cooling.

This is the recommended setting if you prefer a quieter fan profile while maintaining a conservative thermal threshold.

---

## Important: Temperature Threshold

The selected value is a **fan temperature threshold**, not a fixed temperature lock.

For example, setting the threshold to 65°C does not mean that the PS4 will remain permanently at exactly 65°C.

The actual temperature can fluctuate depending on:

* CPU/GPU workload
* game or application
* ambient temperature
* PS4 model
* cooling system condition
* thermal paste condition
* fan behaviour
* system thermal management

---

## Why This Repository?

Older PS4 Fan Threshold payloads are already available in the PS4 homebrew scene.

This repository provides **ready-to-use precompiled builds tested specifically on PS4 firmware 11.02 with GoldHEN v2.4b18.10**, using three commonly useful temperature thresholds.

The goal is simple:

1. Download the desired `.bin`.
2. Copy it to `/data/payloads/`.
3. Launch it through GoldHEN LaunchPad.
4. Optionally add it to the AutoRun Queue.

No SDK installation or compilation is required for users who simply want to use the precompiled payloads.

---

## Building From Source

The payload source is based on the original:

**Scene-Collective — ps4-fan-threshold**

https://github.com/Scene-Collective/ps4-fan-threshold

The payload was built using:

**Scene-Collective — ps4-payload-sdk**

https://github.com/Scene-Collective/ps4-payload-sdk

The temperature threshold is defined in:

```text
source/main.c
```

For example:

```c
uint8_t THRESHOLDTEMP = 65;
```

Changing this value and running the GitHub Actions workflow produces a payload using the selected threshold.

---

## Build Process

The payloads were compiled using **GitHub Actions** with the Scene-Collective PS4 Payload SDK.

The resulting `.bin` files were then transferred to and tested on a real PS4 running:

**Firmware 11.02 + GoldHEN v2.4b18.10**

---

## Credits

Original payload project:

**Scene-Collective — ps4-fan-threshold**

https://github.com/Scene-Collective/ps4-fan-threshold

PS4 Payload SDK:

**Scene-Collective — ps4-payload-sdk**

https://github.com/Scene-Collective/ps4-payload-sdk

GoldHEN:

**GoldHEN Team**

https://github.com/GoldHEN/GoldHEN

This repository contains unofficial precompiled and tested builds.

It is **not affiliated with, endorsed by, or an official release from Scene-Collective or GoldHEN**.

---

## Disclaimer

Use these payloads at your own discretion.

Changing the fan threshold changes the behaviour of the PS4 thermal control system.

The selected threshold does not guarantee a specific operating temperature under all conditions.

Monitor your console's temperature and behaviour when experimenting with different settings.

---

## Tested Configuration

**PS4 Firmware:** 11.02
**GoldHEN:** v2.4b18.10

### Tested Payloads

* `fan55.bin` — 55°C — ✅ Tested
* `fan60.bin` — 60°C — ✅ Tested
* `fan65.bin` — 65°C — ✅ Tested

### GoldHEN Features Tested

* Payload Server — ✅
* LaunchPad — ✅
* AutoRun Queue — ✅
* Automatic application of `fan65.bin` after GoldHEN activation — ✅

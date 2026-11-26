# Decision Log

Newest last. Each entry: decision, reason, alternatives, date.

## D1: Device is a Raspberry Pi 5 (8GB) — 2026-11-25
- **Why:** Low power (about 5-10W), large community, runs 1-4B quantized models via llama.cpp at usable speed for Q&A. Already owned.
- **Rejected:** Arduino/ESP32 (kilobytes of RAM, cannot run a useful LLM). Jetson Orin Nano Super (faster, but more expensive and a heavier power draw; revisit only if speed or vision becomes a priority).
- **Note:** Jetson is an alternative to the Pi, not an add-on.

## D2: No PoE HAT — 2026-11-25
- **Why:** The device runs from battery and solar with no Ethernet. A PoE HAT adds cost and idle draw.
- **Use instead:** USB-C power (5V/5A preferred, 5V/3A minimum) from a power bank or solar charge controller with a PD output, plus a heatsink or active cooler.

## D3: OS is Raspberry Pi OS Lite 64-bit, not a custom OS — 2026-11-25
- **Why:** 64-bit is required for llama.cpp. Lite idles at roughly 150-250MB RAM. A from-scratch OS would take weeks and complicate power, wireless, display and GPIO.
- **Plan:** Stripped appliance setup (headless, unused services off, read-only root, auto-start service). Freeze into a reproducible image with pi-gen once stable.

## D4: Read-only root filesystem (overlayfs) — 2026-11-25
- **Why:** Power loss on a battery system can corrupt SD cards mid-write. Models and knowledge live on a separate partition or NVMe.

## Open questions
- Which model and quantization (candidates: 1.5B-3B class such as Qwen, Gemma, Llama 3.2)?
- NVMe vs microSD for model storage?
- Interface: screen, buttons, voice, or all three?
- Battery chemistry and solar panel wattage for target runtime?

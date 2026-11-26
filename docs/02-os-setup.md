# OS Setup

Target: Raspberry Pi OS Lite 64-bit, headless, appliance-style.

## Steps
1. Flash Raspberry Pi OS Lite (64-bit) with Raspberry Pi Imager. Enable SSH and set hostname, user and Wi-Fi in the imager settings.
2. First boot: `sudo apt update && sudo apt full-upgrade`.
3. Build or install llama.cpp (script to be added in `scripts/`).
4. Run the llama.cpp server as a systemd service (unit to be added in `config/`).
5. Disable unused services (Bluetooth, avahi, desktop), and turn off HDMI output to save power.
6. Move model and knowledge files to a separate partition or NVMe.
7. Enable read-only root (overlayfs) last, after everything is working.

## Later
- Freeze the working setup into a reproducible image with pi-gen.

Each step above will get its exact commands recorded here as we run them.

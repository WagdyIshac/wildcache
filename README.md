# wildcache: Off-Grid Survival SLM

A small language model running on a Raspberry Pi 5, powered by battery and solar, that gives survival guidance with no internet connection.

**Status:** Hardware, OS plan and model family chosen. Next: benchmarks and the survival knowledge base.

## Goals
- Run fully offline on a battery and solar budget
- Answer survival questions (water, shelter, fire, first aid, navigation, foraging)
- Ground answers in an offline reference library (RAG) rather than model memory alone
- Be reproducible: anyone can rebuild the device from this repo

## Repo layout
| Path | Purpose |
|---|---|
| `docs/DECISIONS.md` | Log of every decision and why (read this first) |
| `docs/01-hardware.md` | Board, power, storage, cooling |
| `docs/02-os-setup.md` | OS install and appliance hardening steps |
| `scripts/` | Setup and helper scripts |
| `config/` | systemd units and config files |
| `models/` | Model files (git-ignored; see docs for download) |
| `knowledge/` | Offline survival library for retrieval |

## Roadmap
- [x] 1. Choose device
- [x] 2. Choose OS approach
- [ ] 3. Model: Qwen2.5-3B-Instruct Q4_K_M chosen (see D5); benchmark tokens/sec and power draw
- [ ] 4. Build offline knowledge base (RAG)
- [ ] 5. Power system: battery, solar panel, charge controller, runtime tests
- [ ] 6. Read-only root and auto-start service
- [ ] 7. Enclosure and interface (screen, buttons, or voice)
- [ ] 8. Field test and publish

## License
MIT (see `LICENSE`)

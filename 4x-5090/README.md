# 4× NVIDIA RTX 5090

<img src="photos/gallery/banner.webp" alt="The 4× 5090 build — four RTX 5090s stacked in the open cube frame over the fan base">

The team build: four RTX 5090s in a cube housing on an AMD Ryzen Threadripper PRO platform. Built for larger open models like Kimi, MiniMax, and GLM. No API bills. Low latency. Private data.

- **4× NVIDIA RTX 5090** — 128 GB VRAM · 7,168 GB/s · 838 FP32 TFLOPS
- **AMD Ryzen Threadripper PRO** · 96 GB RAM · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU · 2× 10 GbE · BMC
- **2,750 W draw** · 4,000 W PSU
- **20″ × 20″ × 24″** · 66 lb

> **Draft guide** — component photos are representative and a few specs are still being confirmed; the real build photos, the board manual, and a testing screenshot are landing soon.

## Prefer a finished machine?

Building from this guide is the full DIY path. If you'd rather skip sourcing, CNC, and assembly, we have it covered — [order the 4× 5090 built](https://www.autonomous.ai/computer-4).

## Build it

1. **Parts** — the [bill of materials](bom/bom.md).
2. **Housing** — the [STL files](stl-models) and the [STEP files](step_models).
3. **Lay out the electronics** — the [component checklist](docs/prepare-ee.md), with a photo of every part.
4. **Assemble** — the [step-by-step assembly guide](docs/assembly.md), 23 steps from bare housing to closed box.
5. **BIOS, drivers, testing** — the shared [BIOS tuning and GPU testing](../setup.md) guide. Board-specific notes below.
6. **Serve your models** — [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI, or any local AI engine: vLLM, Ollama, llama.cpp.

<table>
<tr>
<td width="50%"><img src="photos/gallery/fan-chassis.webp" alt="Motherboard on the fan chassis"></td>
<td width="50%"><img src="photos/gallery/psu-cabling.webp" alt="Cabling the power supplies"></td>
</tr>
<tr>
<td width="50%"><img src="photos/gallery/cooler-mount.webp" alt="Mounting a GPU to the frame"></td>
<td width="50%"><img src="photos/gallery/gpu-stack.webp" alt="All four RTX 5090s on the frame"></td>
</tr>
</table>

## BIOS notes and testing

The 4× runs on an AMD Ryzen Threadripper PRO (WRX90) board. The settings that matter (the general list is in [the setup guide](../setup.md)):

```
Enable Above 4G Decoding
Enable Re-size BAR support
Set every GPU slot to PCIe Gen 5 (with bifurcation as the board requires)
```

Exact menu paths depend on the motherboard — the board model and manual are being finalized.

Then make sure all four cards are detected, report full VRAM, and link at full PCIe width — the checklist is in [the setup guide](../setup.md#gpu-testing). A verification screenshot from this build is coming.

## Serve your models

The rig runs, now put it to work. The easiest way is [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI: it pools your machines into one local AI network. Or run any local AI engine — vLLM, Ollama, llama.cpp.

```bash
curl -fsSL https://grid.autonomous.ai/install.sh | bash
```

<img width="2200" height="1452" alt="Grid — your machines pooled into one local AI network" src="https://github.com/user-attachments/assets/0ad98393-248a-40bd-9877-e6f0847c7b0e" />

## The finished machine

<img src="photos/gallery/finished.webp" alt="The finished 4× 5090">

## Other builds

The [2× 5090](../2x-5090/README.md) (start tonight), the [2× 6000](../2x-6000/README.md) (desk-sized, 192 GB VRAM), the [4× 6000](../4x-6000/README.md) (384 GB VRAM), and the [8× 5090](../8x-5090/README.md) (on-prem scale) round out the family.

## License

Open source under the [MIT License](../LICENSE).

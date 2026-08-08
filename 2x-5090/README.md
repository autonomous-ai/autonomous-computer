# 2× NVIDIA RTX 5090

<img src="photos/gallery/hero.webp" alt="The 2× 5090 build — two RTX 5090s on the open frame">

The entry-level Personal AI Computer: two RTX 5090s on an Intel Xeon W platform. Desk-sized, runs on a normal wall outlet, and enough VRAM for Llama, Qwen, and DeepSeek with quantization — run OpenClaw, Hermes Agent, or your own LangChain stack with zero API spend.

- **2× NVIDIA RTX 5090** — 64 GB VRAM · 3,584 GB/s · 419 FP32 TFLOPS
- **Intel Xeon W5** (ASUS W790 ACE) · 96 GB RAM · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU · 10 GbE + 2.5 GbE
- **1,550 W draw** · 1,600 W PSU
- **12.5″ × 12.5″ × 16″** · 33 lb

## Prefer a finished machine?

Building from this guide is the full DIY path. If you'd rather skip sourcing, CNC, and assembly, we have it covered — [order the 2× 5090 built](https://www.autonomous.ai/computer-2).

## Build it

1. **Parts** — the [bill of materials](bom/bom.md).
2. **Housing** — the [STL files](stl-models) and the [STEP files](step_models).
3. **Lay out the electronics** — the [component checklist](docs/prepare-ee.md), with a photo of every part.
4. **Assemble** — the [photo-by-photo assembly guide](docs/assembly.md), 23 steps from bare housing to closed box.
5. **BIOS, drivers, testing** — the shared [BIOS tuning and GPU testing](../setup.md) guide. Board-specific notes below.
6. **Serve your models** — [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI, or any local AI engine: vLLM, Ollama, llama.cpp.

<table>
<tr>
<td width="50%"><img src="photos/gallery/riser-detail.webp" alt="Seating the PCIe riser"></td>
<td width="50%"><img src="photos/gallery/riser-frame.webp" alt="Mounting the PCIe 5.0 risers"></td>
</tr>
<tr>
<td width="50%"><img src="photos/gallery/fan-tray.webp" alt="The fan tray"></td>
<td width="50%"><img src="photos/gallery/side-panel.webp" alt="Closing the side panel"></td>
</tr>
</table>

## BIOS notes and testing

The two settings that matter on the W790 (the general list is in [the setup guide](../setup.md)):

```
Advanced -> PCI Subsystems Settings -> Enable Above 4G Decoding
Advanced -> PCI Subsystems Settings -> Enable Re-size BAR support
```

Board references: [motherboard manual](docs/um-motherboard.pdf) · [BIOS manual](docs/um-bios.pdf)

Then make sure both cards are detected, report full VRAM, and link at full PCIe width — the checklist is in [the setup guide](../setup.md#gpu-testing).

<p align="center">
    <img src="photos/2gpu/testing/nvidia-smi.png" width="700" alt="nvidia-smi with both RTX 5090s detected">
</p>

## Serve your models

The rig runs, now put it to work. The easiest way is [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI: it pools your machines into one local AI network. Or run any local AI engine — vLLM, Ollama, llama.cpp.

```bash
curl -fsSL https://grid.autonomous.ai/install.sh | bash
```

<img width="2200" height="1452" alt="Grid — your machines pooled into one local AI network" src="https://github.com/user-attachments/assets/0ad98393-248a-40bd-9877-e6f0847c7b0e" />

## The finished machine

<img src="photos/gallery/finished.webp" alt="The finished 2× 5090 on a desk">

## Other builds

Need more? The [4× 5090](../4x-5090/README.md) (the team build), the [4× 6000](../4x-6000/README.md) (384 GB VRAM), and the [8× 5090](../8x-5090/README.md) (on-prem scale) scale the same idea up.

## License

Open source under the [MIT License](../LICENSE).

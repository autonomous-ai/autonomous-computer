# Time to build your own Personal AI Computer

https://github.com/user-attachments/assets/36f7aa02-42ac-4b35-b757-a5dd3b43ef1a

## Prefer a finished machine?

Building from this guide is the full DIY path. If you'd rather skip sourcing, CNC, and assembly, we have it covered — [order a Personal AI Computer](https://www.autonomous.ai/computer/buy).

## The future of AI is local

AI in 2026 looks like computing in 1975: the intelligence lives in a few mainframes, owned by a few companies, and you rent it by the token. Everyone knows how that movie ends. The machine moves onto the desk — and the people who own their machines build everything that comes next.

The Personal AI Computer is that machine. The models are good, the GPUs are affordable, and homes and businesses are reaching the same answer: bring it in-house. Three reasons:

1. **No one can switch you off.** In June 2026 the US government took Fable 5 offline for most of a month and gated GPT-5.6 behind an approved-partner list. Weights on your own disk can't be revoked.
2. **Your business is their training data.** Every prompt you send OpenAI or Anthropic carries your product, your process, your edge. They will turn your secret sauce into their product.
3. **Inference becomes free.** Open weights on a cloud API already cut the bill 20–30×. On your own machine there is no bill at all. No API, no meter.

## The end-to-end open-source local AI stack

Open software lets you run and shape your AI; open hardware lets you build, repair, and improve the machine it runs on. With both in your hands — the code, the CAD, the BOM, the BIOS settings — you can build the whole thing end to end. So we open-source both:

- **Open Source Hardware — this repo.** Your Personal AI Computer in four sizes, below: every part, every bracket, every BIOS setting, every assembly photo.
- **Open Source Software — your choice.** The easiest way is [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI — but any local AI engine works: vLLM, Ollama, llama.cpp.

## 2× NVIDIA RTX 5090

The entry-level build, for personal use. Enough for Llama, Qwen, and DeepSeek with quantization — run OpenClaw, Hermes Agent, or your own LangChain stack locally.

- **2× NVIDIA RTX 5090** — 64 GB VRAM · 3,584 GB/s · 419 FP32 TFLOPS
- **Intel Xeon W5** (ASUS W790 ACE) · 96 GB RAM · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU · 10 GbE + 2.5 GbE
- **1,550 W draw** · 1,600 W PSU
- **12.5″ × 12.5″ × 16″** · 33 lb

**[Build the 2× 5090 →](2x-5090/README.md)** · **[Or order it built →](https://www.autonomous.ai/computer-2)**

<a href="2x-5090/README.md"><img src="2x-5090/photos/gallery/hero.webp" alt="The 2× 5090 build — two RTX 5090s on the open frame"></a>

<table>
<tr>
<td width="50%"><img src="2x-5090/photos/gallery/riser-detail.webp" alt="Seating the PCIe riser"></td>
<td width="50%"><img src="2x-5090/photos/gallery/riser-frame.webp" alt="Mounting the PCIe 5.0 risers"></td>
</tr>
<tr>
<td width="50%"><img src="2x-5090/photos/gallery/fan-tray.webp" alt="The fan tray"></td>
<td width="50%"><img src="2x-5090/photos/gallery/side-panel.webp" alt="Closing the side panel"></td>
</tr>
</table>

<img src="2x-5090/photos/gallery/finished.webp" alt="The finished 2× 5090">


## 4× NVIDIA RTX 5090

The team build. Larger open models like Kimi, MiniMax, and GLM. No API bills. Low latency. Private data.

- **4× NVIDIA RTX 5090** — 128 GB VRAM · 7,168 GB/s · 838 FP32 TFLOPS
- **AMD Ryzen Threadripper Pro** · 96 GB RAM · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU · 2× 10 GbE · BMC
- **2,750 W draw** · 4,000 W PSU
- **20″ × 20″ × 24″** · 66 lb

**[Build the 4× 5090 →](4x-5090/README.md)** · **[Or order it built →](https://www.autonomous.ai/computer-4)**

<a href="4x-5090/README.md"><img src="4x-5090/photos/gallery/banner.webp" alt="The 4× 5090 build — four RTX 5090s stacked in the open cube frame over the fan base"></a>

<table>
<tr>
<td width="50%"><img src="4x-5090/photos/gallery/fan-chassis.webp" alt="Motherboard on the fan chassis"></td>
<td width="50%"><img src="4x-5090/photos/gallery/psu-cabling.webp" alt="Cabling the power supplies"></td>
</tr>
<tr>
<td width="50%"><img src="4x-5090/photos/gallery/cooler-mount.webp" alt="Mounting a GPU to the frame"></td>
<td width="50%"><img src="4x-5090/photos/gallery/gpu-stack.webp" alt="All four RTX 5090s on the frame"></td>
</tr>
</table>

<img src="4x-5090/photos/gallery/finished.webp" alt="The finished 4× 5090">


## 8× NVIDIA RTX 5090

The on-prem build, for business. Develop, serve, and fine-tune with open models — the work that should never leave your floor.

- **8× NVIDIA RTX 5090** — 256 GB VRAM · 14,336 GB/s · 1,676 FP32 TFLOPS
- **2× AMD EPYC 9004** (ASRock Rack GENOA2D24G-2L+) · 192 GB RAM · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU, over MCIO · 2× 1 GbE · BMC
- **5,100 W draw** · 8,000 W PSU
- **5U rack chassis**

**[Build the 8× 5090 →](8x-5090/README.md)** · **[Or order it built →](https://www.autonomous.ai/computer-8)**

<a href="8x-5090/README.md"><img src="8x-5090/photos/gallery/open-chassis.webp" alt="The finished 8× 5090 — 5U rack chassis, top cover off, both GPU columns and the center fan wall"></a>

<table>
<tr>
<td width="50%"><img src="8x-5090/photos/gallery/dual-socket-board.webp" alt="The dual-EPYC (Genoa) board — two SP5 sockets and twenty-four DIMM slots"></td>
<td width="50%"><img src="8x-5090/photos/gallery/card-install.webp" alt="Seating an RTX 5090 into the chassis"></td>
</tr>
<tr>
<td width="50%"><img src="8x-5090/photos/gallery/interior-topdown.webp" alt="Top-down — the PCIe adapter boards, the center fan wall, and the MCIO cabling"></td>
<td width="50%"><img src="8x-5090/photos/gallery/psu-rear.webp" alt="The rear — 2,000 W CRPS power modules"></td>
</tr>
</table>


## 4× NVIDIA RTX PRO 6000

The server build — rack-ready for on-prem and the data center. 384 GB of VRAM: fine-tune and serve the biggest open models.

- **4× NVIDIA RTX PRO 6000 Blackwell** — 384 GB GDDR7 ECC · 7,168 GB/s (96 GB per card)
- **AMD EPYC 9124** (ASRock Rack TURIN2D24G-2L+) · 384 GB DDR5 ECC · 1 TB NVMe
- **PCIe Gen 5 ×16** per GPU, over MCIO · BMC
- **3× 2,000 W** CRPS
- **5U rack chassis**

**[Build the 4× 6000 →](4x-6000/README.md)**

<a href="4x-6000/README.md"><img src="4x-6000/photos/gallery/hero-rack.jpg" alt="The 4× 6000 build racked — 5U chassis in the server rack"></a>

<table>
<tr>
<td width="50%"><img src="4x-6000/photos/gallery/gpu-install.jpg" alt="Installing the RTX PRO 6000s"></td>
<td width="50%"><img src="4x-6000/photos/gallery/gpu-row.jpg" alt="Four flow-through RTX PRO 6000s over the airflow modules"></td>
</tr>
<tr>
<td width="50%"><img src="4x-6000/photos/gallery/interior.jpg" alt="Full chassis interior — GPUs, fan wall, dual-SP5 board"></td>
<td width="50%"><img src="4x-6000/photos/gallery/mcio-risers.jpg" alt="MCIO riser boards before the GPUs go in"></td>
</tr>
</table>

<img src="4x-6000/photos/gallery/power-detail.jpg" alt="GPU power cabling detail">

## Software

1. **[BIOS tuning and GPU testing](setup.md)** — after you build the rig, run this to make sure it actually works: BIOS settings for multi-GPU, NVIDIA drivers, then confirm every GPU is detected, linked at full PCIe width, and stable under load.

<img width="2560" height="1441" alt="gpu-testing" src="https://github.com/user-attachments/assets/b54b63bc-4f43-465d-894f-4c8dc9c61a08" />

2. **Serve your models** — the rig runs, now put it to work. The easiest way is [Grid](https://github.com/autonomous-ai/autonomous-grid), the open orchestrator for local AI: it pools your machines into one local AI network. Or run any local AI engine — vLLM, Ollama, llama.cpp.

   ```bash
   curl -fsSL https://grid.autonomous.ai/install.sh | bash
   ```

<img width="2200" height="1452" alt="home-grid (1)" src="https://github.com/user-attachments/assets/0ad98393-248a-40bd-9877-e6f0847c7b0e" />


## Contributing

Built one? Improved a part? Found a better component? See [**CONTRIBUTING.md**](CONTRIBUTING.md) — and [share your build](https://github.com/autonomous-ai/autonomous-computer/issues/new?template=share-your-build.md). The best community builds get featured.

## License

Open source under the [MIT License](LICENSE). Fork it, change it, build your own and sell it — we just want it built.

---

<div align="center">
<b>Autonomous</b> — the AI hardware company.<br>
Questions? <a href="https://github.com/autonomous-ai/autonomous-computer/issues">Open an issue.</a>
</div>

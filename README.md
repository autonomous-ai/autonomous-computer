# Autonomous Computer — Build Your Own Personal AI Computer

https://github.com/user-attachments/assets/3e410e5d-83f4-4aed-a8b4-2426781f3ebd

<div align="center">

<img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT">
<img src="https://img.shields.io/github/stars/autonomous-ai/autonomous-computer" alt="GitHub stars">
<img src="https://img.shields.io/github/forks/autonomous-ai/autonomous-computer" alt="GitHub forks">
<img src="https://img.shields.io/badge/Status-In%20Development-blue" alt="Status">
<img src="https://img.shields.io/github/repo-size/autonomous-ai/autonomous-computer" alt="Repo Size">
<img src="https://img.shields.io/github/issues/autonomous-ai/autonomous-computer" alt="Open Issues">

</div>

---

<div align="center">
<b><i>Own your intelligence.</i></b><br>
The best models live in someone else's cloud, behind someone else's terms and someone else's government — a model you rent can be cut off overnight; a model in your own house can't. These are open-source guides to build that machine: every part, every bracket, every BIOS setting, every assembly photo. Pick the size that fits your budget and your work. <b>Build it once; own it for good.</b>
</div>

## Pick your configuration

One Personal AI Computer, three configurations — from a home rig to an on-prem business cluster. Each is a complete, self-contained guide: bill of materials, 3D-printable/CNC housing files, wiring, BIOS, and assembly photos.

| Config | GPUs | VRAM | Best for | Platform | Guide |
|---|---|---|---|---|---|
| **2×** | 2× RTX 5090 | 64 GB | **Home** — your first local rig, runs a real model tonight | Intel Xeon W5 · ASUS W790 | [→ 2× config](builds/2x/README.md) |
| **4×** | 4× RTX PRO 6000 Blackwell | 384 GB | **Team** — big models + agents running all day | AMD EPYC 9124 · ASRock Rack | [→ 4× config](builds/4x/README.md) |
| **8×** | 8× RTX 4090 / 5090 | 192–256 GB | **On-prem business** — a company's AI on its own floor; IP and data never leave | Dual AMD EPYC 9004 (Genoa) | [→ 8× config](builds/8x/README.md) |

## Quick start

1. **Pick a configuration** above by budget and the models you want to run.
2. **Source the parts** from that config's Bill of Materials.
3. **Make the housing** — print the STL files or CNC the STEP files in that config's folder.
4. **Assemble** — follow the config's photo-by-photo assembly guide.
5. **Set up the software** — drivers, BIOS, and serving open models locally: [`/software`](software/README.md).
6. **Run your intelligence** — point your agent at `localhost` and never get cut off again. Running more than one machine? [**Grid**](https://github.com/autonomous-ai/autonomous-grid) gives them all one endpoint.

## The configurations

- [**2× — Home**](builds/2x/README.md) · 2× RTX 5090, 64 GB
- [**4× — Team**](builds/4x/README.md) · 4× RTX PRO 6000 Blackwell, 384 GB
- [**8× — On-prem business**](builds/8x/README.md) · 8× RTX 4090/5090, 192–256 GB

## Software

Bringing the box to life — OS, NVIDIA drivers, BIOS tuning, serving open models (Ollama / vLLM / llama.cpp), and connecting an agent: [**`/software`**](software/README.md). *(Setup and testing are documented today; local model-serving guides are in progress.)*

### Manage your rig with Grid

Once the box serves a model, [**Grid**](https://github.com/autonomous-ai/autonomous-grid) is how you run it day to day. Grid is our open-source orchestration layer for local AI: it pools the computers you already own — this rig, your Mac, the workstation in the corner — behind **one OpenAI-compatible endpoint** and routes each request to whichever machine is running the right model. Your inference servers (Ollama, vLLM, llama.cpp, LM Studio, MLX) stay exactly where they are; Grid ties them together, on your local network or remotely.

```bash
curl -fsSL https://grid.autonomous.ai/install.sh | bash
```

It's a big project with its own repo — quickstart, CLI reference, and how it works: [**autonomous-ai/autonomous-grid**](https://github.com/autonomous-ai/autonomous-grid).

## Contributing

Built one? Improved a part? Found a better component? See [**CONTRIBUTING.md**](CONTRIBUTING.md) — and [share your build](https://github.com/autonomous-ai/autonomous-computer/issues/new?template=share-your-build.md). The best community builds get featured.

## License

Open source under the [MIT License](LICENSE). Fork it, change it, build your own and sell it — we just want it built.

---

<div align="center">
<b>Autonomous</b> — the AI hardware company.<br>
Questions? <a href="https://github.com/autonomous-ai/autonomous-computer/issues">Open an issue.</a>
</div>

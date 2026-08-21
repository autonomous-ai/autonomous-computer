# Brainstorm & Discussion — Alternative Build Options

Three alternative builds weighed while scoping the 4× RTX PRO 6000. All three were costed against a dual-socket EPYC 9124 server platform, which is the baseline they refer to below; the machine that shipped is the one in the [bill of materials](../bom/bom.md). Each table lists the proposed swap, the rationale, and a verification note.

---

## Option 1 — Higher-Speed Variant (RTX 5090)

| Component  | Proposed Swap                                          | Rationale                                                                                  |
|:-----------|:-------------------------------------------------------|:-------------------------------------------------------------------------------------------|
| Mainboard  | ASRock Rack GENOAD12M-2Q (or equivalent single-socket) | Single-socket but keeps all 12 DIMM slots                                                  |
| CPU        | AMD EPYC 9354 (32C) or 9454 (48C)                      | 2–3× the core count of 9124; higher clock to feed RTX 5090 without bottlenecking           |
| RAM        | 12× 64 GB DDR5-4800 / 5600 ECC RDIMM                   | Unchanged                                                                                  |
| GPU        | RTX 5090                                               | Unchanged                                                                                  |
| SSD        | Crucial T705 1 TB, or Samsung 990 Pro in RAID 0        | Move to PCIe 5.0 (T705) → ~14,500 MB/s read vs 7,450 MB/s on 990 Pro                       |
| PSU        | 2000W Changcheng                                       | Unchanged                                                                                  |

### Verification

| Claim | Verdict | Note |
|:------|:-------:|:-----|
| `GENOAD12M-2Q` exists as ASRock Rack part number | ⚠️ | Single-socket SP5 boards from ASRock Rack exist (e.g. `GENOAD8X-2T`, `GENOAD8UD-2T/X550`). Verify the exact `GENOAD12M-2Q` SKU on ASRock Rack's site before ordering. |
| EPYC 9354 base clock (3.25 GHz) > 9124 (3.0 GHz) | ✅ | |
| EPYC 9454 has higher clock than 9124 | ❌ | 9454 base is **2.75 GHz**, *lower* than 9124. Core count is higher (48C), but the "higher clock" framing is wrong. |
| DDR5-5600 on EPYC 9004 (Genoa) | ⚠️ | Genoa is officially rated for **DDR5-4800** at 1 DPC. 5600 may run as overclock but is not guaranteed on EPYC server BIOS / QVL. |
| Crucial T705 ~14,500 MB/s vs 990 Pro ~7,450 MB/s | ✅ | Matches manufacturer specs. |

---

## Option 2 — Optimal (Single-Socket Turin + PCIe 5.0 RAID 0)

| Component  | Proposed Optimum                       | Why It's Faster & Cheaper                                                                                              |
|:-----------|:---------------------------------------|:-----------------------------------------------------------------------------------------------------------------------|
| CPU        | AMD EPYC 9355 (Turin)                  | 32C/64T Zen 5; ~15–20% IPC uplift over Genoa; higher clock than 9354 → keeps RTX 5090 from bottlenecking               |
| Mainboard  | Supermicro H13SSL-NT or Gigabyte ME03-CE0 | Dedicated single-socket SP5; Supermicro's stability is well known and pricing is friendlier than dual-socket boards |
| RAM        | 12× 64 GB DDR5-6000 ECC RDIMM          | **Key point:** Turin supports DDR5-6000 (vs 4800 on Genoa). Memory bandwidth improves by ~25%.                         |
| GPU        | RTX 5090                               | Unchanged                                                                                                              |
| SSD        | 2× Crucial T705 1 TB in RAID 0         | Two PCIe 5.0 drives in RAID 0 → ~28,000 MB/s sequential read. Feeds the 768 GB of RAM almost instantly.                |
| Heatsink   | Dynatron L31 or Noctua NH-D9 TR5-SP6 4U | Dynatron is server-grade and quieter than Coolserver; Noctua runs cooler and silent for focused work                  |
| PSU        | FSP Cannon Pro 2000W Platinum          | 80+ Platinum efficiency beats Changcheng → lower power bill and less waste heat                                        |

### Verification

| Claim | Verdict | Note |
|:------|:-------:|:-----|
| EPYC 9355 — 32C/64T Zen 5, base 3.55 GHz | ✅ | TDP 280 W. |
| Zen 5 IPC +15–20% vs Genoa | ✅ | AMD's published average is ~17% IPC. |
| 9355 clock (3.55 GHz) > 9354 (3.25 GHz) | ✅ | |
| Supermicro H13SSL-NT — single-socket SP5 | ✅ | Real product. |
| Gigabyte ME03-CE0 — single-socket SP5 | ✅ | Real product. |
| Turin supports DDR5-6000 (vs Genoa 4800), ~25% bandwidth uplift | ✅ | 6000/4800 = 1.25. |
| 2× T705 RAID 0 ~28,000 MB/s | ✅ (theoretical) | **No redundancy** — a single drive failure loses all data. Acceptable for scratch / dataset cache, not for OS / persistent state. |
| Noctua `NH-D9 TR5-SP6 4U` | ✅ | Real Noctua SKU for SP5/SP6 sockets (4U form factor). |
| Dynatron L31 for SP5 | ✅ | Real product. |
| FSP Cannon Pro 2000W Platinum | ✅ | Real; Platinum efficiency > typical Changcheng tier. |

---

## Option 3 — 3× H100 PCIe (LLM-First Build)

| Component  | Proposed Optimum                  | Reason                                                                                                                |
|:-----------|:----------------------------------|:----------------------------------------------------------------------------------------------------------------------|
| CPU        | AMD EPYC 9355 (Turin, 32C)        | 2026-class build → Zen 5. Plenty of PCIe 5.0 lanes to feed 3× H100.                                                   |
| Mainboard  | Supermicro H13SSL-NT              | PCIe slot spacing is wide enough for 3 thick cards                                                                    |
| GPU        | 3× NVIDIA H100 80GB (PCIe)        | 240 GB HBM3 total. Fewer cards = fewer failure points and lower power draw than 8× RTX 5090.                          |
| RAM        | 12× 64 GB DDR5-6000 ECC RDIMM     | Keep the 768 GB RAM to stream data into the H100s                                                                     |
| SSD        | 2× Crucial T705 1 TB (RAID 0)     | ~28 GB/s so data is never the bottleneck                                                                              |
| PSU        | FSP Cannon Pro 2000W Platinum     | 3× H100 ≈ 1050 W + CPU/board ~400 W → 2000 W is very safe                                                             |
| Case       | 4U / 7U Rackmount                 | H100 PCIe is **passively cooled** — needs a chassis with strong Delta/Sanyo front-to-back airflow.                    |

### Verification

| Claim | Verdict | Note |
|:------|:-------:|:-----|
| H100 PCIe 80 GB, 350 W, HBM3, passive cooled | ✅ | |
| 3 × 80 GB = 240 GB total VRAM | ✅ | |
| Power: 3×350 + ~400 = 1450 W on a 2000 W PSU | ✅ | ~28% headroom — safe. |
| H100 PCIe requires chassis airflow (passive heatsink) | ✅ | Mandatory rackmount with high-static-pressure fans. |
| H13SSL-NT slot pitch fits 3 thick cards | ⚠️ | H13SSL-NT has 3× PCIe 5.0 x16 slots, but slot spacing isn't ideal for 3 dual-slot cards with long heatsinks. OK on paper for H100 PCIe's 2-slot passive shroud; confirm against datasheet slot pitch and chassis riser layout. |
| 4U is enough for 3× H100 + cooling | ⚠️ | 4U is tight. **5U+** or a dedicated GPU chassis is the safer envelope for sustained thermal load. |
| Fewer cards / lower power than 8× RTX 5090 | ✅ | 3×350 = 1050 W vs 8×575 = 4600 W. Also far higher memory bandwidth per dollar for LLM serving. |

---

## Summary

- **Option 1** is a moderate refresh — keep DDR5-4800, swap to a faster Genoa CPU and PCIe 5.0 SSD. Cheapest of the three. Verify the exact ASRock Rack SKU and don't claim higher clock for 9454.
- **Option 2** is the strongest single-node workstation: Turin gives both clock and a real ~25% memory bandwidth jump, RAID 0 PCIe 5.0 hits ~28 GB/s, and Platinum PSU pays itself back over time. Watch the RAID 0 redundancy story and double-check the Noctua part number.
- **Option 3** is the LLM-serving build: 3× H100 PCIe gives 240 GB of HBM3 with far better memory bandwidth than any consumer GPU stack. Plan chassis airflow carefully; 5U is the safer floor.

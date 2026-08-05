# Bill of Materials

Quantities are per machine — one 8× GPU build. Part photos are in the [component checklist](../docs/prepare-ee.md).

| No  | Item                      | Detail                                     | Qty | Category   | Notes                                        |
|:---:|:--------------------------|:--------------------------------------------|:---:|:-----------|:---------------------------------------------|
|  1  | Mainboard                 | ASRock Rack GENOA2D24G-2L+                   |  1  | Mainboard  | Dual SP5, PCIe over MCIO                      |
|  2  | CPU                       | AMD EPYC 9004 series (Genoa)                 |  2  | Processor  | SP5 socket                                    |
|  3  | CPU heatsink              | SP5-compatible cooler                        |  2  | Cooling    |                                               |
|  4  | RAM                       | DDR5 ECC RDIMM                               |  4  | Memory     | Configurable 1–24 DIMMs                       |
|  5  | SSD                       | 1 TB NVMe                                    |  1  | Storage    | Capacity configurable                         |
|  6  | M.2 heatsink              | —                                            |  1  | Cooling    |                                               |
|  7  | GPU                       | NVIDIA RTX 4090 or 5090                      |  8  | Graphics   | 24 GB / 32 GB each — 192–256 GB total         |
|  8  | MCIO cable                | —                                            | 16  | Cable      | Two per GPU (x16 = 2× x8)                     |
|  9  | MCIO→PCIe adapter         | —                                            |  8  | Adapter    | One per GPU                                   |
| 10  | PSU                       | 2000 W CRPS                                  |  4  | Power      | 8000 W total                                  |
| 11  | PSU board                 | Power distribution board                     |  1  | Power      |                                               |
| 12  | Motherboard power cable   | Power-board-to-motherboard harness           |  1  | Cable      | 1 set                                         |
| 13  | GPU power cable           | 12V-2x6 / 12VHPWR, 600 W rated               |  8  | Cable      | One per GPU                                   |
| 14  | Fan                       | Case fan                                     | 12  | Cooling    |                                               |
| 15  | Fan hub                   | Fan control board                            |  1  | Cooling    |                                               |
| 16  | Chassis                   | 5U rack chassis kit                          |  1  | Housing    | Ships complete — [housing prep](../docs/prepare-me.md) |

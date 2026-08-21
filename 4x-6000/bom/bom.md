# Bill of Materials

Quantities are per machine — one 4× RTX PRO 6000 build. Lay every part out and check it off before assembly.

> Draft — component photos from this build are landing soon.

| No  | Item              | Detail                                          | Qty | Category   | Notes                                                                     |
|:---:|:------------------|:------------------------------------------------|:---:|:-----------|:--------------------------------------------------------------------------|
|  1  | Mainboard         | ASUS Pro WS W790E-SAGE SE                       |  1  | Mainboard  | Intel W790, LGA 4677; 7× PCIe 5.0 ×16                                     |
|  2  | CPU               | Intel Xeon w5-3423                              |  1  | Processor  | 12 cores, LGA 4677, 112 PCIe 5.0 lanes                                    |
|  3  | CPU heatsink      | Heatsink 4677-2UAF8                             |  1  | Cooling    | LGA 4677                                                                  |
|  4  | RAM               | 32 GB DDR5-4800 ECC                             |  6  | Memory     | 192 GB total; configurable 64–256 GB                                      |
|  5  | SSD               | 2 TB NVMe PCIe 4.0                              |  1  | Storage    | Configurable 1–8 TB; Gen 5 at 8 TB                                        |
|  6  | GPU               | NVIDIA RTX PRO 6000 Blackwell Workstation Edition |  4  | Graphics   | 96 GB GDDR7 ECC each — 384 GB total                                      |
|  7  | PCIe 5.0 riser    | PCIe 5.0 x16 riser cable                        |  4  | Cable      | One per GPU                                                               |
|  8  | PSU               | 2,000 W, native 12V-2x6                         |  2  | Power      | 4,000 W total; 240 V circuit required                                     |
|  9  | GPU power cable   | 12V-2x6 / 12VHPWR, 600 W rated                  |  4  | Cable      | One per GPU                                                               |
| 10  | Power cord        | Wall cord rated for the PSU                     |  2  | Cable      | One per supply                                                            |
| 11  | Fan               | 120 mm case fan                                 | 18  | Cooling    | Single controller                                                         |
| 12  | Frame housing     | Full housing set (printed or CNC)               |  1  | Housing    | CNC-machined solid aluminium; print the [STLs](../../4x-5090/stl-models) or CNC the [STEPs](../../4x-5090/step_models) |

Next: [housing prep](../docs/prepare-me.md) · [assembly](../docs/assembly.md).

# Bill of Materials

Quantities are per machine — one 2× RTX PRO 6000 build. Part photos are in the [component checklist](../docs/prepare-ee.md).

> This build shares the 2× 5090 platform and housing; only item 6 (the GPUs) differs.

| No  | Item              | Detail                                    | Qty | Category   | Notes                                        |
|:---:|:------------------|:------------------------------------------|:---:|:-----------|:---------------------------------------------|
|  1  | Mainboard         | ASUS W790 ACE                              |  1  | Mainboard  | Intel W790 chipset, LGA 4677                  |
|  2  | CPU               | Intel Xeon W5                              |  1  | Processor  | LGA 4677 socket                               |
|  3  | CPU heatsink      | LGA 4677-compatible cooler                 |  1  | Cooling    |                                               |
|  4  | RAM               | DDR5 48 GB                                 |  4  | Memory     | 192 GB total; configurable 1–8 DIMMs          |
|  5  | SSD               | 1 TB NVMe                                  |  1  | Storage    | Capacity configurable                         |
|  6  | GPU               | NVIDIA RTX PRO 6000 Blackwell Workstation Edition |  2  | Graphics   | 96 GB GDDR7 ECC each — 192 GB total    |
|  7  | PCIe 5.0 riser    | PCIe 5.0 x16 riser cable                   |  2  | Cable      | One per GPU                                   |
|  8  | PSU               | 1600 W                                     |  1  | Power      | 600 W per card — confirm headroom on your wall circuit |
|  9  | GPU power cable   | 12V-2x6 / 12VHPWR, 600 W rated             |  2  | Cable      | One per GPU                                   |
| 10  | Power cord        | Wall cord rated for the PSU                |  1  | Cable      |                                               |
| 11  | Fan               | Case fan                                   |  4  | Cooling    |                                               |
| 12  | Frame housing     | Full housing set                           |  1  | Housing    | Same as the 2× 5090 — print the [STLs](../../2x-5090/stl-models) or CNC the [STEPs](../../2x-5090/step_models) |

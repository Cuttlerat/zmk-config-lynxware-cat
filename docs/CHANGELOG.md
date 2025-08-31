# Overview
This project ports the Lynxware Cat to ZMK and makes it wireless. It also experiments with Kailh Mute switches and replaces the mouse sensor with PMW3610. Some 3D models were modified to accommodate the new hardware, the updated models are available in the [STL directory](../stl).
 
_This changelog lists only differences from the main DIY manual. For baseline instructions, see the [Lynxware DIY manual](https://www.lynxware.org/diy)._ 

## Full changelog
- Used ZMK instead of Lynxware Cat default firmware
- Wireless via Nordic ESB and dedicated dongle
  - Dongle acts as the central and listens for input events.
- Hardware migration and sensor integration
  - Target board migrated to `nice_nano_v2` (nRF52840).
  - Mouse sensor changed to PMW3610.
  - JST-XH 2.54 instead of DuPont connectors and pins.
  - No LEDs due to insufficient pins on the nRF board.
- Switches and mechanics
  - Kailh Mute switches evaluated for quieter actuation and reduced noise.
  - Plate/keycap tolerances adjusted.
- 3D model updates
  - Modifications to fit Nice!Nano v2, PMW3610 PCB, and ESB dongle.
  - Added spacers on front and thumb panels to ensure clearance between panel and PCB.
  - Buttons with increased tolerances.
- Mouse skates changed to a modern gaming type (6 mm diameter), mounted to the case bottom (not into skate/pad pockets)

## Bill of Materials (only changes)

| Item | Change | Specification | Qty | Notes | Links |
| --- | --- | --- | --- | --- | --- |
| Controller | Replace default controller with Nice!Nano v2; add dedicated dongle | Nice!Nano v2 (nRF52840) or compatible | 3 | | |
| Batteries | Add per-side Li-ion battery | Li-ion 102530 800 mAh | 2 |  | |
| JST connectors | Use JST-XH 2.54 instead of DuPont | 2x4-pin, 2x6-pin, 2x10-pin |  |  | |
| Mouse sensor | Replace mouse sensor with PMW3610 | PMW3610 PCB | 1 |  | [PMW3610 PCB](https://github.com/siderakb/pmw3610-pcb) |
| Switches | Use Kailh Mute switches | Kailh Mute | 64 | 62 for default buttons and 2 for reset buttons | |
| Mouse skates | Use modern gaming skates mounted to case bottom | 6 mm diameter | 10 | Mounted to case bottom; not into skate/pad pockets | |
| Case parts | Modify 3D-printed case/plates (spacers, tolerances) | 3D-printed | set |  | [STL directory](../stl) |


## Pinout 

<details>
<summary>Thumb cluster (buttons)</summary>

| Name | Pin |
| --- | --- |
| Ti4 | P0.31 |
| Ti3 | P0.29 |
| Ti2 | P0.02 |
| Ti1 | P1.15 |
| To3 | P1.13 |
| To2 | P1.11 |
| To1 | P0.10 |

</details>

<details>
<summary>Gamepad (WIP)</summary>

| Name | Pin |
| --- | --- |
| JV | P0.31 |
| JY | P0.29 |
| JX | P0.02 |
| Ti2 | P1.15 |
| Ti1 | P1.13 |
| To3 | P1.11 |
| To2 | P0.10 |
| To1 | P0.06 |

</details>

<details>
<summary>Front panel - Right</summary>

| Name | Pin |
| --- | --- |
| Fi1 | P0.09 |
| Fi2 | P1.07 |
| Fi3 | P1.02 |
| Fi4 | P1.01 |
| Fo1 | P1.06 |
| Fo2 | P1.04 |
| Fo3 | P0.11 |
| Fo4 | P1.00 |
| Fo5 | P0.24 |
| Fo6 | P0.08 |

</details>

<details>
<summary>Front panel - Left</summary>

| Name | Pin |
| --- | --- |
| Fi1 | P0.09 |
| Fi2 | P1.07 |
| Fi3 | P1.02 |
| Fi4 | P1.01 |
| Fo6 | P1.06 |
| Fo5 | P1.04 |
| Fo4 | P0.11 |
| Fo3 | P1.00 |
| Fo2 | P0.24 |
| Fo1 | P0.08 |

</details>

<details>
<summary>Mouse Sensor</summary>

| Signal | Pin |
| --- | --- |
| SCK | P0.17 |
| MOSI | P0.20 |
| MISO | P0.20 |
| CS | P0.06 |
| IRQ | P0.22 |

</details>

## 3D printing
**Printer**: Bambu Lab P1S

| Part | Material | Nozzle | Layer height | Notes |
| --- | --- | --- | --- | --- |
| Case | ERYONE PETG-CF Black | 0.4 mm hardened | 0.2 mm | Cheaper alternative to Bambu Lab PETG-CF |
| Buttons | Bambu Lab PETG-HF Black | 0.4 mm hardened | 0.08 mm | |
| Other parts | Bambu Lab PLA Maroon Red | 0.4 mm hardened | 0.2 mm | |


## Known issues
- Button keycaps are not secure and can be jiggly; consider shimming or alternative keycaps.
- Some buttons can stick and repeat due to ESB transport behavior; pressing the dongle's reset button resolves it.


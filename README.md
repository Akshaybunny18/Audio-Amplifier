# Audio Amplifier — EW-II Project 1

**IIIT-Hyderabad | Table 5, Room N-104**
**Akshay Chanda (2024102014) & S V Santhosh Yadav (2024102054)**

---

## Overview

A four-stage audio amplifier designed, simulated in LTspice, and verified on hardware. Takes a 10–20 mVpp electret microphone signal and delivers ~0.98 W into a 10 Ω speaker load across the full audible range.

The four stages are:
1. **Differential Pre-Amplifier** — BC547B diff pair, G1 ≥ 2
2. **Common-Emitter Gain Stage** — BC547B, G2 ≈ 33 (G1 × G2 ≈ 500)
3. **Active Band-Pass Filter** — UA741 inverting BPF, 20 Hz–20 kHz, unity gain
4. **Class-AB Push-Pull Power Amplifier** — TIP31A/TIP32A, ~0.968 W into 10 Ω

For full design derivations, calculations, simulation results, and hardware measurements, see [`Report_Audio-Amplifier.pdf`](Report_Audio-Amplifier.pdf).

---

## Key Specifications

| Parameter | Value |
|---|---|
| Supply | ±5 V (stages 1, 2, 4) / ±12 V (stage 3 op-amp) |
| Input | 10–20 mVpp (electret microphone) |
| Total voltage gain | ~500 (~54 dB) |
| Bandwidth | 20 Hz – 20 kHz |
| Output power | ~0.968 W into 10 Ω |
| THD | ~4.8% |

---

## Repository Structure

```
Audio_Amplifier/
├── main.tex                           # LaTeX source for the project report
├── Report_Audio-Amplifier.pdf         # Compiled PDF report
├── Project1EW-II_Problem_Statement.pdf
├── Video.mp4                          # Hardware demo video
├── LT_Spice/
│   ├── stage1.asc                     # Stage 1 schematic
│   ├── stage2.asc                     # Stage 2 schematic
│   ├── stage3.asc                     # Stage 3 schematic
│   ├── stage4.asc                     # Stage 4 schematic
│   ├── pre_final.asc / final.asc      # Combined circuit schematics
│   ├── bill_of_materials.txt
│   ├── UA741.301                      # UA741 SPICE model
│   └── tip31a.lib / tip32a.lib        # Power transistor SPICE models
└── images/                            # All figures used in the report
```

To open simulations, load any `.asc` file in LTspice with the `.lib`/`.301` model files in the same `LT_Spice/` directory.

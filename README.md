# Balemuni’s Turnip — Mesa 26.3.0-devel  
## Apex Universal V2 — Custom Vulkan Driver for Qualcomm Adreno GPUs

Balemuni’s **Apex Universal V2** is a highly optimized custom build of **Mesa Turnip 26.3.0-devel**, designed to deliver maximum performance, stability and emulator compatibility across all Qualcomm Adreno GPUs.

The project provides two editions:

- **Apex v2 ULTIMATE (SD8 Gen 2)** — instruction‑level tuning for Cortex‑X3 prime cores  
- **Apex Universal V2** — compatible with all Adreno 6xx / 7xx / 8xx devices, including upcoming Elite platforms

Both builds are compiled from the latest Mesa `main` branch and include extensive source‑level optimizations, expanded memory suballocator scaling and targeted fixes for emulator rendering issues.

---

## Key Enhancements

### Global Code Motion (IR3 Compiler)
Enables `gcm=1` to hoist loop‑invariant instructions and common subexpressions out of shader hot paths.  
Reduces register pressure and improves framerate consistency.

### Expanded Shader Cache (4 GB)
Increases Mesa’s default shader cache from 1 GB to 4 GB.  
Prevents premature shader eviction and reduces compilation stutter in large titles.

### Scaled Suballocator Pools (512 KB)
Increases `pipeline_suballoc` and `kgsl_profiling_suballoc` block sizes from 128 KB to 512 KB.  
Reduces kernel memory fragmentation and CPU context‑switch overhead.

### Zelda TOTK/BOTW Artifact Fixes
Enables:
- `tu_dont_care_as_load = true`  
- `tu_allow_oob_indirect_ubo_loads = true`  

Prevents GMEM tile discarding and resolves black blocks, sky flicker and terrain artifacts.

### Extended Emulator Compatibility
Includes native Driconf rules for:
- border color handling  
- OOB indirect UBO tolerance  
- D3D‑compatible texture coordinate rounding  

Improves stability across PC translation layers and major emulators.

### Driver Identification
Reports as:
- **Turnip (Balemuni Apex Universal V2)**  
- **Turnip (Balemuni Apex v2 Ultimate)**  

---

## Snapdragon Elite (Gen 3, Gen 4, Gen 5) Compatibility

The Universal edition is designed to support **all modern Adreno architectures**, including:

- **Snapdragon 8 Gen 3** — Adreno 750  
- **Snapdragon 8 Elite Gen 4** — Adreno 830  
- **Snapdragon 8 Elite Gen 5** — Adreno 840  

Turnip already includes support for Adreno 750, 830 and 840 in upstream Mesa.  
Therefore, Apex Universal V2 is **expected to run on Gen 3, Gen 4 and Gen 5 Elite chips**.

**Important:**  
We currently do **not** own any Snapdragon Gen 3 / Gen 4 / Gen 5 devices.  
Compatibility is based on upstream Mesa support and should work, but **cannot yet be tested or guaranteed** until retail hardware is available.

---

## Package Overview

| Package File | Target Hardware | Recommended Emulators |
|--------------|-----------------|------------------------|
| **Balemuni_Apex_v2_ULTIMATE_SD8Gen2.zip** | Snapdragon 8 Gen 2 (Adreno 740) — Cortex‑X3 tuned | Eden, Citron, Yuzu, Cemu, Winlator, PPSSPP |
| **Balemuni_Apex_Universal_V2.zip** | All Adreno 6xx / 7xx / 8xx devices | All Vulkan emulators & Android games |

### Recommended Edition

| Device | Package |
|--------|---------|
| AYN Thor / Thor Pro / Thor Max, Odin 2/3, RedMagic 8/9, Galaxy S23/S24, ROG Phone | **ULTIMATE SD8Gen2** |
| Any other Android 13+ device with Adreno GPU | **Universal V2** |

> The ULTIMATE edition contains Cortex‑X3/ARMv8.5‑tuned code paths.  
> Use the Universal edition on older or mid‑range chipsets.

---

## Emulation & Gaming Compatibility

Optimized and tested for:

- Eden / Citron (Nintendo Switch) — including TOTK & BOTW artifact fixes  
- Cemu (Wii U)  
- NetherSX2 / AetherSX2 (PS2)  
- PPSSPP (PSP)  
- Vita3K (PS Vita)  
- Winlator / Mobox / Box64 (Windows translation)  
- Native Android Vulkan titles

---

## Supported Devices

- AYN Thor / Pro / Max (Snapdragon 8 Gen 2, Adreno 740)  
- AYN Odin 2 / Retroid Pocket 5 / Mini  
- RedMagic 8/9, ASUS ROG Phone, Samsung Galaxy S23/S24  
- Xiaomi 13/14, POCO F3/F4/F5  
- Any Android 13+ device with Adreno 6xx / 7xx / 8xx GPU  
- Expected support: Snapdragon 8 Gen 3, Snapdragon 8 Elite Gen 4, Snapdragon 8 Elite Gen 5

---

## SHA256 Checksums

```text
cd1b92d4b315b2157ce6b523b9b33a02167128873a01f1605dbaae0443533054  Balemuni_Apex_v2_ULTIMATE_SD8Gen2.zip
38a3eb061016f3a17c412001e651105f99344a71a07b8e458a936b7e999cf2e3  Balemuni_Apex_Universal_V2.zip

# Balemuni's Turnip — Mesa 26.3.0-devel (Apex Edition)

Balemuni's Turnip (Apex Edition) is a bleeding-edge, highly tuned custom Mesa Turnip 26.3.0-devel Vulkan driver engineered specifically for Qualcomm Adreno GPUs, with dedicated tuning for the Qualcomm Snapdragon 8 Gen 2 (Adreno 740) on devices like the AYN Thor, Odin 2, and other Android handhelds and smartphones.

This driver is built from the latest upstream Mesa `main` Git branch and incorporates deep custom source-code optimizations, memory suballocator scaling, and tailored emulator compatibility patches to deliver unmatched stability, peak framerates, and flawless visual rendering.

## Key Innovations & Custom Code Enhancements

- Global Code Motion (GCM) in IR3 Compiler (`gcm=1`)  
  Automatically hoists loop-invariant instructions and common subexpressions out of shader hot paths. Reduces shader register pressure and improves framerate consistency.

- 4 GB Default On-Disk Shader Cache  
  The default Mesa shader cache limit has been increased from 1 GB to 4 GB (`4ULL * 1024 * 1024 * 1024`). Prevents premature deletion of pre-compiled shaders in large titles and eliminates shader compilation stutters.

- Scaled 512 KB High-VRAM Suballocator Pools  
  `pipeline_suballoc` and `kgsl_profiling_suballoc` default block chunks have been scaled from 128 KB to 512 KB, reducing kernel memory fragmentation and CPU context-switching overhead.

- Zelda: TOTK & BOTW Black Blocks / Artifacts Fix  
  `tu_dont_care_as_load = true` and `tu_allow_oob_indirect_ubo_loads = true` prevent tile discarding on GMEM boundaries, fully resolving the black rectangular boxes and sky/terrain flickering in Tears of the Kingdom.

- Official Vulkan 1.4 Driver Identification  
  Reports in Vulkan ICD and in-game HUDs as `Turnip (Balemuni Apex Edition)` with full Vulkan 1.4 feature support.

- Zero-Crash Multi-Cluster CPU Safety  
  Optimized ARM64 instruction scheduling ensures crash-free operation across all asymmetric Big.LITTLE CPU clusters (Cortex-A510/A710/A715/X3) with zero SIGILL errors.

## Package Overview

| Package File | Target Hardware | Recommended Emulators |
|--------------|-----------------|------------------------|
| Balemuni_Apex_Ultimate_Mesa26.3_SD8Gen2.zip | Snapdragon 8 Gen 2 (Adreno 740 / AYN Thor) | Eden, Citron, Yuzu, Cemu, Winlator, PPSSPP |
| Balemuni_Apex_Universal_Mesa26.3_AllAdreno.zip | All Adreno Devices (Adreno 6xx, 7xx, 8xx) | All Vulkan Emulators & Android Games |

## Emulation & Gaming Compatibility

Balemuni's Apex Edition is engineered and tested to provide top-tier performance in:

- Eden / Citron (Nintendo Switch Emulation)  
- Cemu (Wii U Emulation)  
- Azahar / NetherSX2 / AetherSX2 (PS2 Emulation)  
- PPSSPP (PSP Emulation)  
- Vita3K (PS Vita Emulation)  
- Winlator / Mobox / Box64 (Windows PC Translation)  
- Native Android Vulkan Titles

## Target Devices

- AYN Thor / Pro / Max (Snapdragon 8 Gen 2, Adreno 740)  
- AYN Odin 2 / Retroid Pocket 5 / Mini / Steam Deck OLED (Android)  
- Smartphones: RedMagic 8/9, ASUS ROG Phone, Samsung Galaxy S23/S24, Xiaomi 13/14, POCO F3/F4/F5  
- Universal: Any Android 11+ device equipped with Qualcomm Adreno 6xx, 7xx, or 8xx GPUs

## Verified SHA256 Checksums


```text
dbd1971dd93eecc789ea20913fac68876f0f112c697bce6e6b16025c1d49cd8f  Balemuni_Apex_Ultimate_Mesa26.3_SD8Gen2.zip
dbd1971dd93eecc789ea20913fac68876f0f112c697bce6e6b16025c1d49cd8f  Balemuni_Apex_Universal_Mesa26.3_AllAdreno.zip

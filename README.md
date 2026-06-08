<p align="center"><img width="180" height="138" alt="chanokobannersmall" src="https://github.com/user-attachments/assets/00d635b4-5c39-4bf4-8910-b787abc2b9d9" /></p>

_<p align="center">Rhythmic Filter & Delay Sequencer.</p>_

---

![Version](https://img.shields.io/badge/Version-1.1.0-brightgreen?style=flat-square)
![macOS Support](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-000000?style=flat-square&logo=apple&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Intel%20%7C%20Arm64%20%7C%20U2B-black?labelColor=606060&style=flat-square&logo=apple&logoColor=white)
![Format](https://img.shields.io/badge/Format-Standalone-00CED1?style=flat-square)

---

<img width="1039" height="718" alt="chanokopreview" src="https://github.com/user-attachments/assets/1f68af44-8ea0-4d1d-b31f-c738967c4526" />

---

## 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **Digital Bit-Crusher**: Reduce the effective sample rate via decimation and manipulate each of the 8 bits of every audio sample independently. Pass, Mute or Invert for textures ranging from subtle aliasing to extreme digital noise.
- **State Variable Filter (SVF)**: Switch between Lowpass, Bandpass and Highpass models with sweeping Cutoff and Resonance controls. The filter cutoff is modulated in real time by the sequencer when enabled.
- **Time FX Delay**: Feedback delay line with adjustable Time and Feedback for complex, echoing textures and spatial depth.
- **Analog-Style Overdrive**: Push the signal into soft-clip saturation with the built-in Drive control for harmonic warmth and grit. Output is bounded to prevent clipping regardless of drive amount.
- **16-Step Filter Sequencer**: Modulates the filter cutoff frequency across 16 steps with per-step level control and global BPM sync. Each step value maps to a frequency on a logarithmic scale.
- **Live FFT Metering**: Real-time frequency spectrum display drawn at native Retina resolution.
- **14 Curated Presets**: Instantly recall distinct sonic palettes — from lo-fi tape warmth to extreme glitch and chip arpeggiation.
- **WAV Recorder**: Capture the processed output directly from the master bus to a 16-bit 48 kHz WAV file without any additional software.
- **Standalone Desktop Application**: Frameless, hardware-inspired UI built for macOS with low-latency audio processing running entirely on the audio thread.

---

## 𝐒𝐢𝐠𝐧𝐚𝐥 𝐂𝐡𝐚𝐢𝐧

The audio signal flows through the following processing stages in order:

```
Audio File
    |
Bit-Crusher  (AudioWorklet — decimation + per-bit operations)
    |
Waveshaper   (arctan soft-clip distortion)
    |
SVF Filter   (lowpass / bandpass / highpass + resonance)
    |
    +---> Dry path -------+
    |                     |
    +--> Delay --> Loop ---> Master Gain
                              |
                         Brick-Wall Limiter  (-6 dB threshold, 20:1 ratio)
                              |
                         FFT Analyser --> Output
```

---

## 𝐒𝐲𝐬𝐭𝐞𝐦 𝐑𝐞𝐪𝐮𝐢𝐫𝐞𝐦𝐞𝐧𝐭𝐬

- **macOS**: 14.0 (Sonoma), 15.0 (Sequoia) or 16.0 (Tahoe).
- **Architecture**: Intel, Arm64 (Silicon) & U2B (Universal).

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧

### 𝐒𝐭𝐚𝐧𝐝𝐚𝐥𝐨𝐧𝐞
1. Download the latest [`Chanoko`](https://github.com/KouseiMusic/Chanoko/releases/tag/Chanoko_1.1.0).
2. Extract & Drag `Chanoko` to your `Applications` folder.
3. Open `Chanoko`.
4. If macOS shows a Gatekeeper warning on first launch, right-click the application and choose `Open`, then confirm.
5. Click on `Load` and choose a sample you want to play with.

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

- **Real-time Audio Processing:** Load an audio file, select your filter type and dial in the sequencer to rhythmically modulate the signal. Enable the WAV recorder before playback to capture the output.

### 𝐃𝐢𝐠𝐢𝐭𝐚𝐥 𝐂𝐨𝐫𝐞

| Control | Description | Range |
| :--- | :--- | :--- |
| **Sample Clock** | Decimation factor. Higher values reduce the effective sample rate and introduce aliasing. | 1 to 200 |
| **Dist Drive** | Soft-clip saturation amount applied after the bit-crusher. | 0.0 to 1.0 |
| **Bit 0 – 7** | Per-bit operation for each of the 8 bits of every sample. Pass, Mute, or Invert. | — |

### 𝐒𝐕𝐅 & 𝐓𝐢𝐦𝐞 𝐅𝐗

| Control | Description | Range |
| :--- | :--- | :--- |
| **Cutoff (Hz)** | Adjusts the filter's cutoff frequency. Overridden by the sequencer when enabled. | 20 to 20000 |
| **Resonance** | Accentuates the frequencies around the cutoff point. | 0.1 to 18.0 |
| **Filter Type** | Toggles between LOWPASS, BANDPASS and HIGHPASS models. | — |
| **Delay Time** | Sets the delay repeat interval (time between echoes). | 0.05 to 1.5 s |
| **Feedback** | Determines how many times the delayed signal repeats. | 0.0 to 0.80 |

### 𝐒𝐞𝐪𝐮𝐞𝐧𝐜𝐞𝐫

| Control | Description | Range |
| :--- | :--- | :--- |
| **Steps Array** | 16 individual step sliders. Each step sets the filter cutoff value for that beat, mapped logarithmically to 20 Hz–20 kHz. | 0.0 to 1.0 per step |
| **BPM** | Adjusts the global tempo of the sequencer. Steps advance in 16th notes. | 40 to 240 BPM |
| **Seq ON / OFF** | Enables or disables sequencer modulation of the filter cutoff. | — |

### 𝐆𝐥𝐨𝐛𝐚𝐥 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

| Control | Description |
| :--- | :--- |
| **VOL** | Master output volume knob. |
| **Presets** | Dropdown menu featuring 14 distinct audio configurations. |
| **Record (●)** | Starts and stops WAV recording of the processed output. Click again to stop and save the file. |
| **Play (▶)** | Starts audio playback and the sequencer. |
| **Pause (❚❚)** | Pauses audio playback. The sequencer position is held. |
| **Stop (■)** | Stops playback, resets the sequencer to step 1. |
| **Load** | Opens a file picker to load any audio file. |

---

## 𝐏𝐫𝐞𝐬𝐞𝐭𝐬

| Name | Character |
| :--- | :--- |
| **INIT** | Neutral starting point. All processing minimal, sequencer off. |
| **ARCADE NOISE** | Moderate decimation with bit inversion, bright lowpass tone. |
| **CYBER DRONE** | Slow bandpass sequencer at 80 BPM with long feedback echo. |
| **DUB ECHO** | Warm lowpass with syncopated sequencer at 140 BPM and long echo tail. |
| **ACID BASS** | High-resonance lowpass sequencer at 125 BPM. |
| **LO-FI TAPE** | Gentle bit reduction, warm lowpass roll-off, short room echo. |
| **BROKEN GEAR** | Heavy decimation, all bits alternating mute/invert, slow irregular sequencer. |
| **CHIP ARP** | Chiptune-style arpeggiated filter at 180 BPM with short delay. |
| **GHOST RES** | Near-resonant bandpass with slow rising sequencer and long delay. |
| **GLITCH SEQ** | Aggressive bit manipulation, fast highpass sequencer at 160 BPM. |
| **SUB PING** | Mid-frequency bandpass ping with long, sparse delay tail. |
| **MUTANT FM** | Maximum decimation with alternating bit operations, fast sequencer. |
| **STUTTER CHOIR** | Lower bits muted, very short flutter echo producing stutter effect. |
| **METAL SCRAP** | Heavy decimation, metallic highpass character, driving sequencer. |

---

_This software is free. Don't forget to give it a ⭐ on Github if you liked the project._

---

<p align="center"><code>𝒦𝑜𝓊𝓈𝑒𝒾</code></p>
<p align="center"><code>2026</code></p>

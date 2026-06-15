<p align="center"><img width="180" height="138" alt="chanokobannersmall" src="https://github.com/user-attachments/assets/00d635b4-5c39-4bf4-8910-b787abc2b9d9" /></p>

**_<p align="center">Séquenceur de Distorsion, Filtre Rythmique et Delay.</p>_**

---

![Version](https://img.shields.io/badge/Version-1.1.0-brightgreen?style=flat-square)
![macOS Support](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-000000?style=flat-square&logo=apple&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Intel%20%7C%20Arm64%20%7C%20U2B-black?labelColor=606060&style=flat-square&logo=apple&logoColor=white)
![Format](https://img.shields.io/badge/Format-Standalone-00CED1?style=flat-square)
![DAW](https://img.shields.io/badge/DAW-Ableton%20Live%2012%2B-000000?style=flat-square&logo=abletonlive&logoColor=white)

---

<img width="1039" height="718" alt="chanokopreview" src="https://github.com/user-attachments/assets/1f68af44-8ea0-4d1d-b31f-c738967c4526" />

---

## 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **Digital Bit-Crusher** : Réduisez la fréquence d'échantillonnage effective via décimation et manipulez chacun des 8 bits de chaque échantillon audio de manière indépendante. Pass, Mute ou Invert pour des textures allant d'un aliasing subtil au bruit numérique extrême.
- **State Variable Filter (SVF)** : Basculez entre les modèles Lowpass, Bandpass et Highpass avec des contrôles de balayage Cutoff et Resonance. La fréquence de coupure du filtre est modulée en temps réel par le sequencer lorsqu'il est activé.
- **Time FX Delay** : Ligne de delay à feedback avec Time et Feedback ajustables pour des textures complexes, des échos et de la profondeur spatiale.
- **Analog-Style Overdrive** : Poussez le signal dans une saturation soft-clip avec le contrôle Drive intégré pour obtenir de la chaleur harmonique et du grain. La sortie est limitée pour éviter tout clipping quel que soit le niveau de drive.
- **16-Step Filter Sequencer** : Module la fréquence de coupure du filtre sur 16 pas avec un contrôle de niveau par pas et une synchronisation BPM globale. Chaque valeur de pas correspond à une fréquence sur une échelle logarithmique.
- **Live FFT Metering** : Affichage du spectre fréquentiel en temps réel avec une résolution Retina native.
- **14 Curated Presets** : Rappelez instantanément des palettes sonores distinctes : de la chaleur d'une bande lo-fi au glitch extrême et aux arpèges chiptune.
- **WAV Recorder** : Capturez la sortie traitée directement depuis le master bus dans un fichier WAV 16 bits 48 kHz sans logiciel supplémentaire.
- **Standalone Desktop Application** : Interface sans cadre inspirée par le hardware, conçue pour macOS avec un traitement audio à faible latence tournant entièrement sur le thread audio.

---

## 𝐒𝐲𝐬𝐭𝐞𝐦 𝐑𝐞𝐪𝐮𝐢𝐫𝐞𝐦𝐞𝐧𝐭𝐬

- **macOS** : 14.0 (Sonoma), 15.0 (Sequoia) ou 16.0 (Tahoe).
- **Architecture** : Intel (x64), Silicon (x64) et Universal (U2B).
- **DAW (Mode plugin)** : Ableton Live 12 ou 11, Logic Pro, Reason avec le pilote audio virtuel [BlackHole](https://github.com/ExistentialAudio/BlackHole) pour le routage DAW en mode standalone.
> Les formats de plugins Audio Unit (AU) et VST3 sont actuellement en cours de développement.

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧

### 𝐒𝐭𝐚𝐧𝐝𝐚𝐥𝐨𝐧𝐞
1. Téléchargez la dernière version de [`Chanoko`](https://github.com/KouseiMusic/Chanoko/releases/download/Chanoko_1.1.0/Chanoko.1.1.0.macOS.Universal.zip).
2. Extrayez et glissez `Chanoko` dans votre dossier `Applications`.
3. Ouvrez `Chanoko`.
4. Si macOS affiche un avertissement Gatekeeper au premier lancement, faites un clic droit sur l'application et choisissez `Ouvrir`, puis confirmez.
5. Cliquez sur `Load` et choisissez un échantillon audio avec lequel vous voulez jouer.

### 𝐀𝐮𝐝𝐢𝐨 𝐔𝐧𝐢𝐭 (𝐀𝐔)

> En cours de développement

### 𝐕𝐒𝐓𝟑

> En cours de développement

## 𝐃𝐀𝐖 𝐔𝐬𝐚𝐠𝐞

1. Installez [`BlackHole`](https://github.com/ExistentialAudio/BlackHole), un pilote audio virtuel gratuit pour macOS.
2. Ouvrez `Configuration audio et MIDI` (dans `/Applications/Utilitaires/`).
3. Créez un `Appareil à sorties multiples` qui inclut à la fois votre `Interface Audio` et `BlackHole`.
4. Définissez cet `Appareil à sorties multiples` comme sortie système dans `Réglages Système` > `Son`.
5. Dans votre `DAW`, créez une piste d'entrée audio et réglez sa source d'entrée sur `BlackHole`.
6. Vous pouvez maintenant enregistrer ou monitorer la sortie de `Chanoko` en temps réel.

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

- **Traitement audio en temps réel :** Chargez un fichier audio, sélectionnez votre type de filtre et réglez le sequencer pour moduler le signal de manière rythmique. Activez le WAV recorder avant la lecture pour capturer la sortie.

### 𝐃𝐢𝐠𝐢𝐭𝐚𝐥 𝐂𝐨𝐫𝐞

| Control | Description | Range |
| :--- | :--- | :--- |
| **Sample Clock** | Facteur de décimation. Les valeurs élevées réduisent la fréquence d'échantillonnage effective et introduisent de l'aliasing. | 1 à 200 |
| **Dist Drive** | Quantité de saturation soft-clip appliquée après le bit-crusher. | 0.0 à 1.0 |
| **Bit 0 - 7** | Opération par bit pour chacun des 8 bits de chaque échantillon. Pass, Mute ou Invert. | - |

### 𝐒𝐕𝐅 & 𝐓𝐢𝐦𝐞 𝐅𝐗

| Control | Description | Range |
| :--- | :--- | :--- |
| **Cutoff (Hz)** | Ajuste la fréquence de coupure du filtre. Outrepassé par le sequencer lorsqu'il est activé. | 20 à 20000 |
| **Resonance** | Accentue les fréquences autour du point de coupure. | 0.1 à 18.0 |
| **Filter Type** | Bascule entre les modèles LOWPASS, BANDPASS et HIGHPASS. | - |
| **Delay Time** | Définit l'intervalle de répétition du delay (temps entre les échos). | 0.05 à 1.5 s |
| **Feedback** | Détermine le nombre de répétitions du signal retardé. | 0.0 à 0.80 |

### 𝐒𝐞𝐪𝐮𝐞𝐧𝐜𝐞𝐫

| Control | Description | Range |
| :--- | :--- | :--- |
| **Steps Array** | 16 curseurs de pas individuels. Chaque pas définit la valeur de coupure du filtre pour ce temps, mappée de façon logarithmique de 20 Hz à 20 kHz. | 0.0 à 1.0 par pas |
| **BPM** | Ajuste le tempo global du sequencer. Les pas avancent en doubles croches (16th notes). | 40 à 240 BPM |
| **Seq ON / OFF** | Active ou désactive la modulation du filtre par le sequencer. | - |

### 𝐆𝐥𝐨𝐛𝐚𝐥 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

| Control | Description |
| :--- | :--- |
| **VOL** | Bouton de volume de sortie général. |
| **Presets** | Menu déroulant proposant 14 configurations audio distinctes. |
| **Record (●)** | Démarre et arrête l'enregistrement WAV de la sortie traitée. Cliquez à nouveau pour arrêter et sauvegarder le fichier. |
| **Play (▶)** | Lance la lecture audio et le sequencer. |
| **Pause (❚❚)** | Met en pause la lecture audio. La position du sequencer est conservée. |
| **Stop (■)** | Arrête la lecture et réinitialise le sequencer au pas 1. |
| **Load** | Ouvre un sélecteur de fichiers pour charger n'importe quel fichier audio. |

---

## 𝐏𝐫𝐞𝐬𝐞𝐭𝐬

| Name | Character |
| :--- | :--- |
| **INIT** | Point de départ neutre. Traitement minimal et sequencer désactivé. |
| **ARCADE NOISE** | Décimation modérée avec inversion de bits et tonalité lowpass brillante. |
| **CYBER DRONE** | Sequencer bandpass lent à 80 BPM avec un long écho de feedback. |
| **DUB ECHO** | Lowpass chaud avec sequencer syncopé à 140 BPM et longue queue d'écho. |
| **ACID BASS** | Sequencer lowpass à haute résonance à 125 BPM. |
| **LO-FI TAPE** | Légère réduction de bits, atténuation lowpass chaleureuse et court écho de pièce. |
| **BROKEN GEAR** | Forte décimation, tous les bits alternant entre mute/invert et sequencer lent irrégulier. |
| **CHIP ARP** | Filtre arpégé de style chiptune à 180 BPM avec delay court. |
| **GHOST RES** | Bandpass proche de la résonance avec sequencer montant lent et long delay. |
| **GLITCH SEQ** | Manipulation de bits agressive et sequencer highpass rapide à 160 BPM. |
| **SUB PING** | Ping bandpass à fréquence moyenne avec une queue de delay longue et éparse. |
| **MUTANT FM** | Décimation maximale avec opérations de bits alternées et sequencer rapide. |
| **STUTTER CHOIR** | Bits inférieurs coupés et très court écho flottant produisant un effet de bégaiement. |
| **METAL SCRAP** | Forte décimation, caractère highpass métallique et sequencer entraînant. |

---

## 𝐒𝐢𝐠𝐧𝐚ｌ 𝐂𝐡𝐚𝐢𝐧

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          CHANOKO SIGNAL PATH                            │
└─────────────────────────────────────────────────────────────────────────┘

  AUDIO FILE
  (WAV / AIFF / MP3 / AAC / FLAC)
       │
       ▼
┌─────────────┐
│ BIT-CRUSHER │  Traitement basé sur AudioWorklet.
│             │  Décimation (Sample Rate) + Opérations par Bit.
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ WAVESHAPER  │  Distorsion Arctan Soft-Clip.
│             │  Saturation non linéaire et mise en forme harmonique.
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ SVF FILTER  │  Filtre à état variable (LP / BP / HP).
│             │  Contrôle de fréquence résonante et pente.
└──────┬──────┘
       │
       ├──────────────────────────────────────┐
       │                                      │
       ▼                                      ▼
  (Dry Path)                        ┌─────────────────────────────────┐
       │                            │           DELAY UNIT            │
       │                            │  Répétition du signal           │
       │                            │  avec boucle de Feedback.       │
       │                            └─────────────────┬───────────────┘
       │                                              │
       │                                              │
       ▼                                              ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                               MASTER GAIN                               │
│                      Contrôle d'amplitude globale                       │
└────────────────────────────────────┬────────────────────────────────────┘
                                     │
                                     ▼
                      ┌───────────────────────────────┐
                      │           LIMITER             │
                      │Threshold: -6 dB | Ratio: 20:1 │
                      └──────────────┬────────────────┘
                                     │
                                     ▼
                      ┌───────────────────────────────┐
                      │          FFT ANALYSER         │
                      │    Spectre visuel temps réel  │
                      └──────────────┬────────────────┘
                                     │
                                     ▼
                                AUDIO OUTPUT
```

---

_Ce logiciel est gratuit. N'oubliez pas de lui donner une ⭐ sur Github si vous avez aimé le projet._

---

<p align="center"><code>𝒦𝑜𝓊𝓈𝑒𝒾</code></p>
<p align="center"><code>2026</code></p>

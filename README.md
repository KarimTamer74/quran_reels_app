<div align="center">

<img src="docs/screenshots/app_icon.png" width="100" alt="QuranReels App Icon">

# 🎬 QuranReels

### Transform Quran recitations into cinematic vertical videos — ready to share.

<p>
  <a href="#-features">
    <img src="https://img.shields.io/badge/✨_Features-1D9E75?style=for-the-badge&labelColor=111111" alt="Features">
  </a>
  <a href="#-screenshots">
    <img src="https://img.shields.io/badge/📸_Screenshots-1D9E75?style=for-the-badge&labelColor=111111" alt="Screenshots">
  </a>
  <a href="#-architecture">
    <img src="https://img.shields.io/badge/🏗️_Architecture-1D9E75?style=for-the-badge&labelColor=111111" alt="Architecture">
  </a>
  <a href="#-tech-stack">
    <img src="https://img.shields.io/badge/🛠️_Tech_Stack-1D9E75?style=for-the-badge&labelColor=111111" alt="Tech Stack">
  </a>
  <a href="#-contact">
    <img src="https://img.shields.io/badge/👨‍💻_Contact-1D9E75?style=for-the-badge&labelColor=111111" alt="Contact">
  </a>
</p>

<br>

<p>
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter">
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart">
  <img src="https://img.shields.io/badge/Cubit%20%2F%20BLoC-6C63FF?style=flat-square" alt="Cubit BLoC">
  <img src="https://img.shields.io/badge/FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white" alt="FFmpeg">
  <img src="https://img.shields.io/badge/Active%20Development-1D9E75?style=flat-square" alt="Status">
</p>

<br>

<p>
  <strong>📖 Quran Selection</strong>
  &nbsp;•&nbsp;
  <strong>🎙️ Reciter Selection</strong>
  &nbsp;•&nbsp;
  <strong>🎨 Custom Templates</strong>
  &nbsp;•&nbsp;
  <strong>🎥 FFmpeg Video Generation</strong>
</p>

</div>

---

## What is QuranReels?

QuranReels is a Flutter application that lets users pick any Surah and Ayah range, choose from world-renowned reciters, select a visual template, and export a professional 9:16 vertical video — fully on-device, no backend required.

Built to solve a real problem: creating Quran recitation videos for social media is technically complex. QuranReels handles audio synchronization, Arabic text rendering, gradient backgrounds, and FFmpeg composition in a clean, guided flow.

## 📱 User Flow
```
Surah  →  Ayah Range  →  Reciter  →  Template  →  Preview  →  Generate  →  Share
```

---
## ✨ Features

| | Feature | Details |
|---|---|---|
| 📖 | **Surah & Ayah Selection** | Search all 114 Surahs, select any Ayah range with live text preview |
| 🎙️ | **12 World Reciters** | Abdul Basit, Al-Afasy, As-Sudais, Al-Minshawi & more |
| 🔊 | **Audio Preview** | Preview recitation before generating |
| 🎨 | **8 Built-in Templates** | Gradient backgrounds (Emerald, Ocean, Sunset, Minimal...) |
| 🖼️ | **Custom Templates** | Upload your own background image |
| 🎬 | **On-Device Video Generation** | FFmpeg-powered, no internet needed after audio download |
| 📝 | **Synchronized Subtitles** | Each Ayah appears exactly when the reciter reads it |
| 💾 | **Save & Share** | Export to gallery or share directly to Instagram, WhatsApp, TikTok |
| 🌍 | **Arabic + English** | Full RTL support with localized UI |
| 🌓 | **Dark / Light Theme** | Persistent theme preference |

---

## 📸 Screenshots

### 🚀 Splash

<div align="center">
  <img src="docs/screenshots/splash.png" width="220">
</div>

### 🏠 Home

<div align="center">
  <img src="docs/screenshots/home_light.png" width="220" alt="Home Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/home_dark.png" width="220" alt="Home Dark">
</div>

### 📖 Surah Selection

<div align="center">
  <img src="docs/screenshots/surah_light.png" width="220" alt="Surah Selection Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/surah_dark.png" width="220" alt="Surah Selection Dark">
</div>

### 🔢 Ayah Range

<div align="center">
  <img src="docs/screenshots/ayah_light.png" width="220" alt="Ayah Range Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/ayah_dark.png" width="220" alt="Ayah Range Dark">
</div>

### 🎙️ Reciter Selection

<div align="center">
  <img src="docs/screenshots/reciter_light.png" width="220" alt="Reciter Selection Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/reciter_dark.png" width="220" alt="Reciter Selection Dark">
</div>

### 🎨 Templates

<div align="center">
  <img src="docs/screenshots/template-light.png" width="220" alt="Template Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/template1_dark.png" width="220" alt="Template Dark">
  &nbsp;&nbsp;
  <img src="docs/screenshots/template2_dark.png" width="220" alt="My Templates">
</div>

### 👁️ Preview

<div align="center">
  <img src="docs/screenshots/preview_light.png" width="220" alt="Preview Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/preview_dark.png" width="220" alt="Preview Dark">
</div>

### ⚙️ Video Generation

<div align="center">
  <img src="docs/screenshots/generation1_light.png" width="220" alt="Generation Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/generation_dark.png" width="220" alt="Generation Dark">
</div>

### 🎬 Reel Done

<div align="center">
  <img src="docs/screenshots/done_light.png" width="220" alt="Reel Done Light">
  &nbsp;&nbsp;
  <img src="docs/screenshots/done_dark.png" width="220" alt="Reel Done Dark">
</div>

---


## 🏗 Architecture

Feature-based folder structure with MVVM-oriented separation and Cubit/BLoC state management.

```
lib/
├── core/                    # Shared infrastructure
│   ├── services/            # VideoGeneratorService, QuranAudioService
│   ├── routing/             # Named routes
│   ├── theme/               # AppColors, AppTheme, AppTextStyles
│   └── shared_widgets/      # CustomAppBar, CustomButton, CustomCard...
│
└── features/
    ├── home/
    ├── quran_generator/
    │   ├── data/            # Models, repositories
    │   └── presentation/
    │       ├── cubits/      # VideoGenerationCubit, PreviewCubit, AudioCubit
    │       ├── controllers/ # VideoResultController
    │       ├── screens/     
    │       └── widgets/     # Extracted, reusable widgets
    ├── onboarding/
    └── settings/
```

**Patterns:** Repository, Cubit/BLoC, Service Layer, Dependency Injection (GetIt)

---

## 🎬 Video Generation Pipeline

QuranReels uses **FFmpeg** to process the selected recitations, Quran text, and visual template into a vertical MP4 video.

```text
Selected Ayahs
      ↓
Download Recitation Audio
      ↓
Process & Combine Audio
      ↓
Prepare Quran Text & Metadata
      ↓
Compose Background + Text + Audio
      ↓
FFmpeg
      ↓
Final 9:16 MP4 Video
```
---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| **Framework** | <img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter"> <img src="https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart"> |
| **Architecture** | <img src="https://img.shields.io/badge/MVVM-1D9E75?style=flat-square" alt="MVVM"> <img src="https://img.shields.io/badge/Feature--Based-1D9E75?style=flat-square" alt="Feature Based Architecture"> |
| **State Management** | <img src="https://img.shields.io/badge/BLoC-6C63FF?style=flat-square" alt="BLoC"> <img src="https://img.shields.io/badge/Cubit-6C63FF?style=flat-square" alt="Cubit"> |
| **Dependency Injection** | <img src="https://img.shields.io/badge/GetIt-1D9E75?style=flat-square" alt="GetIt"> |
| **Video Processing** | <img src="https://img.shields.io/badge/FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white" alt="FFmpeg"> |
| **Audio Playback** | <img src="https://img.shields.io/badge/just__audio-0175C2?style=flat-square&logo=dart&logoColor=white" alt="just_audio"> |
| **Video Playback** | <img src="https://img.shields.io/badge/Video_Player-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Video Player"> |
| **Quran Data** | <img src="https://img.shields.io/badge/AlQuran_Cloud-1D9E75?style=flat-square" alt="AlQuran Cloud"> <img src="https://img.shields.io/badge/Hive-FFC107?style=flat-square&logo=hive&logoColor=black" alt="Hive"> |
| **Quran Audio** | <img src="https://img.shields.io/badge/EveryAyah-1D9E75?style=flat-square" alt="EveryAyah"> |
| **Networking** | <img src="https://img.shields.io/badge/Dio-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dio"> <img src="https://img.shields.io/badge/HTTP-0175C2?style=flat-square&logo=dart&logoColor=white" alt="HTTP"> |
| **Localization** | <img src="https://img.shields.io/badge/Easy_Localization-1D9E75?style=flat-square" alt="Easy Localization"> |
| **Responsive UI** | <img src="https://img.shields.io/badge/ScreenUtil-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter ScreenUtil"> |
| **Local Storage** | <img src="https://img.shields.io/badge/Hive-FFC107?style=flat-square&logo=hive&logoColor=black" alt="Hive"> <img src="https://img.shields.io/badge/Shared_Preferences-4285F4?style=flat-square&logo=android&logoColor=white" alt="Shared Preferences"> |
| **Gallery & Sharing** | <img src="https://img.shields.io/badge/Gal-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Gal"> <img src="https://img.shields.io/badge/Share_Plus-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Share Plus"> |
---

## ⚙️ Engineering Highlights

### 🏗 Architecture & State Management

- **Feature-based architecture** with clear separation between features and shared application infrastructure
- **MVVM-oriented separation** between UI, state management, and application logic
- **Cubit / BLoC** for predictable and reactive state management
- Reusable and modular **custom widgets**
- Centralized **theme and color system**
- Centralized **typography and text styles**
- Separation of media processing logic into dedicated services

### 🎥 Media Processing

- Dynamic **Quran Ayah audio URL generation** using EveryAyah
- On-demand **Ayah audio downloading** instead of bundling complete recitations
- **Audio concatenation** for combining selected Ayahs into a continuous track
- **FFmpeg-based video composition**
- Arabic **Quran text rendering**
- Dynamic Surah and reciter information rendering
- **9:16 vertical video generation** for social media content
- Temporary file management for generated audio and video
- Video progress tracking during generation

### 🎨 UI & User Experience

- Responsive layouts using **Flutter ScreenUtil**
- Light / Dark theme support
- Arabic / English localization with **RTL support**
- Guided multi-step Quran Reel creation flow
- Reusable custom UI components
- Audio preview before video generation
- Suggested and personal template management
- Template rename and delete functionality
- Clear loading, success, and failure states
- Video preview with playback controls
- Save generated videos to the device gallery
- Share generated videos directly from the application
## 🗺️ Roadmap

### ✅ Implemented

<table>
<tr>
<td width="33%">

- [x] Surah selection
- [x] Ayah range selection
- [x] Reciter selection
- [x] Reciter audio preview
- [x] Suggested templates
- [x] My Templates

</td>
<td width="33%">

- [x] Template selection
- [x] Template rename / delete
- [x] Preview screen
- [x] Video generation screen
- [x] Video result screen
- [x] Video playback
- [x] Save to gallery

</td>
<td width="33%">


- [x] Share generated video
- [x] Arabic / English localization
- [x] Light / Dark theme
- [x] Responsive UI
- [x] FFmpeg generation foundation

</td>
</tr>
</table>

### 🚧 In Progress

<table>
<tr>
<td width="33%">

- [ ] Finalize FFmpeg generation pipeline
- [ ] Accurate Ayah / audio synchronization
- [ ] Improve Arabic text wrapping

</td>
<td width="33%">

- [ ] Optimize generation speed & memory usage
- [ ] Improve generated video quality


</td>
<td width="33%">

- [ ] Finalize custom template persistence
- [ ] Production testing across Android devices

</td>
</tr>
</table>

### 🔮 Planned

<table>
<tr>
<td width="33%">

- [ ] More Quran templates
- [ ] More reciters
- [ ] Custom backgrounds

</td>
<td width="33%">

- [ ] Text animation styles
- [ ] Multiple video resolutions


</td>
<td width="33%">

- [ ] Generation history
- [ ] Favorites / saved projects
- [ ] Google Play release

</td>
</tr>
</table>

---

## 👨‍💻 Contact

**Karim Tamer** — Flutter Developer

[![GitHub](https://img.shields.io/badge/GitHub-KarimTamer74-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KarimTamer74)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Karim_Tamer-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karim-tamer74)

---

## 📄 License

Portfolio and demonstration purposes.
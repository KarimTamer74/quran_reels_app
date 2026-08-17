<div align="center">

🎬 QuranReels

Create beautiful, shareable Quran Reels — directly from your selected Ayahs.

<p>
  <img src="docs/screenshots/app_icon.png" width="110" alt="QuranReels App Icon">
</p>

<p>
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?style=for-the-badge&logo=flutter&logoColor=white">
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart&logoColor=white">
  <img src="https://img.shields.io/badge/State-Cubit%20%2F%20BLoC-6C63FF?style=for-the-badge">
  <img src="https://img.shields.io/badge/Architecture-MVVM-1DB954?style=for-the-badge">
  <img src="https://img.shields.io/badge/Video-FFmpeg-000000?style=for-the-badge&logo=ffmpeg&logoColor=white">
</p>

<p>
  <img src="https://img.shields.io/badge/Localization-AR%20%2B%20EN-1DB954?style=flat-square">
  <img src="https://img.shields.io/badge/Theme-Light%20%2B%20Dark-1DB954?style=flat-square">
  <img src="https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square">
</p>

<p>
  <a href="#-overview">Overview</a> •
  <a href="#-features">Features</a> •
  <a href="#-how-it-works">How It Works</a> •
  <a href="#-video-generation">Video Generation</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-screenshots">Screenshots</a>
</p>

</div>

🌙 Overview

QuranReels is a Flutter application built to turn selected Quran verses into beautiful 9:16 vertical videos ready to preview, save, and share.

Instead of manually editing a Quran video, the user simply chooses:

Surah → Ayah Range → Reciter → Template → Preview → Generate → Share

The project combines Quran data, online recitations, customizable visual templates, and local FFmpeg processing into one creation flow.

🚧 Project Status: In Development / Portfolio ProjectThe main application flow and UI are implemented. The FFmpeg generation pipeline is still being refined for synchronization, performance, and production reliability.
## ✨ Features

<table>
<tr>
<td width="50%">

### 📖 Quran Selection

- Browse all Quran Surahs
- Arabic & English names
- Select an Ayah range
- Quran text integration

</td>
<td width="50%">

### 🎙️ Reciters

- Curated reciter collection
- Reciter images
- EveryAyah audio integration
- Audio preview
- Dynamic Ayah audio URLs

</td>
</tr>

<tr>
<td>

### 🎨 Templates

- Suggested templates
- My Templates
- Custom templates
- Rename & delete templates

</td>
<td>

### 👁️ Preview & Generation

- Review selected Quran content
- Preview reciter & template
- Generate vertical Quran Reels
- Track generation progress

</td>
</tr>

<tr>
<td>

### 🎥 Video Result

- Video playback
- Progress & scrubbing
- Save to gallery
- Share generated video

</td>
<td>

### 🌍 Experience

- Arabic & English
- RTL support
- Light & Dark mode
- Responsive UI

</td>
</tr>
</table>

---

## 🧭 How It Works

```text
Select Surah
      ↓
Select Ayah Range
      ↓
Select Reciter
      ↓
Choose Template
      ↓
Preview
      ↓
Generate Video
      ↓
Play • Save • Share
```
🖼️ Screenshots

📖 Quran Selection

<div align="center">
  <img src="docs/screenshots/surah_selection.png" width="250">
  &nbsp;&nbsp;&nbsp;
  <img src="docs/screenshots/ayah_range.png" width="250">
</div>

<p align="center">
  <b>Surah Selection</b>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <b>Ayah Range</b>
</p>

🎙 Reciter Selection

<div align="center">
  <img src="docs/screenshots/reciter_selection.png" width="250">
  &nbsp;&nbsp;&nbsp;
  <img src="docs/screenshots/reciter_audio_preview.png" width="250">
</div>

<p align="center">
  Choose a reciter and preview the recitation before continuing.
</p>

🎨 Templates

<div align="center">
  <img src="docs/screenshots/suggested_templates.png" width="250">
  &nbsp;&nbsp;&nbsp;
  <img src="docs/screenshots/my_templates.png" width="250">
</div>

<p align="center">
  <b>Suggested Templates</b>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <b>My Templates</b>
</p>

👁 Preview

<div align="center">
  <img src="docs/screenshots/preview.png" width="280">
</div>

<p align="center">
  Review the selected Surah, Ayah range, Reciter and Template before generation.
</p>

⚙️ Generation

<div align="center">
  <img src="docs/screenshots/video_generation.png" width="280">
</div>

<p align="center">
  Progress feedback while the video is being generated.
</p>

📱 Final Result

<div align="center">
  <img src="docs/screenshots/video_result.png" width="280">
</div>

<p align="center">
  Preview, save, and share the generated Quran Reel.
</p>

🏗 Architecture

QuranReels follows a feature-based architecture with an MVVM-oriented structure and Cubit/BLoC state management.

The goal is to keep UI, state, business logic, services, and data models separated and maintainable.

                    ┌──────────────────────┐
                    │     Presentation     │
                    │ Screens • Widgets    │
                    │       • Cubits       │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       ViewModel      │
                    │   Cubit / States     │
                    │ UI Flow Orchestration│
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       Services       │
                    │ Audio • Video •      │
                    │ Local Storage        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │         Data         │
                    │ Models • APIs •      │
                    │ External Sources     │
                    └──────────────────────┘

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| **Framework** | Flutter |
| **Language** | Dart |
| **Architecture** | MVVM-oriented / Feature-based |
| **State Management** | Cubit / BLoC |
| **Video Processing** | FFmpeg |
| **Audio Playback** | just_audio |
| **Networking** | Dio / HTTP |
| **Quran Data** | AlQuran Cloud API |
| **Quran Audio** | EveryAyah |
| **Localization** | Easy Localization |
| **Responsive UI** | Flutter ScreenUtil |
| **Local Storage** | Hive / Shared Preferences |
| **Video Playback** | video_player |
| **Gallery** | Gal |
| **Sharing** | share_plus |
| **Dependency Injection** | GetIt |

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

- [x] Surah selection
- [x] Ayah range selection
- [x] Reciter selection
- [x] Reciter audio preview
- [x] Suggested templates
- [x] My Templates
- [x] Template selection
- [x] Template rename / delete
- [x] Preview screen
- [x] Video generation screen
- [x] Video result screen
- [x] Video playback
- [x] Save to gallery
- [x] Share generated video
- [x] Arabic / English localization
- [x] Light / Dark theme
- [x] Responsive UI
- [x] FFmpeg generation foundation

### 🚧 In Progress

- [ ] Finalize FFmpeg generation pipeline
- [ ] Accurate Ayah / audio synchronization
- [ ] Improve Arabic text wrapping
- [ ] Optimize generation speed & memory usage
- [ ] Improve generated video quality
- [ ] Finalize custom template persistence
- [ ] Production testing across Android devices

### 🔮 Planned

- [ ] More Quran templates
- [ ] More reciters
- [ ] Custom backgrounds
- [ ] Text animation styles
- [ ] Multiple video resolutions
- [ ] Generation history
- [ ] Favorites / saved projects
- [ ] Google Play release

---

## 📌 Project Status

QuranReels is an active portfolio project under development.

The main creation flow and UI are implemented. Current development is focused on making the video generation pipeline reliable, accurately synchronized, memory-efficient, and ready for production use.

The project is being developed with production-oriented architecture and reusable components rather than as a simple UI prototype.

## 👨‍💻 Author

**Karim Tamer**

Flutter Developer

<p align="left">
  <a href="https://github.com/KarimTamer74">
    <img src="https://img.shields.io/badge/GitHub-KarimTamer74-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
  <a href="https://www.linkedin.com/in/karim-tamer74">
    <img src="https://img.shields.io/badge/LinkedIn-Karim%20Tamer-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
</p>

## 📄 License

This project is currently intended for portfolio and demonstration purposes.
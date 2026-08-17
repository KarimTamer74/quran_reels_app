<div align="center">

<img src="docs/screenshots/app_icon.png" width="100" alt="QuranReels"/>

# QuranReels

**Transform Quran recitations into cinematic vertical videos — ready to share on Reels & TikTok.**

[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?style=flat-square&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=flat-square&logo=dart&logoColor=white)](https://dart.dev)
[![Cubit/BLoC](https://img.shields.io/badge/State-Cubit%20%2F%20BLoC-6C63FF?style=flat-square)](https://bloclibrary.dev)
[![FFmpeg](https://img.shields.io/badge/Video-FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)](https://ffmpeg.org)
[![Status](https://img.shields.io/badge/Status-Active_Development-1D9E75?style=flat-square)]()

[Features](#-features) · [Screenshots](#-screenshots) · [Architecture](#-architecture) · [Tech Stack](#-tech-stack) · [Contact](#-contact)

</div>

---

## What is QuranReels?

QuranReels is a Flutter application that lets users pick any Surah and Ayah range, choose from world-renowned reciters, select a visual template, and export a professional 9:16 vertical video — fully on-device, no backend required.

Built to solve a real problem: creating Quran recitation videos for social media is technically complex. QuranReels handles audio synchronization, Arabic text rendering, gradient backgrounds, and FFmpeg composition in a clean, guided flow.

```
Surah  →  Ayah Range  →  Reciter  →  Template  →  Preview  →  Generate  →  Share
```

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 📖 Quran Selection
- Browse & search all 114 Surahs
- Arabic & English names
- Ayah range picker with live text preview

</td>
<td width="50%">

### 🎙️ Reciters
- 12 world-renowned reciters
- Audio preview before generation
- Powered by EveryAyah.com

</td>
</tr>
<tr>
<td>

### 🎨 Templates
- 8 built-in gradient templates
- Custom image upload
- Rename & delete personal templates

</td>
<td>

### 🎬 Video Generation
- On-device FFmpeg processing
- Synchronized Arabic subtitles
- Real-time progress tracking

</td>
</tr>
<tr>
<td>

### 📱 Video Result
- In-app playback with scrubbing
- Save to gallery
- Share to Instagram, WhatsApp, TikTok

</td>
<td>

### 🌍 Experience
- Arabic + English (RTL support)
- Light & Dark theme
- Responsive for phones & tablets

</td>
</tr>
</table>

---

## 📸 Screenshots

### Surah & Ayah Selection
<div align="center">
  <img src="docs/screenshots/surah_selection.png" width="220">
  &nbsp;&nbsp;
  <img src="docs/screenshots/ayah_range.png" width="220">
</div>

### Reciter & Template
<div align="center">
  <img src="docs/screenshots/reciter_selection.png" width="220">
  &nbsp;&nbsp;
  <img src="docs/screenshots/suggested_templates.png" width="220">
</div>

### Preview & Result
<div align="center">
  <img src="docs/screenshots/preview.png" width="220">
  &nbsp;&nbsp;
  <img src="docs/screenshots/video_result.png" width="220">
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
    │       ├── screens/     # 7 screens
    │       └── widgets/     # Extracted, reusable widgets
    ├── onboarding/
    └── settings/
```

**Patterns:** Repository, Cubit/BLoC, Service Layer, Dependency Injection (GetIt)

---

## 🎬 Video Generation Pipeline

All processing happens on-device using `ffmpeg_kit_flutter`.

```
Download Ayah audio files  →  Extract per-file duration (ffprobe)
         ↓
Merge audio (concat)  →  Dart-side Arabic word wrap
         ↓
Compose: gradient background + timed subtitle filters + metadata overlay
         ↓
Export MP4  (720×1280 · H.264 · AAC · faststart)
```

**Key engineering decisions:**
- **720p output** — 2× faster than 1080p with no visible quality loss on mobile
- **Dart-side word wrap** — avoids FFmpeg multiline limitations for Arabic text
- **`enable='between(t,start,end)'`** — each Ayah subtitle synced to exact audio duration
- **Shadow rendering** — cleaner text on any background, no border artifacts
- **`superfast` preset + CRF 28** — optimal speed/quality balance on mobile hardware

---

## 🛠 Tech Stack

| Category | Package |
|---|---|
| Framework | Flutter 3.x, Dart 3.x |
| State Management | `flutter_bloc` (Cubit) |
| Dependency Injection | `get_it` |
| Video Processing | `ffmpeg_kit_flutter_new` |
| Audio Playback | `just_audio` |
| Video Playback | `video_player` |
| Quran Data | AlQuran Cloud API + Hive cache |
| Quran Audio | EveryAyah.com |
| Localization | `easy_localization` |
| Responsive UI | `flutter_screenutil` |
| Gallery / Share | `gal`, `share_plus` |
| Networking | `http`, `dio` |
| Local Storage | `hive`, `shared_preferences` |

---

## ⚙️ Engineering Highlights

**Architecture**
- Feature-based structure with clear separation of UI, state, and services
- Cubit for predictable, testable state transitions
- Centralized design system (colors, typography, spacing)

**Media Processing**
- Dynamic audio URL generation per Ayah and reciter — no bundled audio
- FFmpeg filter_complex pipeline: gradient → text overlays → mux
- Temporary job directories cleaned after generation

**UI/UX**
- Multi-step guided creation flow with shared state via `PreviewCubit`
- `VideoResultController extends ChangeNotifier` separates playback logic from UI
- Animated generation progress with simulated + real progress blending

---

## 🗺 Roadmap

**✅ Done**
- Full creation flow (Surah → Ayah → Reciter → Template → Preview → Generate → Share)
- FFmpeg on-device video generation with synchronized subtitles
- Custom template upload, rename & delete
- Arabic/English localization + RTL
- Light/Dark theme with persistence

**🚧 In Progress**
- Generation speed & memory optimization
- Production testing across Android devices

**🔮 Planned**
- Generation history & saved projects
- More templates and reciters
- Text animation styles
- Google Play release

---

## 🚀 Getting Started

```bash
git clone https://github.com/KarimTamer74/quran_reels.git
cd quran_reels
flutter pub get
flutter run
```

> Requires Android SDK 21+ · FFmpeg Kit is bundled — no additional setup needed.

---

## 👨‍💻 Contact

**Karim Tamer** — Flutter Developer

[![GitHub](https://img.shields.io/badge/GitHub-KarimTamer74-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KarimTamer74)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Karim_Tamer-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karim-tamer74)

---

## 📄 License

Portfolio and demonstration purposes.
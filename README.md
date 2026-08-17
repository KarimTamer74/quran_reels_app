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

✨ Features

<table>
<tr>
<td width="50%">

📖 Quran Selection

Browse Quran Surahs

Arabic & English names

Surah number

Responsive selection UI

Quran text integration

</td>
<td width="50%">

🔢 Ayah Range

Select starting Ayah

Select ending Ayah

Preview the selected range

Carry the selection through the creation flow

</td>
</tr>

<tr>
<td>

🎙 Reciters

Curated reciter list

Reciter images

EveryAyah audio integration

Play Basmala / Ayah previews

Dynamic audio URLs

</td>
<td>

🎨 Templates

Suggested templates

Template categories / filters

My Templates

Custom template support

Rename templates

Delete templates

</td>
</tr>

<tr>
<td>

👁 Preview

Review the complete configuration before generation:

Surah

Ayah range

Reciter

Template

Background

Reciter information

</td>
<td>

🎥 Video Result

After generation:

Play / pause

Scrub through the video

Save to gallery

Share the generated MP4

View duration & file size

</td>
</tr>
</table>

🧭 How It Works

┌──────────────────┐
│   1. Select      │
│      Surah       │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   2. Select      │
│    Ayah Range    │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   3. Select      │
│     Reciter      │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   4. Select      │
│     Template     │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   5. Preview     │
│  Complete Setup  │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   6. Generate    │
│     Video        │
└────────┬─────────┘
         ↓
┌──────────────────┐
│   7. Video       │
│      Result      │
│ Play • Save •    │
│      Share       │
└──────────────────┘

🎥 Video Generation

Video generation is the core technical part of QuranReels.

The application uses FFmpeg to compose the final Reel locally.

Generation Pipeline

Selected Ayahs
      │
      ▼
EveryAyah Audio URLs
      │
      ▼
Download Required Audio
      │
      ▼
Merge Ayah Audio
      │
      ├───────────────┐
      ▼               ▼
Template /        Quran Text
Background        + Metadata
      │               │
      └───────┬───────┘
              ▼
           FFmpeg
              │
              ▼
       Vertical MP4
        1080 × 1920
           9:16

🔊 Audio

Only the required recitation files are requested instead of bundling the entire Quran audio library inside the application.

EveryAyah URLs follow the project structure:

https://everyayah.com/data/{reciter_folder}/{surah}{ayah}.mp3

The selected Ayah recordings are downloaded and combined into the video's audio track.

🎞 FFmpeg

FFmpeg handles:

Background / template processing

Audio input

Quran text rendering

Surah information

Reciter information

Video composition

MP4 encoding

9:16 vertical output

Output

Format      MP4
Resolution  1080 × 1920
Aspect      9:16
Use Case    Social / Short-form Video

⚠️ Current focus: accurate Ayah/audio synchronization, Arabic text rendering, generation performance, and production stability.

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

📂 Project Structure

lib/
│
├── core/
│   ├── constants/
│   ├── extensions/
│   ├── localization/
│   ├── routing/
│   ├── services/
│   │   ├── quran_audio_service.dart
│   │   └── video_generator_service.dart
│   ├── shared_widgets/
│   ├── theme/
│   └── utils/
│
├── features/
│   ├── onboarding/
│   │
│   └── quran_generator/
│       ├── data/
│       │   └── models/
│       │
│       └── presentation/
│           ├── cubits/
│           ├── screens/
│           └── widgets/
│
└── main.dart

Why this structure?

Core → reusable application infrastructure

Features → isolated business features

Screens → page-level UI

Widgets → reusable UI components

Cubits → state & flow management

Models → structured application data

Services → external / media operations

🧠 State Management

The project uses flutter_bloc / Cubit for predictable and reactive state management.

Key Cubits include:

TemplateCubit
PreviewCubit
VideoGenerationCubit

The generation flow is represented through explicit states:

Initial
   │
   ▼
Loading
   │
   ▼
Generating
   │
   ├──────────────► Failure
   │
   ▼
Ready
   │
   ▼
Done

This keeps business logic out of UI widgets and allows the UI to react to state changes.

⚡ Performance

Media generation can be expensive, so the project is built with performance in mind.

Current techniques

⚙️ FFmpeg-based media processing

🧩 Reusable widgets

🧱 const widgets where applicable

🎨 RepaintBoundary around expensive template cards

🔊 Load only required audio

💾 Temporary file storage for generated media

📊 Generation progress feedback

🧠 Separation of video processing from UI rendering

🌍 Localization

QuranReels supports:

Language

Direction

🇬🇧 English

LTR

🇪🇬 Arabic

RTL

Localization is implemented using Easy Localization, with the UI designed to support Arabic RTL layouts.

User-facing strings are kept localization-ready rather than being tightly coupled to individual widgets.

🎨 Design System

QuranReels supports both:

☀️ Light Mode

Clean surfaces, readable typography, and the brand green accent.

🌙 Dark Mode

Dark cinematic surfaces designed to complement Quran video content.

Brand Accent

Color(0xFF1DB954)

The design combines the green brand accent with dark visual surfaces to create a modern Quran-focused identity.

🛠 Tech Stack

Layer

Technology

Framework

Flutter

Language

Dart

Architecture

MVVM-oriented / Feature-based

State Management

BLoC / Cubit

Video Processing

FFmpeg

Audio Playback

just_audio

Networking

Dio / HTTP

Quran Text

AlQuran Cloud API

Quran Audio

EveryAyah

Localization

Easy Localization

Responsive UI

Flutter ScreenUtil

Local Storage

Hive / Shared Preferences

Video Playback

video_player

Gallery

Gal

Sharing

share_plus

Dependency Injection

GetIt

UI

Material + Custom Widgets

🔌 External Sources

📖 Quran Text

The project uses the AlQuran Cloud API for Quran data.

https://api.alquran.cloud/v1/quran/quran-uthmani

🎙 Quran Recitations

Recitations are retrieved from EveryAyah.

This approach allows the application to request only the selected Ayahs instead of shipping the complete audio library with the APK.

💡 Engineering Highlights

Flutter

Feature-based architecture

MVVM-oriented separation

Cubit/BLoC state management

Reusable custom widgets

Centralized theme system

Centralized typography

Responsive UI

Arabic RTL support

Media Processing

Dynamic Ayah audio URL generation

Individual audio downloads

Audio concatenation

FFmpeg video composition

Arabic text rendering

9:16 vertical video generation

Temporary media file handling

User Experience

Guided creation flow

Audio preview

Template browsing

Custom template management

Generation progress

Video preview

Save to gallery

Share generated video

Light / Dark mode

Arabic / English localization

🗺️ Roadmap

✅ Implemented

Surah selection

Ayah range selection

Reciter selection

Reciter audio preview

Suggested templates

My Templates

Template selection

Template rename / delete

Preview screen

Video generation screen

Video result screen

Video playback

Save to gallery

Share generated video

Arabic / English localization

Light / Dark theme

Responsive UI

FFmpeg generation foundation

🚧 In Progress

Finalize FFmpeg generation pipeline

Accurate Ayah / audio synchronization

Improve Arabic text wrapping

Optimize generation speed & memory usage

Improve generated video quality

Finalize custom template persistence

Production testing across Android devices

🔮 Planned

More Quran templates

More reciters

Custom backgrounds

Text animation styles

Multiple video resolutions

Generation history

Favorites / saved projects

Google Play release

📌 Project Status

QuranReels is an active portfolio project under development.

The main creation flow and UI are implemented. Current development is focused on making the video generation pipeline reliable, accurately synchronized, memory-efficient, and ready for production use.

The project is being developed with production-oriented architecture and reusable components rather than as a simple UI prototype.

👨‍💻 Author

<div align="center">

Karim Tamer

Flutter Developer

<a href="https://github.com/KarimTamer74">
  <img src="https://img.shields.io/badge/GitHub-KarimTamer74-181717?style=for-the-badge&logo=github&logoColor=white">
</a>

</div>

<div align="center">

🌙 Built with Flutter & ❤️ for Quran content creators

</div>

📄 License

This project is currently intended for portfolio, learning, and demonstration purposes.
🎬 AyahFlow

<p align="center">
  <img src="docs/screenshots/ayahflow_app_icon.png" width="120" alt="AyahFlow App Icon">
</p>

<h3 align="center">
  A modern Flutter application for creating cinematic Quran Reels from selected verses.
</h3>

<p align="center">
  Flutter • Dart • BLoC/Cubit • MVVM • FFmpeg • REST APIs • Easy Localization
</p>

<p align="center">
  <a href="#-screenshots">📸 Screenshots</a>
  &nbsp; • &nbsp;
  <a href="#-features">✨ Features</a>
  &nbsp; • &nbsp;
  <a href="#-video-generation-pipeline">🎥 Video Generation</a>
  &nbsp; • &nbsp;
  <a href="#-architecture">🏗 Architecture</a>
</p>

📱 About

AyahFlow is a Flutter-based Quran Reel generator designed to turn selected Quran verses into short, vertical videos suitable for sharing on social media.

The user can select a Surah, choose an ayah range, select a reciter, choose a visual template/background, preview the configuration, and generate a final video containing the Quran text, reciter information, visual background, and recitation audio.

The project focuses on:

Clean and maintainable Flutter architecture

Reusable UI components

Reactive state management with Cubit

MVVM-oriented feature organization

Arabic-first Quran presentation

Light / Dark themes

Arabic / English localization

Responsive UI

Local video generation with FFmpeg

Performance-conscious video processing

🚧 Status: In Development / Portfolio Project

The application is not currently presented as a production-ready Google Play release.

✨ Features

📖 Surah Selection

Users can browse the Quran and select the Surah they want to use in their Reel.

Quran data integration

Surah name in Arabic and English

Surah number

Search/filter-friendly selection UI

Responsive Surah cards

🔢 Ayah Range Selection

After selecting a Surah, users can select the exact range of verses they want to include.

Example:

Al-Baqarah
Ayahs 1 → 5

The selected range is carried through the creation flow until the final generation stage.

🎙 Reciter Selection

Users can choose from a curated list of Quran reciters.

Each reciter contains information such as:

Reciter name

EveryAyah audio folder

Reciter image

Audio preview support

Audio is retrieved dynamically rather than bundling every Quran recording inside the application.

The project uses EveryAyah audio URLs for individual ayahs.

🎨 Template System

AyahFlow provides visual templates/backgrounds for Quran Reels.

Users can:

Browse suggested templates

Filter templates

Select a template

Browse personal templates

Add custom templates

Rename personal templates

Delete personal templates

The template system is designed to be reusable and extensible.

👤 My Templates

Users can manage their own visual templates separately from the built-in suggested templates.

The UI separates:

Suggested Templates
        ↓
My Templates

This keeps the template browsing experience clean and scalable.

👁 Preview

Before generating the final video, the application presents a preview configuration containing:

Surah

Selected ayah range

Reciter

Template/background

Reciter information

The selected data is passed through the creation flow using a dedicated preview arguments model rather than relying on unrelated UI state.

🎥 Video Generation Pipeline

The main technical feature of AyahFlow is its Quran video generation pipeline.

The generation process is designed around FFmpeg.

Pipeline

Surah
   │
   ▼
Ayah Range
   │
   ▼
Reciter
   │
   ▼
EveryAyah Audio URLs
   │
   ▼
Download Ayah Audio
   │
   ▼
Merge Audio
   │
   ▼
Background / Template
   │
   ▼
Quran Text + Metadata
   │
   ▼
FFmpeg
   │
   ▼
MP4 Video

Audio

Individual ayah audio files are generated from EveryAyah URLs:

https://everyayah.com/data/{reciter_folder}/{surah}{ayah}.mp3

The application downloads the required ayah recordings and combines them into a single audio track.

Video

FFmpeg is responsible for:

Loading the background

Loading the merged audio

Rendering Quran text

Rendering Surah information

Rendering reciter information

Creating the final vertical video

Encoding the result as MP4

The intended output format is optimized for social-media-style vertical video:

1080 × 1920
9:16
MP4

⚠️ The video generation pipeline is currently under active development and optimization.

🧭 User Flow

┌─────────────────────┐
│   Select Surah      │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Select Ayah Range   │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Select Reciter      │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Select Template     │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│       Preview       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Generate Video      │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│  Video Result       │
│                     │
│ Play • Save • Share │
└─────────────────────┘

📸 Screenshots

Add screenshots to docs/screenshots/ and update the filenames below.

📖 Quran Selection

Surah Selection

Ayah Range

<img src="docs/screenshots/surah_selection.png" width="250">

<img src="docs/screenshots/ayah_range.png" width="250">

🎙 Reciter Selection

<p align="center">
  <img src="docs/screenshots/reciter_selection.png" width="250">
  <img src="docs/screenshots/reciter_audio_preview.png" width="250">
</p>

🎨 Templates

Suggested Templates

My Templates

<img src="docs/screenshots/suggested_templates.png" width="250">

<img src="docs/screenshots/my_templates.png" width="250">

👁 Preview

<p align="center">
  <img src="docs/screenshots/preview.png" width="250">
</p>

🎥 Video Generation

<p align="center">
  <img src="docs/screenshots/video_generation.png" width="250">
</p>

📱 Generated Video

<p align="center">
  <img src="docs/screenshots/video_result.png" width="250">
</p>

🏗 Architecture

AyahFlow follows a feature-based Flutter architecture with MVVM-oriented separation and Cubit/BLoC state management.

The main goal is to keep:

UI responsibilities

State management

Business logic

Services

Data models

separated from each other.

High-Level Architecture

┌────────────────────────────────────┐
│            Presentation            │
│                                    │
│ Screens • Widgets • Cubits • UI    │
└──────────────────┬─────────────────┘
                   │
                   ▼
┌────────────────────────────────────┐
│             ViewModel              │
│                                    │
│ Cubit / State + UI orchestration   │
└──────────────────┬─────────────────┘
                   │
                   ▼
┌────────────────────────────────────┐
│              Services              │
│                                    │
│ Audio • Video • Local Storage      │
└──────────────────┬─────────────────┘
                   │
                   ▼
┌────────────────────────────────────┐
│               Data                 │
│                                    │
│ Models • APIs • External Sources   │
└────────────────────────────────────┘

📂 Project Structure

The project is organized by feature and shared core infrastructure.

lib/
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
│   ├── quran_generator/
│   │   ├── data/
│   │   │   └── models/
│   │   └── presentation/
│   │       ├── cubits/
│   │       ├── screens/
│   │       └── widgets/
│   │
│   └── ...
│
└── main.dart

The core layer contains reusable application infrastructure, while feature-specific UI and state live under features.

🧠 State Management

The application uses flutter_bloc / Cubit for predictable state management.

Examples include:

TemplateCubit
PreviewCubit
VideoGenerationCubit

The video generation flow exposes states such as:

Initial
   ↓
Loading
   ↓
Generating
   ↓
Ready
   ↓
Done

or:

Initial
   ↓
Loading
   ↓
Failure

The UI reacts to state changes instead of directly controlling business logic.

⚡ Performance

Video generation can be computationally expensive, so the project is designed with performance in mind.

Implemented / considered optimizations include:

FFmpeg-based processing

Avoiding unnecessary widget rebuilds

const widgets where possible

RepaintBoundary around expensive template cards

Reusable widgets

Lazy loading of audio files

Temporary file storage for generated media

Progress feedback during generation

Separation of video generation from UI rendering

🌍 Localization

The application supports multiple languages using Easy Localization.

Current target languages:

🇬🇧 English

🇪🇬 Arabic

The UI is designed with RTL support in mind for Arabic.

All user-facing text is intended to be localization-ready instead of being hardcoded inside widgets.

🎨 Theming

AyahFlow supports:

🌙 Dark Mode

☀️ Light Mode

The design system uses a centralized color and typography system to maintain consistency across screens.

The primary brand color is based around:

Color(0xFF1DB954)

The UI uses the green accent together with dark cinematic surfaces to create a modern Quran-focused visual identity.

🛠 Tech Stack

Category

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

Quran Audio

EveryAyah

Quran Data

AlQuran Cloud API

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

Material + Custom Reusable Widgets

🔌 External Data Sources

Quran Text

Quran text is retrieved using:

AlQuran Cloud API

Example endpoint used by the project:

https://api.alquran.cloud/v1/quran/quran-uthmani

Quran Audio

Individual recitations are retrieved from:

EveryAyah

This allows the application to request only the selected ayahs instead of bundling the complete audio library into the APK.

🎯 Engineering Highlights

Flutter Architecture

Feature-based project organization

MVVM-oriented separation

Cubit/BLoC state management

Reusable custom widgets

Centralized theme system

Centralized typography

Localization-ready UI

Media Processing

Dynamic Quran audio URL generation

Individual ayah audio downloads

Audio concatenation

FFmpeg video composition

Arabic text rendering

Vertical 9:16 video generation

Temporary media file management

UX

Step-by-step Quran Reel creation flow

Loading and generation progress

Audio preview before generation

Template selection

Personal template management

Video preview

Save to gallery

Share generated video

🗺 Roadmap

Completed / Implemented

Surah selection

Ayah range selection

Reciter selection

Reciter audio preview

Suggested templates

My Templates

Template selection

Template rename/delete flow

Preview screen

Video result screen

Video playback

Save video to gallery

Share generated video

Arabic / English localization

Light / Dark theme

Responsive UI

FFmpeg-based generation pipeline

🚧 In Progress

Finalize FFmpeg generation pipeline

Accurate per-ayah audio/text synchronization

Improve Quran text rendering and wrapping

Optimize generation speed and memory usage

Improve generated video quality

Finalize custom template persistence

Production testing across Android devices

🔮 Planned

More Quran templates

More reciters

Custom background support

More text animation styles

Multiple video resolutions

Generation history

Favorites / saved projects

Google Play release

📌 Project Status

AyahFlow is currently an active portfolio project under development.

The main application flow and UI have been implemented, while the video generation pipeline is still being refined for reliability, synchronization, performance, and production release.

The project is intentionally being developed with production-oriented architecture and engineering practices rather than as a simple UI prototype.

👨‍💻 Author

Karim Tamer

Flutter Developer

<p align="left">
  <a href="https://github.com/KarimTamer74">
    <img src="https://img.shields.io/badge/GitHub-KarimTamer74-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
</p>

📄 License

This project is currently intended for portfolio, learning, and demonstration purposes.

# DLMS-4800 PRO LIVE (Android Native Kotlin)

Aplikasi **Digital Loudspeaker Management System (DLMS)** berbasis Android Native (Kotlin) yang mampu menangkap **Audio Perangkat secara Live (`AudioPlaybackCapture`)** dari YouTube, Spotify, TikTok, maupun pemutar musik lokal, memprosesnya secara *real-time* di latar belakang, dan mengeluarkan hasilnya ke **Bluetooth**, **Jack Headset 3.5mm**, maupun **USB DAC**.

## Fitur Utama
1. **Live System Audio Capture (`AudioPlaybackCapture` + `MediaProjection`)**:
   - Menangkap audio internal Android 10+ (API 29+) dan otomatis mengecualikan UID aplikasi sendiri (`excludeUid`) agar tidak terjadi *echo/feedback loop*.
2. **Real-Time 64-Bit Biquad DSP Engine (`48 kHz Stereo`)**:
   - **31-Band ISO Graphic Equalizer (`20 Hz – 20 kHz`, `±15 dB`)** dengan *True Bypass*.
   - **Linkwitz-Riley 24dB/oct Crossover (`40 Hz – 250 Hz`)** memisahkan jalur `SUB/LOW` dan `MID/HIGH`.
   - **Output Bus Matrix**:
     - `Stereo Headset / Bluetooth (L/R)` — Output stereo penuh untuk TWS, Headphone Bluetooth, atau IEM.
     - `2-Way Split (L=SUB | R=MID-HI)` — Menggunakan kabel splitter 3.5mm TRS ke Dual RCA/TS untuk memecah Sub & Mid-High langsung ke 2 *power amplifier* eksternal.
     - `CH1 SUB Only` & `CH2 MID/HIGH Only` — Untuk kalibrasi tiap jalur speaker.
   - **Alignment Delay (`0.0 – 50.0 ms`)** dengan konversi jarak otomatis (`cm`), **Phase 180°**, serta **Brickwall Peak Limiter**.
3. **60fps Real-Time Spectrum Analyzer (RTA) & VU/GR Meter**.

## Cara Build Menjadi `.apk`
1. **Via Android Studio (PC/Laptop):**
   - Ekstrak `DLMSProLive_Android.zip`, buka folder di Android Studio, tunggu Gradle sync selesai, lalu klik **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
2. **Langsung di HP Android (Tanpa PC via AndroidIDE):**
   - Instal aplikasi **AndroidIDE**, ekstrak folder proyek ini ke penyimpanan internal, buka lewat AndroidIDE, dan tekan tombol **Run / Build APK**.
3. **Via GitHub Actions (Cloud Build Otomatis):**
   - Upload isi folder ini ke repositori GitHub baru, buka tab **Actions**, jalankan workflow **Build Android APK**, lalu unduh file `app-debug.apk` di bagian *Artifacts*.

> **Catatan Penggunaan:** Saat memulai *Live Capture*, kecilkan volume bawaan YouTube/sistem atau gunakan aplikasi volume per-app (seperti Samsung Sound Assistant) jika suara asli masih terdengar bersamaan dengan suara hasil DSP dari aplikasi DLMS.

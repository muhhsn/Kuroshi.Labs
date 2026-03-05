# 🖥️ ZBRose Labs - AI System Monitor (TUI)

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![Theme](https://img.shields.io/badge/theme-TokyoNight-magenta)

**AI System Monitor** adalah aplikasi berbasis Terminal User Interface (TUI) yang dikembangkan oleh ZBRose Labs. Tool ini dirancang untuk memantau performa sistem, memanajemen *process* OS, dan mengontrol *container* Docker secara interaktif langsung dari *command line*. 

Keunggulan utama dari tool ini adalah integrasi **AI Guardrail** bertenaga Google Gemini yang memberikan peringatan dan analisis teknis instan sebelum Anda mengeksekusi tindakan berisiko (seperti mematikan *process* penting atau menghapus *junk file* sistem). Sangat dioptimalkan untuk berjalan mulus di berbagai *environment*, termasuk OS kustom seperti Windows 11 Ghost Spectre.

## ✨ Fitur Utama

* **📊 Ultra-Compact System Stats:** Memantau penggunaan CPU, RAM, Disk, dan mendeteksi penumpukan file *junk* (Temp & Prefetch) secara *real-time*.
* **🤖 AI Guardrail (Gemini Integration):** Menganalisis potensi risiko sebelum Anda melakukan tindakan destruktif (Kill Process, Stop Docker, Wipe Junk). AI akan memberikan peringatan teknis 1-2 kalimat.
* **🐳 Docker & Services Manager:** Mendeteksi dan mengelola *container* Docker yang sedang berjalan, serta layanan jaringan (*listening ports*) di latar belakang.
* **⚙️ Process Killer:** Tabel proses OS interaktif yang diurutkan berdasarkan penggunaan memori. Pilih proses, dan matikan langsung dari TUI.
* **🧹 Junk Cleaner Engine:** Memindai direktori Temp Windows secara otomatis dengan opsi *wipe* sekali klik.
* **🎨 TokyoNight Storm UI:** Antarmuka terminal yang cantik, modern, dan tidak membuat mata cepat lelah, dibangun menggunakan *framework* Textual.
* **📦 Auto-Dependency Installer:** Skrip akan otomatis mendeteksi dan menginstal *library* yang kurang saat pertama kali dijalankan.

## 🛠️ Persyaratan Sistem

* **Python:** Versi 3.8 atau lebih baru.
* **Terminal Emulator:** PowerShell, CMD, atau emulator modern lainnya (Zellij, Windows Terminal, dll). *Catatan: Script ini menolak berjalan di IDLE Shell karena keterbatasan rendering TUI.*
* **Docker Desktop/Daemon:** (Opsional) Jika ingin menggunakan fitur manajemen container.
* **API Key:** Google Gemini API Key untuk mengaktifkan fitur AI Guardrail.

## 🚀 Cara Instalasi & Penggunaan

1. **Clone Repository**
   ```bash
   git clone [https://github.com/username/zbrose-labs.git](https://github.com/username/zbrose-labs.git)
   cd zbrose-labs/nama-folder-monitor

2. Set up API Key (Environment Variable)
    Sangat disarankan untuk mengatur API Key Gemini sebagai variabel environment untuk alasan keamanan.

    Windows (PowerShell):
    PowerShell
   ```bash
    $env:GEMINI_API_KEY="your_api_key_here"
   ```
    Linux/macOS:
    ```Bash

    export GEMINI_API_KEY="your_api_key_here"

3. Jalankan Aplikasi
    Aplikasi dilengkapi dengan auto-installer untuk dependency. Cukup jalankan skrip utamanya:
   ```Bash

    python monitor_tui.py

⌨️ Panduan Navigasi (Keybindings)

Aplikasi ini sepenuhnya bisa dikendalikan menggunakan keyboard maupun mouse.
Tombol / Aksi	Fungsi
Klik Kiri	Memilih baris di tabel Process / Docker untuk memunculkan aksi.
j	Membuka modal Junk Scanner secara cepat.
r	Memaksa pembaruan data (Refresh Tables) secara manual.
q	Keluar dari aplikasi.
🏗️ Tech Stack

    Textual: Framework TUI utama untuk merender komponen UI secara asinkron.

    psutil: Mengambil informasi memori, CPU, disk, dan proses OS lintas platform.

    Docker SDK for Python: Berkomunikasi dengan Docker daemon lokal.

    Google Generative AI: Berkomunikasi dengan model gemini-2.5-flash untuk menghasilkan wawasan guardrail.

⚠️ Peringatan Keamanan (Disclaimer)

Tool ini dapat mematikan proses di level sistem operasi. Meskipun terdapat fitur AI Guardrail, mohon gunakan alat ini dengan hati-hati. ZBRose Labs tidak bertanggung jawab atas kerusakan sistem, kernel panic, atau kehilangan data yang disebabkan oleh penghentian proses kritis Windows secara paksa.

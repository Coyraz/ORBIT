# Mind Map — Project ORBIT

[← README](../README.md)

Transkripsi struktur **Project-Based Engineering Sprint — Briefing v1** yang diberikan untuk paket ini. Tujuh cabang, misi, fase tanggal, peran, Definition of Done dan dimensi evaluasi dipertahankan untuk dokumen tim. Nama project menggunakan ORBIT; peserta mengikuti kickoff brief. Gambar sumber tidak disertakan dalam paket; gunakan diagram dan outline berikut untuk berbagi.

## Mermaid

Diagram dapat dirender oleh penampil Markdown yang mendukung Mermaid. Outline di bawah menyediakan versi teks jika renderer tidak tersedia.

```mermaid
mindmap
  root((PROJECT ORBIT))
    Mission
      Multi-Robot Fleet Management System
      From Simulation to Real Robots
      Target TIFA dan NEVO
    1 Tujuan Utama
      Prototype FMS berbasis ROS 2
      Simulasi multi-robot dan validasi robot asli
      Repository GitHub end-to-end
      Binary package yang dapat diinstal
      Training dan evaluasi kesiapan tim ROS
    2 Scope Sistem
      Fleet manager
        Registrasi robot
        Assignment
        Status task
      Simulasi minimal dua robot di Gazebo
      Robot adapter TIFA dan NEVO
      Monitoring status health progress
      Reliability timeout dan failure handling
      Packaging dan documentation
    3 Timeline Sprint
      20 sampai 23 Oktober
        Ideation dan requirement
        Architecture dan feasibility
        Proof of Concept
        Integration review awal
      26 sampai 30 Oktober
        Fleet orchestration
        Physical robot integration
        System validation
        Binary packaging
        Final demo dan evaluation
      9 hari dan 36 jam efektif
    4 Peran Tim
      Product Owner dan Sponsor
        Kiki atau Rifqy
      Engineering Coordinator
      FMS Engineer
      Simulation dan Robotics Engineer
      Integration Engineer
      DevOps dan Release Engineer
      Satu orang dapat memegang beberapa peran
    5 Definition of Done
      Demo end-to-end simulasi
      TIFA dan NEVO lolos uji integrasi dasar
      Task dispatch dan status reporting berjalan
      Arsitektur dan setup terdokumentasi
      Binary release tersedia
      Final technical review dan individual defense
    6 Tech Stack dan Rules
      ROS 2 Jazzy
      Ubuntu 24.04
      Gazebo
      GitHub sumber utama engineering
      ClickUp opsional untuk tracking
      Safety existing robot tidak dioverride
      Reusable modular mudah diintegrasikan
    7 Evaluasi Peserta
      Technical quality
      Problem solving dan ownership
      Collaboration dan communication
      Documentation dan testing
      Kejelasan argumentasi teknis
      Final technical defense
```

## Outline untuk dibaca atau dibagikan

**Misi:** Multi-Robot Fleet Management System — from simulation to real robots. Target robot **TIFA + NEVO**.

1. **Tujuan utama:** prototype FMS berbasis ROS 2; simulasi multi-robot dan validasi robot asli; repository GitHub end-to-end; installable binary package; training dan evaluasi kesiapan tim ROS.
2. **Scope sistem:** fleet manager (registrasi, assignment, status task); minimal dua robot di Gazebo; adapter TIFA–NEVO; monitoring status, health dan progress; reliability (timeout dan failure handling dengan safety awareness); packaging dan dokumentasi.
3. **Timeline sprint:** 20–23 Oktober untuk ideation/requirements, architecture/feasibility, PoC dan integration review awal; 26–30 Oktober untuk fleet orchestration, physical integration, system validation, binary packaging, final demo dan evaluation. Total 9 hari/36 jam.
4. **Peran tim:** PO/Sponsor Kiki (Rifqy), Engineering Coordinator, FMS Engineer, Simulation/Robotics Engineer, Integration Engineer, DevOps/Release Engineer. Satu orang dapat memegang beberapa peran; lima peserta tercantum pada brief.
5. **Definition of Done:** demo end-to-end simulasi; uji integrasi dasar TIFA dan NEVO; task dispatch dan status reporting; arsitektur dan setup terdokumentasi; binary release; final technical review dan individual defense.
6. **Tech stack dan aturan:** ROS 2 Jazzy, Ubuntu 24.04, Gazebo; GitHub sebagai sumber utama; ClickUp opsional; safety existing tidak dioverride; reusable, modular dan mudah diintegrasikan.
7. **Evaluasi peserta:** technical quality, problem solving/ownership, collaboration/communication, documentation/testing, kejelasan argumentasi teknis dan final defense.

**Rangkaian output:** FMS Prototype → Simulation + Real Robot Validation → GitHub Repository → Binary Package.

Jadwal sesi: **16.00–18.00 dan 19.00–21.00 WIB**. Lihat [timeline harian](TIMELINE_9_DAYS.md) untuk pemecahan kegiatan.

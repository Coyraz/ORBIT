# PROJECT ORBIT
## Project-Based Engineering Sprint — Kickoff Brief

**Organizer:** Diagonal Robotics  
**Period:** 20–30 Oktober 2026 · 9 hari aktif · 36 jam efektif  
**Schedule:** 16.00–18.00 & 19.00–21.00 WIB  
**Participants:** Kiki, @aryadelphi, Reinald Mariel, @nasywa, @vacha  
**Platform:** ROS 2 Jazzy, Ubuntu 24.04, Gazebo

## Pengantar untuk tim

Selamat malam. Selama sembilan hari kerja ke depan, Diagonal Robotics menjalankan program internal **Engineering Sprint** untuk pelatihan dan seleksi kesiapan tim melalui sebuah project berbasis kebutuhan industri. Kita akan membangun, menguji, dan mempertanggungjawabkan solusi engineering secara bersama.

## The Mission

Rancang dan bangun **Multi-Robot Fleet Management System (FMS)** untuk sebuah fasilitas logistik fiktif yang membutuhkan koordinasi beberapa Autonomous Mobile Robots.

Sistem harus mampu menerima permintaan pekerjaan, menentukan robot pelaksana, memonitor proses, menerima hasil eksekusi, dan menangani kegagalan dasar. Solusi harus **reusable, modular**, serta dapat didistribusikan kepada pengguna sebagai **installable binary package**.

## Engineering Objectives

1. Merumuskan masalah dan kebutuhan sistem secara mandiri.
2. Menghasilkan beberapa alternatif pendekatan dan menganalisis trade-off.
3. Membuktikan feasibility melalui Proof of Concept.
4. Mengimplementasikan minimal dua robot pada simulasi.
5. Mengembangkan FMS dan robot integration interface.
6. Melakukan pengujian terkontrol pada TIFA dan NEVO.
7. Menghasilkan versioned binary release beserta dokumentasi.
8. Mempertanggungjawabkan setiap keputusan teknis.

## Deliverables

- Problem statement dan requirements.
- Feasibility matrix dan Architecture Decision Records.
- Fleet Manager dan Robot Adapter.
- Multi-robot simulation.
- TIFA dan NEVO integration test reports.
- Automated tests dan CI pipeline.
- GitHub repository dan installable binary release.
- Final demonstration dan individual technical defense.

## Engineering Rules

- Setiap engineer wajib berkontribusi pada ideation dan analisis solusi.
- Setiap modul harus memiliki owner, acceptance criteria dan evidence.
- Seluruh perubahan kode dilakukan melalui Git branch dan Pull Request.
- Keputusan desain penting harus terdokumentasi.
- Setiap kegagalan pengujian dicatat secara transparan.
- Sistem software tidak boleh mengabaikan mekanisme keselamatan robot.
- Gunakan aset dan data sintetis yang dibuat untuk studi kasus ini; seluruh materi repository harus boleh dibagikan kepada tim.

## Success Criteria — 30 Oktober

**Gate 1:** simulasi dua robot dan FMS end-to-end berfungsi.  
**Gate 2:** integrasi fisik TIFA dan NEVO divalidasi melalui pengujian aman dan terdokumentasi.  
**Gate 3:** binary package dapat diinstal pada environment target dan menghasilkan fungsi yang didemonstrasikan.  
**Gate 4:** seluruh engineer menyelesaikan technical defense dan evaluasi kontribusi individual.

**Final Output:** working prototype + physical validation + GitHub documentation + binary release + engineering evaluation report.

## Agenda kickoff — 20 Oktober, awal sesi 16.00

| Durasi | Agenda | Hasil |
| --- | --- | --- |
| 10 menit | Misi, scope dan empat gate | Pemahaman bersama |
| 10 menit | Pembagian peran, owner dan reviewer | Owner map awal |
| 10 menit | Cara kerja GitHub, evidence dan keselamatan | Aturan kerja dipahami |
| 10 menit | Tanya jawab dan batas kasus fiktif | Pertanyaan discovery |
| Sisa sesi | Problem discovery dan kebutuhan | Draft problem statement |

Baca [timeline](TIMELINE_9_DAYS.md), [challenge](PROJECT_CHALLENGE.md) dan [mind map](MIND_MAP.md) sebelum sesi dimulai. GitHub menjadi sumber utama engineering; ClickUp dapat digunakan untuk tracking.

# Sprint Charter

[← README](../README.md)

## Identitas dan tujuan

| Elemen | Ketetapan |
| --- | --- |
| Project | ORBIT — Project-Based Engineering Sprint |
| Penyelenggara | Diagonal Robotics |
| Product Owner / Sponsor | Kiki (Rifqy) |
| Periode | 20–30 Oktober 2026; 9 hari aktif, 36 jam per peserta |
| Sesi | 16.00–18.00 dan 19.00–21.00 WIB |
| Platform wajib | ROS 2 Jazzy dan Ubuntu 24.04 |
| Target | Simulasi minimal dua robot; integrasi fisik TIFA dan NEVO |

Sprint menggabungkan pengembangan prototype industrial-based, pelatihan engineering, dan evaluasi kesiapan tim. Peserta harus menunjukkan kemampuan merumuskan masalah, membandingkan alternatif, menguji feasibility, mengintegrasikan sistem, dan menjelaskan keputusan teknis dengan bukti.

## Engineering objectives

1. Merumuskan masalah dan kebutuhan sistem secara mandiri.
2. Menghasilkan beberapa alternatif pendekatan dan menganalisis trade-off.
3. Membuktikan feasibility melalui Proof of Concept (PoC).
4. Mengimplementasikan minimal dua robot pada simulasi.
5. Mengembangkan FMS dan robot integration interface.
6. Melakukan pengujian terkontrol pada TIFA dan NEVO.
7. Menghasilkan versioned binary release beserta dokumentasi.
8. Mempertanggungjawabkan setiap keputusan teknis.

## Scope

**Wajib:** robot registration, capability/availability, assignment, task lifecycle, robot adapter, monitoring status/health/progress, timeout dan failure handling dasar, simulasi multi-robot, integrasi TIFA–NEVO, automated tests, CI, binary packaging, dokumentasi dan evaluasi individu.

**Batas sprint:** prototype untuk skenario logistik fiktif yang terkontrol. Optimasi fleet skala besar, sertifikasi keselamatan, rollout operasional, dashboard kompleks, perubahan hardware besar dan manipulasi payload otomatis tidak menjadi baseline. Tambahan fitur harus melewati review dampak terhadap empat gate.

Pemilihan scheduler, transport antarmuka, strategi navigasi dan format binary dibuktikan melalui feasibility matrix dan ADR. Baseline simulator yang dipakai dalam paket ini adalah Gazebo Harmonic, pasangan yang didukung untuk Jazzy; catat versi dependency aktual sebelum integrasi.

## Deliverables dan bukti

| Deliverable | Bukti minimum | Target |
| --- | --- | --- |
| Problem statement dan requirements | Kebutuhan ber-ID, scope dan skenario uji | D1 |
| Feasibility matrix dan ADR | Alternatif, trade-off, hasil PoC, keputusan | D2–D3 |
| Fleet Manager dan Robot Adapter | Kode, PR, kontrak interface, tes | D3–D6 |
| Multi-robot simulation | Launch/config, runbook, log dan demo dua robot | D4 |
| Physical validation | Laporan TIFA dan NEVO, prasyarat, hasil dan limitasi | D6–D7 |
| Automated tests dan CI | Hasil unit/integration test pada commit yang sama | D2–D8 |
| Repository dan binary release | Tag, artifact, checksum, clean-install report | D8–D9 |
| Demo dan individual defense | Evidence index, review dan scorecard tiap engineer | D9 |

## Gate dan keputusan

Empat gate final mengikuti [Acceptance Criteria](ACCEPTANCE_CRITERIA.md). D4 menjadi review awal G1, D7 review G2, D8 rehearsal G3, D9 keputusan akhir G1–G4. Lulus gate memerlukan evidence yang dapat ditelusuri ke commit/artifact dan review oleh orang selain pembuatnya.

PO menetapkan scope dan menerima hasil sprint. Engineering Coordinator mengelola dependency dan integrasi. Owner modul bertanggung jawab atas implementasi dan evidence; reviewer memeriksa hasil. Jika gate terblokir, catat alasan, dampak, owner perbaikan dan jadwal ulang; jangan mengubah status menjadi lulus untuk mengejar jadwal.

## Risiko utama

| Risiko | Penanganan | Pemicu eskalasi |
| --- | --- | --- |
| Hardware/jaringan tidak siap | Inventaris dan bench check sejak D1; adapter diuji terpisah | Akses robot belum siap pada D3 |
| Kontrak antar modul berbeda | Bekukan kontrak awal D2, versioning dan contract tests | Perubahan memutus adapter atau FMS |
| Scope terlalu besar | Dahulukan alur end-to-end minimum | Target harian tidak tercapai |
| Konflik namespace/TF/waktu | Isolasi identitas robot dan cek konfigurasi | Robot menerima task milik robot lain |
| Binary hanya bekerja di mesin pembuat | Clean-install rehearsal D8 | Dependensi tidak tercatat |
| Perilaku robot tidak aman | Operator, area uji, stop dan inspeksi sebelum gerak | Stop/health check gagal |

## Perubahan scope

Buat issue berisi alasan, alternatif, dampak jadwal, acceptance criteria dan keputusan PO. Perubahan desain signifikan memiliki ADR. Perubahan setelah G1 harus menjalankan ulang tes yang terdampak dan memperbarui runbook.

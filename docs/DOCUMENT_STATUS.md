# Dasar Dokumen & Keputusan yang Perlu Ditetapkan

[← README](../README.md)

Versi paket: **1.0 · 19 Oktober 2026**. Dokumen ini membedakan isi brief dari rincian implementasi yang masih harus diputuskan tim.

## Dasar penyusunan

| Sumber | Bagian yang digunakan |
| --- | --- |
| Kickoff brief yang diberikan organizer | Nama ORBIT, penyelenggara, peserta, platform, misi, objectives, deliverables, aturan dan empat gate |
| Project-Based Engineering Sprint — Briefing v1 | Mind map tujuh cabang, 20–23 dan 26–30 Oktober, 9 hari/36 jam, peran, Definition of Done, dimensi evaluasi |
| Daftar 14 tahap sprint di tracker | Pemetaan discovery sampai handoff; tautan di Task Map |
| Dokumentasi resmi Gazebo | Pasangan ROS 2 Jazzy–Gazebo Harmonic untuk Ubuntu 24.04 |

Mind map Markdown merupakan transkripsi untuk tim dari Briefing v1. Gambar sumber tidak dibundel. Deskripsi rinci task tracker tidak berhasil diambil karena batas akses harian; pemecahan sesi dan kriteria operasional disusun dari brief dan mind map, bukan diklaim sebagai salinan deskripsi task.

## Ketetapan dari brief

ORBIT diselenggarakan Diagonal Robotics pada 20–30 Oktober 2026 dengan 9 hari aktif/36 jam; sesi 16.00–18.00 dan 19.00–21.00 WIB; lima peserta tercantum pada kickoff. ROS 2 Jazzy dan Ubuntu 24.04 menjadi platform. Targetnya simulasi minimal dua robot, integrasi TIFA dan NEVO, installable binary release, serta defense/evaluasi individu. Seluruh engineer melakukan ideation; modul memiliki owner, acceptance criteria dan evidence; perubahan kode melalui branch/PR.

## Rincian operasional untuk dikonfirmasi

| Keputusan | Target penetapan | Penanggung jawab | Tempat pencatatan |
| --- | --- | --- | --- |
| Owner/reviewer tiap modul | Kickoff D1 | Coordinator + PO + tim | Team Roles dan issue |
| Detail kebutuhan dan skenario acceptance | D1–D2 | Owner + reviewer | Requirements dan Acceptance Criteria |
| Bobot, anchor, kategori dan evaluator penilaian | Kickoff D1 | PO + evaluator | Evaluation Rubric |
| Algoritma assignment, transport dan kontrak | D2 | Tim engineering | Feasibility dan ADR |
| Format binary, target arsitektur dan dependency | D2 | Release + integration | ADR dan release plan |
| Timeout, retry, toleransi navigasi | Sebelum tes terkait | Owner + reviewer | Kontrak/config dan test report |
| Batas operasi, operator dan prosedur stop fisik | Sebelum run fisik | Integration + operator | Preflight dan runbook |

Detail harian, bobot evaluasi, kebutuhan ber-ID, template, serta contoh struktur package adalah elaborasi operasional. Tidak ada hasil uji, CI lulus, binary terbit, branch protection aktif atau gate lulus yang diasumsikan.

## Pemeliharaan

Jika ada perubahan, perbarui dokumen terkait dalam PR yang sama. Kontrak atau pilihan teknis signifikan memakai ADR. Jangan menghapus hasil tes gagal; tambahkan retest dan relasinya. Bukti final harus sesuai commit/artifact yang didemonstrasikan.

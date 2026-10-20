# Team Roles & Ownership

[← README](../README.md)

## Peserta

| Peserta | Identitas dalam brief | Penugasan |
| --- | --- | --- |
| Kiki (Rifqy) | Kiki | Product Owner / Sponsor sesuai Briefing v1; kontribusi teknis dicatat bila memegang modul |
| Arya Delphi | @aryadelphi | Peran teknis ditetapkan pada kickoff |
| Reinald Mariel | Reinald Mariel | Peran teknis ditetapkan pada kickoff |
| Nasywa | @nasywa | Peran teknis ditetapkan pada kickoff |
| Vacha | @vacha | Peran teknis ditetapkan pada kickoff |

Briefing v1 menyebut kapasitas 5–6 engineer; daftar kickoff saat ini memuat **lima peserta**. Tidak ada peserta keenam yang diasumsikan. Satu orang dapat memegang lebih dari satu peran. Pembagian teknis belum ditentukan dalam sumber yang diberikan.

## Peran dan akuntabilitas

| Peran | Tanggung jawab | Output yang dipertanggungjawabkan |
| --- | --- | --- |
| Product Owner / Sponsor | Menetapkan kebutuhan, prioritas, scope dan penerimaan hasil | Charter, keputusan scope, status gate dan evaluasi akhir |
| Engineering Coordinator | Menjaga kontrak, dependency, integrasi, review dan ritme sprint | Arsitektur, ADR, integration plan, status blocker |
| FMS Engineer | Registrasi, assignment, lifecycle, antrean dan reliability | Fleet core, kontrak, tes dan log task |
| Simulation / Robotics Engineer | World, robot, navigasi, namespace/TF dan skenario | Simulasi dua robot, runbook dan evidence G1 |
| Integration Engineer | Adapter TIFA–NEVO, inspeksi, operator coordination dan uji fisik | Interface mapping dan laporan G2 per robot |
| DevOps / Release Engineer | Build/test automation, CI, versioning, packaging dan install | Pipeline, artifact, checksum dan clean-install report |

## Owner map — isi saat kickoff

| Area | Owner | Reviewer selain owner | Target |
| --- | --- | --- | --- |
| Koordinasi engineering dan arsitektur | Belum ditetapkan | Belum ditetapkan | D1–D9 |
| Fleet core dan kontrak | Belum ditetapkan | Belum ditetapkan | D2–D7 |
| Simulasi multi-robot | Belum ditetapkan | Belum ditetapkan | D2–D4 |
| Adapter TIFA | Belum ditetapkan | Belum ditetapkan | D5–D7 |
| Adapter NEVO | Belum ditetapkan | Belum ditetapkan | D5–D7 |
| CI dan binary release | Belum ditetapkan | Belum ditetapkan | D2–D9 |
| Evidence index dan runbook | Belum ditetapkan | Belum ditetapkan | D1–D9 |

## Cara membagi pekerjaan

1. Coordinator mencocokkan minat, kesiapan teknis dan kebutuhan modul.
2. Setiap modul memiliki satu owner utama dan satu reviewer; pairing boleh melibatkan siapa pun.
3. Owner bertanggung jawab pada interface, acceptance criteria, evidence dan handoff, meski implementasinya dikerjakan bersama.
4. Seluruh peserta tetap wajib melakukan ideation, review, dokumentasi dan technical defense.
5. Operator robot dan pendamping keselamatan ditunjuk sebelum setiap sesi fisik; role software tidak otomatis memberi izin menggerakkan robot.

Jika PO juga menjadi implementer, penerimaan teknis pekerjaannya harus disertai reviewer lain. Semua peserta menjalani defense; untuk penilaian kontribusi PO, gunakan evaluator selain dirinya sendiri.

## Eskalasi

Owner melaporkan blocker di issue dan update sesi: dampak, bukti, upaya yang dicoba, kebutuhan bantuan dan keputusan yang diperlukan. Coordinator mengatur dependency dan recovery; PO memutus perubahan scope atau trade-off yang mengubah target sprint. Temuan keselamatan menghentikan pengujian fisik sampai prasyarat dipenuhi kembali.

# Evaluation Rubric — Individual Engineering Review

[← README](../README.md)

Dimensi mengikuti Briefing v1: technical quality, problem solving & ownership, collaboration & communication, documentation & testing, kejelasan argumentasi teknis, dan final technical defense. **Bobot, skala dan kategori di bawah adalah usulan operasional**, ditetapkan PO/evaluator pada kickoff sebelum dipakai untuk penilaian.

## Dimensi dan bobot usulan

| Dimensi | Bobot | Hal yang dinilai | Bukti utama |
| --- | --- | --- | --- |
| Technical quality | 25% | Kebenaran implementasi, modularitas, kontrak, error handling dan maintainability | PR, kode, contract/system tests |
| Problem solving & ownership | 20% | Rumusan masalah, alternatif, eksperimen, penanganan blocker dan penyelesaian tanggung jawab | Feasibility, PoC, ADR, issue dan recovery |
| Collaboration & communication | 15% | Review yang berguna, koordinasi dependency, pairing dan pelaporan jujur | Review PR, catatan integrasi, update sesi |
| Documentation & testing | 20% | Reproducibility, cakupan normal/gagal, evidence dan kejelasan runbook | Test reports, CI, setup dan release docs |
| Kejelasan argumentasi teknis | 10% | Hubungan kebutuhan, keputusan, bukti, trade-off dan limitasi | ADR dan penjelasan saat review |
| Final technical defense | 10% | Pemahaman kontribusi sendiri dan sistem, kemampuan menjawab serta diagnosis | Catatan defense individual |
| **Total** | **100%** | | |

## Skala per dimensi

| Skor | Anchor penilaian |
| --- | --- |
| 1 | Bukti sangat terbatas; pekerjaan atau pemahaman tidak memenuhi kebutuhan dasar; perlu pendampingan intensif |
| 2 | Sebagian hasil tersedia, tetapi ada gap penting; penjelasan/tes masih memerlukan banyak bantuan |
| 3 | Memenuhi tanggung jawab yang disepakati; hasil dapat dijelaskan dan dibuktikan dengan pendampingan wajar |
| 4 | Hasil konsisten, mandiri, mempertimbangkan trade-off dan membantu integrasi tim |
| 5 | Hasil kuat dan dapat direproduksi; mengantisipasi failure, memperbaiki sistem kerja dan menjelaskan batas solusi secara matang |

Evaluator memberi alasan singkat dan minimal satu bukti spesifik untuk setiap skor. Bila bukti belum cukup, beri **NE (not evaluated)** dan rencana pelengkapan; jangan mengubah NE menjadi nol atau menghitung nilai final seolah lengkap.

**Rumus usulan:** nilai akhir = Σ(bobot dalam persen × skor / 5), dengan rentang 20–100 bila seluruh skor terisi 1–5. Contoh skor `[4, 3, 4, 3, 4, 3]` menghasilkan `20 + 12 + 12 + 12 + 8 + 6 = 70`.

Kategori rekomendasi usulan: **85–100** siap mengambil ownership lebih besar; **70–<85** siap dengan pendampingan terarah; **55–<70** perlu penguatan kompetensi tertentu; **<55** perlu training lanjutan sebelum ownership mandiri. Kategori ini bukan keputusan otomatis penempatan tim.

## Pelaksanaan defense

Alokasi D9: 20 menit per peserta — 5 menit presentasi kontribusi dan evidence, 10 menit tanya jawab, 5 menit feedback. Peserta menunjukkan:

1. Masalah yang ia tangani dan batas tanggung jawabnya.
2. Alternatif, trade-off dan alasan keputusan.
3. Kode/kontrak/tes atau kontribusi engineering yang benar-benar ia kerjakan.
4. Satu kegagalan, diagnosis, perbaikan dan bukti retest.
5. Hubungan modulnya dengan FMS, simulasi, robot fisik dan release.
6. Limitasi serta rekomendasi next step.

Kejelasan argumentasi menilai kualitas alasan sepanjang sprint; final defense menilai pemahaman dan respons saat sesi akhir. Catat keduanya agar penilaian tidak hanya mengulang kesan presentasi.

## Konsistensi dan keadilan

Bandingkan hasil terhadap peran dan scope yang disepakati. Hargai review, integrasi, diagnosis, dokumentasi dan kerja pairing dengan atribusi jelas. Jangan menilai berdasarkan banyaknya commit atau jam online saja. Kontribusi kelompok harus disertai penjelasan bagian masing-masing.

PO dan reviewer memberi penilaian dengan bukti; peserta diberi kesempatan mengoreksi atribusi faktual. Evaluator tidak menilai dirinya sendiri. Pelanggaran keselamatan atau pelaporan yang tidak jujur dicatat sebagai temuan tersendiri untuk ditinjau PO; skor tinggi tidak menggantikan gate yang gagal.

Gunakan [Individual Defense](../templates/INDIVIDUAL_DEFENSE.md). Laporan akhir mencantumkan kekuatan, gap kompetensi, rekomendasi peran, tindakan latihan berikutnya dan batas kesimpulan.

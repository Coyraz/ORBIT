# Acceptance Criteria & Definition of Done

[← README](../README.md)

Empat gate berasal dari kickoff brief. Rincian skenario di bawah adalah baseline operasional yang perlu dikonfirmasi pada D1–D2. Angka timeout, retry, toleransi navigasi dan batas fisik ditetapkan sebelum tes pada requirements/konfigurasi dan dicatat dalam laporan. Tidak ada hasil uji yang diklaim oleh paket dokumentasi ini.

Status yang digunakan: **NOT RUN**, **PASS**, **FAIL**, **BLOCKED**. PASS memerlukan expected = actual dalam batas yang ditetapkan dan reviewer selain pembuat. BLOCKED harus menyebut dependency, owner dan tindakan berikutnya.

## G1 — Simulasi dua robot dan FMS end-to-end

| ID | Given / When | Hasil yang harus terlihat | Evidence |
| --- | --- | --- | --- |
| G1-01 | FMS dan minimal dua robot simulator dijalankan | Dua robot terdaftar dengan identitas unik; health dan availability terpisah | Registry snapshot dan log startup |
| G1-02 | Pekerjaan valid diajukan | Task diterima, robot eligible dipilih, adapter menerima dispatch | Log task_id/robot_id dan alasan assignment |
| G1-03 | Robot mengeksekusi task | Feedback/progress terlihat dan hasil terminal diterima FMS | Event lifecycle dan video/log |
| G1-04 | Dua pekerjaan tersedia | Tidak ada task dimiliki ganda; setiap robot menerima pekerjaan yang sesuai; kebijakan antrean jelas | Trace kedua task dan automated test |
| G1-05 | Tujuan invalid atau tidak ada robot eligible | Input ditolak dengan alasan atau masuk antrean sesuai kontrak; tidak ada false success | Test report input invalid dan fleet unavailable |
| G1-06 | Robot stale/disconnect, reject atau eksekusi gagal | Timeout/failure terdeteksi sesuai konfigurasi; robot tidak sehat tidak diberi task baru; tidak ada task menggantung tanpa status | Fault injection, timestamp dan state akhir |
| G1-07 | Task/event duplikat dikirim | Tidak ada eksekusi ganda tak terkendali; hasil konsisten dengan kebijakan deduplikasi | Contract test dan log |
| G1-08 | Operator lain mengikuti runbook | Simulasi dua robot dan alur demo dapat diulang | Runbook, commit dan review |

Kebijakan cancel/retry/reconnect/restart harus didefinisikan beserta batas dukungannya. Minimal satu jalur failure dan recovery diuji; fitur yang tidak didukung ditolak secara eksplisit dan dicatat, bukan dipresentasikan sebagai tersedia.

## G2 — Validasi fisik TIFA dan NEVO

Kriteria G2-01 sampai G2-05 diperiksa **terpisah untuk masing-masing robot**.

| ID | Skenario | Hasil yang diterima | Evidence |
| --- | --- | --- | --- |
| G2-01 | Preflight robot | Operator, area, stop, batas operasi, hardware/network dan konfigurasi terverifikasi | Checklist bertanggal dan penanggung jawab |
| G2-02 | Koneksi dan registrasi | Identitas, status, health dan adapter mapping benar | Log dan interface mapping |
| G2-03 | Task fisik terkontrol | Dispatch, feedback dan hasil terminal terlihat pada FMS, sesuai tujuan uji | Run report dan video/log robot |
| G2-04 | Stop atau kondisi keselamatan terkontrol | Mekanisme existing tetap efektif; FMS mencatat kondisi dan tidak memberi task baru saat tidak eligible | Catatan operator, status FMS dan reviewer |
| G2-05 | Gangguan dasar dan recovery | Respons sesuai kontrak tanpa gerakan/eksekusi ulang tak terkendali; batas tes fisik vs bench dinyatakan | Fault report, recovery steps dan retest |
| G2-06 | FMS mengoordinasikan TIFA dan NEVO | Kedua adapter menggunakan kontrak bersama; pengendalian area/jalur terdokumentasi; hasil kedua robot dapat ditelusuri | System test, diagram dan trace dua robot |

Jika robot tidak tersedia atau preflight gagal, status G2 adalah BLOCKED/FAIL sesuai penyebab. Simulasi, fake adapter atau video lama tidak menggantikan physical validation.

## G3 — Versioned binary release dan clean install

| ID | Skenario | Hasil yang diterima | Evidence |
| --- | --- | --- | --- |
| G3-01 | Release candidate dibuat | Tag/version, commit, target OS/ROS/arsitektur dan dependency dinyatakan | Release notes dan metadata artifact |
| G3-02 | Artifact dibangun | Binary dapat diunduh/disalin sebagai installable package dengan checksum; source ZIP saja tidak cukup | Artifact dan SHA-256 |
| G3-03 | Environment target bersih digunakan | Install berhasil tanpa source workspace, tanpa build project secara manual, dan tanpa dependency tersembunyi | Laporan clean install oleh reviewer |
| G3-04 | Smoke test dijalankan | Binary terpasang menjalankan fungsi demo yang dinyatakan; config dan perintah startup jelas | Log startup, dispatch dan hasil |
| G3-05 | Release direview | CI/tests relevan lulus untuk commit release; limitations, uninstall/rollback dan setup terdokumentasi | CI report dan runbook |

Minimal satu arsitektur mesin target diuji. Dukungan arsitektur lain hanya diklaim jika memiliki artifact dan bukti install sendiri. Ubuntu 24.04 dan ROS 2 Jazzy tetap menjadi baseline; versi dependency aktual dibekukan pada release.

## G4 — Defense dan evaluasi individual

| ID | Pemeriksaan | Evidence |
| --- | --- | --- |
| G4-01 | Semua engineer menunjukkan kontribusi ideation dan analisis alternatif | Feasibility/ADR, issue dan catatan review |
| G4-02 | Kontribusi implementasi, review, tests dan dokumentasi dapat ditelusuri | PR/commit/evidence per individu |
| G4-03 | Setiap engineer menyelesaikan technical defense | Catatan pertanyaan, jawaban dan scorecard |
| G4-04 | Engineering evaluation report berisi hasil setiap peserta dan tindakan lanjut | Scorecard bertanggal dan evaluator |

G4 menilai penyelesaian proses evaluasi untuk semua peserta. Nilai individu dan rekomendasi kesiapan tim dicatat terpisah; jumlah commit bukan satu-satunya ukuran kontribusi.

## Final Definition of Done

- [ ] G1 PASS dengan bukti simulasi minimal dua robot.
- [ ] G2 PASS untuk TIFA dan NEVO serta integrasi sistem.
- [ ] G3 PASS untuk artifact binary yang sama dengan release final.
- [ ] G4 PASS; seluruh peserta memiliki defense dan evaluation record.
- [ ] README, arsitektur, setup, kontrak, test reports, known issues dan release notes lengkap.
- [ ] Semua evidence dapat ditelusuri ke commit/artifact yang tepat.
- [ ] Owner dan reviewer mencatat keputusan akhir.

Gunakan [Gate Review](../templates/GATE_REVIEW.md). Jika ada kotak belum terpenuhi, laporkan hasil sebagai **prototype parsial dengan gap yang disebutkan**, bukan seluruh sprint selesai.

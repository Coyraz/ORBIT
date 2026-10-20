# Engineering Workflow

[← README](../README.md)

## Alur kerja engineering

**Discover → Ideate → Compare → Decide → Prove → Implement → Integrate → Validate → Package → Defend.**

| Tahap | Aktivitas | Syarat keluar |
| --- | --- | --- |
| Discover | Rumuskan problem, stakeholder fiktif, FR/NFR dan scope | Requirements ber-ID dan test intent |
| Ideate / Compare | Kontribusi tiap engineer; bandingkan alternatif dan risiko | Feasibility matrix dengan alasan dan bukti |
| Decide | Pilih batas modul, kontrak dan pendekatan | ADR dan reviewer tercatat |
| Prove | PoC pada risiko utama | Hipotesis, eksperimen, hasil dan keputusan lanjut |
| Implement | Pecah menjadi issue kecil, branch dan PR | Kode, tests dan dokumentasi |
| Integrate | Hubungkan FMS, simulator dan adapter | Contract test dan demo vertikal |
| Validate | Jalankan skenario normal dan gagal; uji fisik terkontrol | Evidence dan status acceptance criteria |
| Package | Build artifact, versioning dan clean install | G3 dengan artifact yang sama seperti demo |
| Defend | Jelaskan keputusan dan kontribusi | Scorecard individual dan action items |

## GitHub sebagai sumber utama

Issue menyimpan tujuan, owner, reviewer, acceptance criteria, dependency dan evidence. PR menghubungkan perubahan dengan issue serta hasil uji. ADR menyimpan keputusan penting. Tag/release menunjuk artifact berversi. Jika memakai ClickUp, tautkan ke issue/PR yang relevan agar keputusan tidak hanya berada di chat atau tracker.

### Branch dan commit

Gunakan branch untuk setiap perubahan; contoh `feat/task-dispatch`, `fix/adapter-timeout`, `docs/tifa-runbook`. Gunakan commit ringkas dengan tujuan jelas, misalnya `feat: add robot eligibility checks`. Hindari memasukkan build output, credential, data mentah yang tidak diperlukan atau konfigurasi mesin pribadi.

```bash
git switch -c feat/task-dispatch
# Kerjakan perubahan, tes dan dokumentasi.
git add src/ tests/ docs/
git commit -m "feat: add task dispatch"
git push -u origin feat/task-dispatch
```

Contoh di atas berlaku setelah direktori implementasi dibuat. Periksa file yang akan disertakan sebelum commit. Seluruh perubahan kode masuk melalui PR, termasuk perbaikan yang dibuat menjelang demo. Owner tidak menyetujui PR-nya sendiri.

### PR siap merge ketika

- Issue dan acceptance criteria jelas; perubahan cukup kecil untuk ditinjau.
- Tes yang relevan lulus, dan hasilnya merujuk commit yang ditinjau.
- Reviewer memeriksa kontrak, error handling, logging dan dampak pada modul lain.
- Dokumentasi/setup berubah jika perilaku atau dependency berubah.
- Tidak ada blocker yang disembunyikan; keterbatasan tertulis.

Aktifkan perlindungan branch dan required checks ketika konfigurasi repository memungkinkan. Paket dokumentasi ini tidak mengklaim pengaturan tersebut sudah aktif.

## CI dan pengujian

Pipeline implementasi ditargetkan berjalan pada Ubuntu 24.04 dengan ROS 2 Jazzy: dependency setup, build, lint, unit tests dan integration/contract tests. Tambahkan simulation smoke test yang memungkinkan secara headless. Uji fisik tetap menggunakan laporan operator; CI tidak membuktikan robot aman.

Pisahkan tahap build/test PR dan release artifact pada tag. Release candidate harus menunjuk commit yang checks-nya lulus; jika ada perubahan sesudah verifikasi, ulangi checks yang terdampak dan clean-install smoke test untuk artifact baru.

Setiap run memakai task_id, robot_id, run_id dan timestamp agar dispatch, feedback, hasil dan error dapat ditelusuri. Status task dan health robot harus dapat dibedakan. Aturan duplicate task, timeout, retry, cancel, reconnect dan restart diputuskan di kontrak/ADR; retry tidak boleh menyebabkan satu pekerjaan dieksekusi ulang tanpa kontrol.

## Integrasi bertahap

1. Contract test terhadap adapter fake/test double.
2. PoC satu task end-to-end.
3. Simulasi dua robot dengan identitas dan TF terpisah.
4. Fault injection di simulasi atau bench environment.
5. Physical preflight dan uji TIFA serta NEVO secara terpisah.
6. System test dengan koordinasi kedua robot pada area terkontrol.
7. Regresi dan clean install binary.

Gunakan waktu simulasi untuk node simulator yang memerlukannya; pada robot fisik gunakan konfigurasi waktu yang sesuai. Dokumentasikan clock, frame, namespace, QoS dan timeout dalam kontrak. Jangan menyalin parameter simulator ke robot fisik tanpa inspeksi.

## Pengujian fisik

Sebelum bergerak, tetapkan operator, pendamping keselamatan, area steril, batas operasi, mekanisme stop dan cara recovery. Verifikasi stop dan health check sesuai prosedur robot. Jika kondisi berubah atau stop tidak dapat diverifikasi, hentikan run. FMS dan adapter tidak boleh override mekanisme keselamatan existing.

Saat fault injection fisik, pilih tindakan yang tetap aman. Uji hilangnya koneksi atau kegagalan navigasi dapat dilakukan di bench/simulasi jika tidak aman dilakukan sambil robot bergerak; catat batas cakupan bukti dengan jelas.

## Evidence dan Definition of Done modul

Gunakan [Test Report](../templates/TEST_REPORT.md) dan [evidence index](../evidence/README.md). Setiap hasil berisi commit/artifact, environment, langkah, expected/actual, status, log dan reviewer. Kegagalan disimpan beserta retest; jangan menimpa catatan run gagal dengan run yang lulus.

Modul selesai ketika implementasi direview, acceptance criteria terbukti, tes relevan lulus, cara menjalankan dan limitasi terdokumentasi, serta owner menyerahkan evidence. Selesainya modul tidak otomatis meluluskan semua gate sprint.

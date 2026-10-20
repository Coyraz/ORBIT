# Project Challenge — Multi-Robot Logistics FMS

[← README](../README.md)

## Konteks studi kasus

Sebuah fasilitas logistik **fiktif** memiliki beberapa titik pengambilan dan pengantaran, area parkir, serta jalur yang digunakan bersama. Operator mengirim permintaan perpindahan barang. TIFA dan NEVO memiliki karakteristik serta antarmuka yang berbeda; keduanya perlu dilayani oleh satu FMS tanpa menanamkan seluruh detail robot ke logika fleet.

Untuk sprint, pekerjaan dapat direpresentasikan sebagai misi perpindahan antar waypoint. Kegiatan muat/bongkar dapat berupa konfirmasi sintetis; otomatisasi mekanis tidak diwajibkan. Nama lokasi, peta, pekerjaan dan parameter demo dibuat khusus untuk studi kasus ini.

## Tantangan inti

Bagaimana membangun FMS modular yang dapat mengoordinasikan minimal dua robot, memperlihatkan status yang dapat dipercaya, menangani kegagalan dasar, dan dipasang ulang dari binary pada environment target?

## Kebutuhan awal untuk dielaborasi D1

| ID | Kebutuhan | Bukti yang dirancang |
| --- | --- | --- |
| FR-01 | Terima permintaan dengan identitas unik dan tujuan valid | Input valid/invalid dan hasil validasi |
| FR-02 | Registrasikan robot dan tampilkan availability/capability | Registry dua robot dan perubahan health |
| FR-03 | Pilih robot yang eligible dan tersedia | Jejak alasan assignment; tidak ada double assignment |
| FR-04 | Dispatch task melalui kontrak adapter yang sama | Contract test simulator, TIFA dan NEVO |
| FR-05 | Laporkan lifecycle dan hasil task | Event/log berkorelasi task_id dan robot_id |
| FR-06 | Monitor health, status dan progress | Tampilan/log yang membedakan data aktif dan stale |
| FR-07 | Tangani timeout, reject, disconnect dan failure | Fault injection dan hasil yang dapat dijelaskan |
| FR-08 | Jalankan minimal dua robot di simulasi | Runbook end-to-end dari environment bersih |
| FR-09 | Validasi adapter TIFA dan NEVO secara fisik | Laporan masing-masing robot |
| FR-10 | Distribusikan binary berversi dan dokumentasi | Artifact, checksum dan clean-install report |
| NFR-01 | Pisahkan fleet logic dari detail platform robot | Arsitektur dan penggantian adapter tanpa mengubah scheduler |
| NFR-02 | Buat hasil uji dapat direproduksi | Commit, dependency, config, langkah dan expected/actual |
| NFR-03 | Pertahankan mekanisme keselamatan robot | Review dan uji stop terkontrol |
| NFR-04 | Sediakan automated tests dan CI | Pipeline serta test report pada release candidate |

Kebutuhan ini menerjemahkan brief menjadi backlog awal. Owner dan reviewer memfinalisasi detail pada D1–D2. Ambang timeout, batas retry, toleransi navigasi dan batas kecepatan harus ditetapkan dengan alasan dan dicatat sebelum tes; paket ini tidak menetapkan angka fisik tanpa inspeksi robot.

## Ideation wajib untuk semua engineer

Setiap peserta mengusulkan pendekatan, mengidentifikasi risiko, dan meninjau setidaknya satu alternatif anggota lain. Bahas minimal:

- Dispatch terpusat atau pendekatan terdistribusi; alasan kecocokannya untuk sprint.
- Assignment sederhana berbasis availability/capability atau biaya/jarak; data yang diperlukan.
- ROS 2 topic, service atau action untuk tiap jenis interaksi; feedback, hasil, cancel dan kegagalan.
- Adapter terpisah per robot dan kontrak bersama; batas tanggung jawab navigasi dan keselamatan.
- Antrean, penolakan dan recovery ketika tidak ada robot eligible.
- Packaging dan dukungan arsitektur mesin target.

Gunakan [feasibility template](../templates/FEASIBILITY_MATRIX.md). PoC menguji risiko terbesar terlebih dahulu; pemilihan tidak didasarkan pada popularitas teknologi saja.

## Alur demonstrasi minimum

1. Jalankan FMS dan dua robot simulasi dengan identitas terpisah.
2. Registrasikan robot dan perlihatkan status tersedia.
3. Kirim task ke tujuan valid; tunjukkan keputusan assignment.
4. Kirim pekerjaan berikutnya; tunjukkan alokasi tanpa benturan kepemilikan task.
5. Perlihatkan feedback, status terminal dan hasil yang konsisten.
6. Suntikkan satu kegagalan terkontrol; buktikan timeout/failure tercatat dan robot yang tidak sehat tidak menerima pekerjaan baru.
7. Jalankan pengujian fisik terkontrol pada TIFA dan NEVO dengan runbook masing-masing.
8. Pasang binary pada environment bersih dan ulangi smoke test yang dinyatakan dalam release notes.

## Pertanyaan technical defense

Mengapa desain ini dipilih? Alternatif apa yang ditolak? Di mana bukti feasibility? Apa yang terjadi saat feedback hilang atau task dikirim dua kali? Bagaimana membedakan status task dan health robot? Apa yang berubah antara simulator dan robot fisik? Apa batas prototype? Bagaimana orang lain menginstal dan mengujinya tanpa bantuan pembuat?

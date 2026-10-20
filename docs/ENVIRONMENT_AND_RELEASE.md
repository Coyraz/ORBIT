# Environment, Build & Binary Release

[← README](../README.md)

## Baseline

| Komponen | Baseline | Catatan |
| --- | --- | --- |
| OS | Ubuntu 24.04 Noble | OS target sprint |
| ROS | ROS 2 Jazzy Jalisco | Hindari pencampuran distro pada environment uji |
| Simulator | Gazebo Harmonic | Pasangan resmi Jazzy; gunakan integrasi ros_gz |
| Build | colcon + ament | Sesuai jenis package implementasi |
| Navigasi | Diputuskan melalui feasibility/ADR | Nav2 dapat dievaluasi; bukan implementasi yang sudah dipilih |
| Binary | Format dipilih D2; target package installable | `.deb` dapat menjadi kandidat; source archive bukan binary release |
| Arsitektur | Catat mesin FMS dan robot aktual | Build/test artifact terpisah jika mendukung lebih dari satu arsitektur |

Dokumentasi resmi Gazebo mencantumkan Ubuntu 24.04, Jazzy dan Harmonic sebagai kombinasi yang sesuai. Setelah repository ROS dikonfigurasi menurut panduan instalasi resmi, paket integrasi Jazzy adalah `ros-jazzy-ros-gz`. Jangan menganggap package ORBIT sudah tersedia hanya karena dependency terpasang.

Referensi: [ROS 2 Jazzy — Ubuntu deb installation](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html) dan [Gazebo — Installing Gazebo with ROS](https://gazebosim.org/docs/harmonic/ros_installation/). Panduan instalasi ROS perlu diikuti pada mesin target; halaman tersebut tidak berhasil dibaca saat penyusunan paket ini. Kesesuaian simulator diverifikasi dari dokumentasi Gazebo pada 19 Oktober 2026.

## Setup implementasi yang perlu dilengkapi

Saat ini repository berisi paket dokumentasi. Tim implementasi harus menambahkan nama package, dependency, konfigurasi, launch file dan langkah demo yang sebenarnya. Kontrak harus mencatat robot_id, task_id, schema/version, feedback/result/error, namespace, frame TF, QoS, clock, timeout serta kebijakan duplicate/retry/recovery.

Struktur implementasi **usulan**, dibuat jika dipilih dalam review arsitektur:

```text
src/
  orbit_interfaces/
  orbit_fleet_manager/
  orbit_robot_adapter/
  orbit_simulation/
  orbit_bringup/
tests/
config/
```

Pemisahan adapter TIFA dan NEVO menjadi package sendiri atau plugin dipilih melalui ADR. Tidak ada endpoint/protokol robot fisik yang diasumsikan dalam paket dokumentasi ini.

## Verifikasi environment

Catat OS, arsitektur, distro ROS, versi package yang relevan, RMW, network/discovery configuration dan simulator. Konfigurasi simulasi dan fisik dipisahkan; jangan menaruh credential di repository. Simpan konfigurasi demo generik yang cukup untuk reproduksi.

Contoh perintah build/test **setelah source package tersedia**:

```bash
source /opt/ros/jazzy/setup.bash
rosdep install --from-paths src --ignore-src -r -y --rosdistro jazzy
colcon build --symlink-install
source install/setup.bash
colcon test
colcon test-result --verbose
```

Sesuaikan `setup.bash`/`setup.zsh` dengan shell. Ini alur pengembangan dari source; clean-install gate menggunakan artifact binary tanpa build ulang source ORBIT. Perintah launch yang sebenarnya wajib dimasukkan ke runbook sebelum G1.

## Rencana release

1. D2: pilih format package, supported architecture dan dependency boundary melalui ADR.
2. D7: freeze fitur dan identifikasi release candidate commit.
3. D8: build artifact dari commit tersebut; jalankan CI dan tests relevan.
4. Tetapkan version/tag yang konsisten, nama artifact, target OS/ROS/arsitektur dan SHA-256.
5. Reviewer menginstal pada host/VM/container bersih yang sesuai fungsi yang diuji; sebutkan kebutuhan display, perangkat atau network jika ada.
6. Jalankan smoke test dengan perintah yang benar-benar tersedia dari binary terpasang. Simpan expected/actual dan bukti.
7. D9: final demo memakai artifact yang diverifikasi; publikasikan release beserta install guide dan known issues.

Untuk artifact simulasi, environment bersih harus mampu menjalankan simulator/smoke scenario yang dinyatakan. Untuk runtime fisik, dokumentasikan driver/firmware eksternal yang sudah tersedia dan batas cakupan package. Jangan mengklaim dukungan hardware atau arsitektur yang belum diuji.

## Isi release notes minimum

- Version/tag, commit, tanggal dan daftar artifact beserta checksum.
- Ubuntu 24.04, ROS 2 Jazzy, arsitektur yang diuji dan dependency terukur.
- Perintah install, konfigurasi, startup dan smoke test.
- Cara memperoleh world/model/asset demo yang diperlukan.
- Hasil G1–G3 dan tautan evidence.
- Known issues, batas fitur, cara stop, uninstall dan rollback.
- Reviewer dan hasil clean install.

Gunakan [Release Checklist](../templates/RELEASE_CHECKLIST.md). Pipeline, installer, binary dan release merupakan target pekerjaan sprint; paket ini tidak menyertakannya sebagai hasil yang sudah dibuat.

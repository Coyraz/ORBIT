# PROJECT ORBIT

**Project-Based Engineering Sprint · Diagonal Robotics**  
**20–30 Oktober 2026 · 9 hari kerja · 36 jam efektif**  
**16.00–18.00 & 19.00–21.00 WIB · ROS 2 Jazzy · Ubuntu 24.04**

ORBIT adalah sprint internal untuk membangun prototype **Multi-Robot Fleet Management System (FMS)** pada fasilitas logistik fiktif: menerima pekerjaan, memilih robot, mengirim tugas, memantau eksekusi, menerima hasil, dan menangani kegagalan dasar. Targetnya simulasi minimal dua robot serta validasi fisik pada **TIFA dan NEVO**.

Output sprint: **working prototype + physical validation + GitHub documentation + installable binary release + engineering evaluation report**.

## Mulai dari sini

| Dokumen | Kegunaan |
| --- | --- |
| [Sprint Charter](docs/SPRINT_CHARTER.md) | Tujuan, batas scope, deliverables, gate dan risiko |
| [Kickoff Brief](docs/KICKOFF_BRIEF.md) | Brief siap dibagikan kepada peserta |
| [Project Challenge](docs/PROJECT_CHALLENGE.md) | Studi kasus, kebutuhan, pertanyaan desain dan skenario |
| [Timeline 9 Hari](docs/TIMELINE_9_DAYS.md) | Dua sesi setiap hari, output, dependency dan checkpoint |
| [Engineering Workflow](docs/ENGINEERING_WORKFLOW.md) | Ideation sampai release, branch, PR, CI dan evidence |
| [Team Roles](docs/TEAM_ROLES.md) | Peserta, tanggung jawab, owner dan reviewer |
| [Acceptance Criteria](docs/ACCEPTANCE_CRITERIA.md) | Kriteria terukur untuk empat gate |
| [Evaluation Rubric](docs/EVALUATION_RUBRIC.md) | Penilaian individu dan technical defense |
| [Mind Map](docs/MIND_MAP.md) | Transkripsi mind map Briefing v1 dalam Mermaid dan outline |
| [Environment & Release](docs/ENVIRONMENT_AND_RELEASE.md) | Baseline teknis dan prosedur pembuktian binary |
| [Task Map](docs/TASK_MAP.md) | Pemetaan 14 tahap pekerjaan ke sembilan hari |
| [Document Status](docs/DOCUMENT_STATUS.md) | Dasar dokumen dan rincian operasional yang perlu ditetapkan |

## Empat gate akhir — 30 Oktober 2026

1. **G1 — Simulation:** FMS end-to-end dengan minimal dua robot dalam simulasi.
2. **G2 — Physical:** TIFA dan NEVO divalidasi secara aman dengan laporan uji masing-masing.
3. **G3 — Release:** binary berversi dapat dipasang pada environment target dan menjalankan fungsi yang didemonstrasikan.
4. **G4 — People:** seluruh engineer menyelesaikan technical defense dan evaluasi kontribusi individual.

Kegagalan gate dicatat sebagai **FAIL** atau **BLOCKED** beserta bukti dan tindakan lanjut. Rekaman simulasi tidak menggantikan bukti fisik.

## Jadwal dan peserta

Hari aktif: **20, 21, 22, 23, 26, 27, 28, 29, 30 Oktober 2026**. Tanggal 24–25 Oktober tidak dihitung sebagai hari sprint. Setiap hari terdiri dari dua sesi, masing-masing dua jam; total 9 × 4 = **36 jam per peserta**. Jeda 18.00–19.00 tidak dihitung.

Peserta: **Kiki (Rifqy), Arya Delphi, Reinald Mariel, Nasywa, Vacha**. Pembagian owner modul ditetapkan pada kickoff; satu orang dapat memegang lebih dari satu peran.

## Cara menggunakan repository

GitHub menjadi sumber utama kode, keputusan desain, review, hasil uji dan release. ClickUp opsional untuk tracking. Mulai dengan membaca brief dan challenge, tetapkan owner di Team Roles, lalu buat issue dan branch untuk pekerjaan harian.

Paket ini berisi **dokumentasi dan template**, belum implementasi robot/FMS atau binary yang telah diuji. Perintah build pada dokumen environment berlaku setelah package implementasi tersedia. Checklist kosong berarti belum diverifikasi.

```text
ORBIT/
├── README.md
├── docs/                 # Pedoman sprint dan mind map
├── templates/            # Requirements, feasibility, ADR, test, defense
├── evidence/README.md    # Konvensi bukti; belum berisi hasil uji
└── .github/              # Template issue dan pull request
```

Repository target: [kikifachrizi/ORBIT](https://github.com/kikifachrizi/ORBIT). Dokumen menggunakan bahasa Indonesia dengan istilah teknis yang konsisten. Rincian implementasi yang belum dipilih harus diputuskan melalui feasibility review dan ADR, bukan dianggap sudah tersedia.

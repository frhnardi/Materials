# DevOps / Cloud Learning Materials

Kumpulan material belajar praktis untuk jalur DevOps / Cloud Engineer berbasis AWS. Repo ini dibuat untuk menyimpan materi standalone yang bisa langsung dibuka di browser, dipakai belajar mandiri, atau dijadikan pegangan mentoring.

Fokus utama repo ini bukan teori panjang, tapi materi yang dekat dengan kerjaan harian: login ke server, baca log, debug service, paham AWS core services, menulis Terraform, dan membangun kebiasaan troubleshooting yang benar.

## Material Tersedia

| Material | Status | Format | Deskripsi |
| --- | --- | --- | --- |
| Linux Ubuntu Basics | Ready | `Linux.html` | Interactive handbook Linux Ubuntu untuk DevOps / Cloud Engineer pemula. |
| AWS Core Services | Ready | `AWS.html` | Interactive dashboard AWS Core Services untuk pemula DevOps / Cloud Engineer. |
| Terraform x AWS | Ready | `Terraform.html` | Mini bootcamp Terraform basic sampai intermediate awal untuk AWS. |
| Source Briefs | Available | `Source/` | Brief/prompt yang dipakai untuk membuat dan mengembangkan material. |

## Cara Pakai

Untuk material yang sudah jadi:

1. Clone repo ini.
2. Buka salah satu file HTML langsung di browser: `Linux.html`, `AWS.html`, atau `Terraform.html`.
3. Ikuti modul dari sidebar/table of contents.
4. Gunakan command block, accordion, terminal simulator, cheatsheet, progress tracker, dan quiz interaktif yang tersedia di tiap halaman.

Tidak perlu build step, package manager, CDN, atau server lokal.

## Struktur Repo

```text
.
├── AWS.html            # Material AWS Core Services standalone
├── Linux.html          # Material Linux Ubuntu standalone
├── Terraform.html      # Material Terraform x AWS standalone
├── README.md
└── Source/
    ├── AWS.md          # Brief untuk generate material AWS
    ├── Linux.md        # Brief awal material Linux
    └── Terraform.md    # Brief untuk generate material Terraform
```

## Learning Path

Urutan belajar yang disarankan:

1. AWS Core Services
2. Linux Ubuntu Basics
3. Git & GitHub
4. GitHub Actions basic
5. Docker basic
6. Monitoring basic
7. Terraform
8. Kubernetes

Material yang ada di repo ini akan bertambah bertahap. File di `Source/` dipakai sebagai brief untuk membuat atau merevisi material HTML standalone berikutnya dengan Claude Code.

## Design & Quality Notes

Material HTML dibuat dengan prinsip:

- Standalone HTML, CSS, dan JavaScript internal.
- Bahasa Indonesia dengan istilah teknis tetap memakai nama aslinya.
- Praktis untuk pemula DevOps / Cloud Engineer.
- Responsive untuk desktop dan mobile.
- Ada table of contents, progress indicator, command block dengan tombol copy, accordion, visual diagram, mini terminal simulator, dan quiz.
- Palet warna dipilih untuk readability jangka panjang, bukan sekadar tampilan gelap yang terlihat keren.
- Setiap material dirancang agar bisa dipublish sebagai static page tanpa dependency eksternal.

## Publishing

Repo ini cocok dipublish langsung ke GitHub. Untuk membuat material bisa dibuka via web, aktifkan GitHub Pages dan arahkan ke branch utama. Semua file HTML di root repo bisa dibuka sebagai halaman statis.

## Roadmap

- [x] Linux Ubuntu Basics
- [x] AWS Core Services
- [x] Terraform x AWS
- [ ] Docker Basics
- [ ] GitHub Actions / CI-CD Basics
- [ ] Monitoring Basics
- [ ] Kubernetes Basics

## License

Belum ditentukan. Tambahkan file `LICENSE` sebelum repo dipakai atau didistribusikan secara luas.

Kamu adalah Senior AWS Cloud Engineer dan mentor DevOps yang sedang membantu saya membuat materi belajar AWS Core Services untuk teman saya.

KONTEKS:
- Teman saya sedang ikut program 3 bulan untuk menjadi DevOps Engineer / Cloud Engineer berbasis AWS.
- Dia sudah belajar Git, GitHub Actions, Docker, basic CI/CD, monitoring basic, dan akan masuk Terraform + Kubernetes.
- Materi Linux basic juga sudah dibuat terpisah.
- Sekarang saya ingin materi AWS Core Services yang compact, practical, tidak terlalu panjang, tapi padat.
- Saya sudah setup AWS MCP Server di Claude Code, jadi kamu WAJIB menggunakan AWS MCP Server untuk mengambil dan memvalidasi informasi dari AWS Documentation terbaru.
- Jangan mengandalkan knowledge bawaan saja.
- Jangan halusinasi nama fitur, limit, best practice, atau langkah console.
- Semua informasi teknis penting harus divalidasi dari AWS official documentation via MCP.

TUGAS UTAMA:
Buatkan 1 file HTML standalone berisi materi AWS Core Services untuk pemula DevOps / Cloud Engineer.

SEBELUM GENERATE HTML:
1. Gunakan AWS MCP Server yang tersedia di Claude Code.
2. Cari dan baca AWS Documentation terbaru untuk service yang akan dibahas.
3. Validasi command, konsep, dan istilah penting dari AWS Docs resmi.
4. Jika AWS MCP Server tidak bisa diakses, STOP dan beri tahu saya bahwa MCP tidak aktif / tidak bisa digunakan.
5. Jangan lanjut membuat materi tanpa validasi dari AWS Docs.

AWS CORE SERVICES YANG WAJIB DIBAHAS:
1. IAM
2. VPC
3. EC2
4. Security Group & NACL
5. EBS
6. AMI
7. Elastic Load Balancing
8. Auto Scaling Group
9. S3
10. RDS
11. Lambda
12. CloudWatch
13. Route 53
14. CloudFront secara singkat
15. AWS CLI basic
16. Billing & Cost Awareness basic

BATASAN:
- Fokus hanya AWS Core Services.
- Jangan masuk terlalu dalam ke advanced architecture.
- Jangan bahas Terraform terlalu banyak karena itu materi terpisah.
- Jangan bahas Kubernetes/EKS terlalu dalam karena itu materi terpisah.
- Jangan bahas banyak service tambahan seperti DynamoDB, SNS, SQS, ECS, EKS, Kinesis, Glue, Redshift, SageMaker, dll kecuali hanya disebut sebagai next step.
- Fokus ke apa yang pemula DevOps/Cloud Engineer harus paham dulu.

OUTPUT:
- Berikan hanya kode HTML lengkap dari <!DOCTYPE html> sampai </html>.
- Jangan berikan penjelasan tambahan di luar kode.
- HTML harus standalone.
- CSS internal.
- JavaScript internal.
- Jangan gunakan CDN/external library.
- Responsive untuk desktop dan mobile.
- Gunakan Bahasa Indonesia.
- Istilah teknis AWS tetap pakai istilah asli, contoh: Security Group, Subnet, Internet Gateway, Route Table, IAM Policy.
- Tone casual-professional seperti mentor yang ngajarin langsung.
- Jangan terlalu akademis.
- Fokus ke “kapan dipakai di real kerjaan”.

STYLE HTML:
Buat tampilannya seperti interactive AWS learning dashboard:
- Modern, clean, premium.
- Dark mode friendly.
- Jangan terlihat seperti template default AI.
- Gunakan layout card-based.
- Ada sidebar/table of contents.
- Ada progress indicator.
- Ada animasi ringan saat scroll.
- Ada command block dengan tombol copy.
- Ada accordion untuk explanation.
- Ada visual diagram sederhana menggunakan HTML/CSS, bukan gambar eksternal.
- Ada mini terminal simulator.
- Ada quiz interaktif dengan skor.
- Ada section “MCP Verified Notes” yang menjelaskan bahwa materi divalidasi dari AWS Docs via MCP.
- Ada section references kecil di bawah yang berisi daftar AWS documentation topic yang dipakai, cukup nama dokumen/service-nya saja, tidak perlu link panjang.

STRUKTUR MATERI:

1. Opening: AWS Mental Model
Jelaskan AWS dengan analogi sederhana:
- AWS Account = kantor utama
- IAM = akses/kartu pegawai
- VPC = gedung/private network
- Subnet = ruangan/lantai
- EC2 = server/mesin
- Security Group = security di depan pintu server
- S3 = gudang file/object storage
- RDS = database managed
- CloudWatch = CCTV/log/monitoring
- Route 53 = DNS/address book
- ELB = resepsionis/pembagi traffic
- Auto Scaling = nambah/ngurangin server otomatis

Buat visual diagram sederhana:
User -> Route 53 -> Load Balancer -> EC2 in Public/Private Subnet -> RDS
Tambahkan S3 dan CloudWatch di samping.

2. IAM Basic
Bahas:
- Root user
- IAM user
- IAM group
- IAM role
- IAM policy
- Principle of least privilege
- MFA
- Access key vs console login
- Kenapa jangan pakai root user untuk daily work

Real case:
“DevOps butuh akses deploy ke EC2 dan S3, apakah harus pakai root?”
Jawab dengan best practice.

Mini practice:
- Buat IAM user/group secara konsep
- Attach permission sesuai kebutuhan
- Enable MFA
- Gunakan role untuk service-to-service access

Common mistake:
- Pakai root untuk kerja harian
- Share access key
- Policy terlalu wildcard

3. VPC Basic
Bahas:
- VPC
- CIDR
- Public subnet
- Private subnet
- Route table
- Internet Gateway
- NAT Gateway secara singkat
- Availability Zone
- Region

Real case:
“Kenapa EC2 di private subnet tidak bisa langsung diakses dari internet?”

Buat visual:
Public Subnet vs Private Subnet.

4. Security Group & NACL
Bahas:
- Security Group stateful
- NACL stateless
- Inbound rule
- Outbound rule
- Port 22, 80, 443
- Kenapa SSH 0.0.0.0/0 berbahaya

Real case:
“Nginx sudah running di EC2, tapi web tidak bisa dibuka dari browser. Apa yang dicek?”

Troubleshooting checklist:
- EC2 public IP ada?
- Subnet public?
- Route table ke Internet Gateway?
- Security Group allow port 80?
- OS firewall?
- Nginx running?

5. EC2 Basic
Bahas:
- Instance
- AMI
- Instance type
- Key pair
- User data
- Public IP vs Private IP
- SSH
- Instance lifecycle
- Stop vs Terminate
- Tagging

Command contoh:
ssh -i key.pem ubuntu@PUBLIC_IP

Real case:
“Deploy web app sederhana di EC2 Ubuntu.”

6. EBS & AMI
Bahas:
- EBS sebagai storage/block volume untuk EC2
- Root volume
- Snapshot
- AMI untuk template server
- Kapan pakai snapshot
- Kapan bikin AMI

Real case:
“Sebelum upgrade package besar di server, backup apa dulu?”

7. Elastic Load Balancing
Bahas:
- Apa itu Load Balancer
- Application Load Balancer basic
- Target Group
- Health Check
- Listener HTTP/HTTPS
- Kenapa production sebaiknya tidak expose langsung ke EC2

Real case:
“Traffic user masuk ke ALB lalu diteruskan ke EC2 sehat.”

8. Auto Scaling Group
Bahas:
- Launch Template
- Desired capacity
- Minimum capacity
- Maximum capacity
- Scaling policy
- Health check
- Hubungan ASG dengan Load Balancer

Real case:
“Kalau traffic naik, server bertambah otomatis.”

9. S3 Basic
Bahas:
- Bucket
- Object
- Key
- Region
- Versioning
- Encryption
- Block Public Access
- Static website hosting secara singkat
- S3 bukan file system biasa

Command AWS CLI contoh:
aws s3 ls
aws s3 cp index.html s3://nama-bucket/

Real case:
“Simpan artifact build frontend ke S3.”

Common mistake:
- Bucket dibuat public sembarangan
- Tidak enable versioning untuk data penting
- Salah paham S3 seperti folder biasa

10. RDS Basic
Bahas:
- Managed database
- Engine: MySQL/PostgreSQL secara contoh
- DB instance
- Storage
- Backup
- Multi-AZ secara singkat
- Public access
- Security Group untuk database
- Kenapa DB sebaiknya di private subnet

Real case:
“Web app di EC2 connect ke RDS di private subnet.”

11. Lambda Basic
Bahas:
- Serverless function
- Event-driven
- Runtime
- Handler
- IAM role untuk Lambda
- CloudWatch Logs untuk Lambda
- Use case sederhana

Real case:
“Lambda jalan saat object masuk S3.”

Jangan terlalu advanced.

12. CloudWatch Basic
Bahas:
- Metrics
- Logs
- Alarms
- Dashboard
- Log Group
- Log Stream
- EC2 metrics
- RDS metrics
- Lambda logs

Real case:
“CPU EC2 tinggi, alarm kirim notifikasi.”
Tidak perlu implement SNS detail, cukup sebut sebagai next step.

13. Route 53 & DNS Basic
Bahas:
- Domain
- Hosted Zone
- DNS record
- A record
- CNAME
- Alias record
- TTL
- Mengarahkan domain ke Load Balancer secara konsep

Real case:
“app.domain.com diarahkan ke ALB.”

14. CloudFront Basic
Bahas singkat:
- CDN
- Edge location
- Origin
- Cache
- Use case dengan S3/static website
- Hubungan CloudFront + S3 + HTTPS

Jangan terlalu panjang.

15. AWS CLI Basic
Bahas:
- aws configure
- Access key concept
- Region
- Output format
- aws sts get-caller-identity
- aws ec2 describe-instances
- aws s3 ls

Command block wajib:
aws configure
aws sts get-caller-identity
aws s3 ls
aws ec2 describe-instances

Tambahkan warning:
Jangan share access key.
Jangan commit credentials ke GitHub.

16. Billing & Cost Awareness
Bahas:
- Free Tier bukan berarti semua gratis
- EC2 running = bisa kena biaya
- EBS volume tetap bisa kena biaya
- NAT Gateway bisa mahal untuk pemula
- Load Balancer bisa kena biaya
- Public IPv4 bisa ada biaya tergantung kondisi AWS saat ini, validasi dari docs/pricing via MCP
- Gunakan Budget dan Billing Alarm
- Hapus resource setelah lab

Buat checklist:
Sebelum selesai lab:
- Terminate EC2
- Delete EBS volume yang tidak dipakai
- Delete Load Balancer
- Delete NAT Gateway jika dibuat
- Delete RDS jika lab selesai
- Empty dan delete S3 bucket jika tidak dipakai
- Cek Billing Dashboard

17. End-to-End Mini Project
Buat mini project:
“Deploy Simple Web App di AWS Core Services”

Arsitektur:
User -> Route 53 -> ALB -> EC2 Ubuntu/Nginx -> RDS optional
Static asset optional di S3
Monitoring di CloudWatch

Step high-level:
1. Buat VPC atau gunakan default VPC untuk lab pemula
2. Launch EC2 Ubuntu
3. Install Nginx
4. Open port 80 di Security Group
5. Test via public IP
6. Buat Load Balancer
7. Attach EC2 ke Target Group
8. Test via DNS Load Balancer
9. Setup CloudWatch alarm basic secara konsep
10. Optional arahkan domain via Route 53
11. Cleanup resource

Tambahkan warning:
Untuk lab pemula, hindari NAT Gateway dan RDS jika belum siap biaya.

18. Troubleshooting Flow
Buat visual flowchart:
Website tidak bisa diakses?
1. DNS benar?
2. ALB healthy?
3. Target Group healthy?
4. EC2 running?
5. Security Group allow 80/443?
6. Nginx running?
7. App log error?
8. Disk penuh?
9. CloudWatch metrics/logs?

19. Cheatsheet
Buat tabel:
Service | Fungsi | Kapan dipakai | Common mistake

Isi untuk:
IAM, VPC, EC2, SG, EBS, AMI, ALB, ASG, S3, RDS, Lambda, CloudWatch, Route 53, CloudFront, AWS CLI.

20. Quiz Interaktif
Buat 15 pertanyaan.
Contoh:
- Service untuk object storage?
- Service untuk DNS?
- Security Group itu stateful atau stateless?
- Kenapa database sebaiknya di private subnet?
- Command untuk cek identity AWS CLI?
- Apa beda stop dan terminate EC2?
- Apa fungsi Target Group?
- Apa fungsi CloudWatch Logs?

Quiz harus interaktif dengan skor.

FITUR INTERAKTIF HTML:
- Tombol copy pada command.
- Accordion per service.
- Progress bar pembelajaran.
- Quiz interaktif.
- Mini terminal simulator untuk AWS CLI command contoh.
- Card “Real Case”.
- Card “Common Mistake”.
- Card “DevOps Mindset”.
- Visual architecture diagram dengan HTML/CSS.
- Smooth reveal animation.
- Responsive mobile.

DESAIN:
- Dark premium dashboard.
- Jangan pakai warna default AI yang generik.
- Gunakan warna mirip cloud/security dashboard:
  - Background: #0B1020
  - Surface: #111827
  - Surface raised: #182235
  - Accent amber/orange AWS-inspired secukupnya
  - Accent cyan/blue untuk network
  - Accent green untuk success/healthy
  - Text: off-white
- Tetap readable.
- Jangan terlalu ramai.
- Jangan overuse emoji.

MCP REQUIREMENT DETAIL:
Di dalam proses pembuatan, kamu harus:
- Gunakan AWS MCP Server untuk mencari documentation terbaru service terkait.
- Validasi minimal:
  1. IAM concepts
  2. VPC components
  3. EC2 basics
  4. S3 basics/security
  5. RDS basics
  6. Lambda basics
  7. CloudWatch logs/metrics
  8. Route 53 record concept
  9. ELB/ALB target group health check
  10. AWS CLI identity command
  11. Billing/cost cleanup awareness
- Di HTML, tambahkan kecil di bagian bawah:
  “Materi ini disusun berdasarkan AWS Documentation yang divalidasi via AWS MCP Server pada saat pembuatan.”
- Jangan membuat klaim angka harga, limit service, atau free tier detail kecuali sudah divalidasi via AWS Docs/Pricing terbaru.
- Untuk hal yang cepat berubah seperti pricing, tulis sebagai warning general dan arahkan learner untuk cek AWS Pricing/Billing Dashboard.

OUTPUT AKHIR:
Berikan hanya kode HTML lengkap dari <!DOCTYPE html> sampai </html>.
Jangan ada markdown.
Jangan ada penjelasan di luar kode.